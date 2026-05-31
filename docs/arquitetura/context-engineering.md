# Arquitetura de Contexto — AGRO-e Intelligence

## Context Engineering — Princípios e Decisões

O sistema usa uma arquitetura de contexto em 3 camadas com separação explícita entre
instrução, dado e memória. O objetivo é garantir que cada agente receba exatamente
o que precisa — sem ruído, sem informação irrelevante, e com proteção contra
manipulação de entrada.

---

## As 3 Camadas

```
CAMADA 1 — Contexto Fixo
  O que é: System prompts especializados por agente
  Função: Define papel, escopo, formato e limites de cada sub-agente
  Imutável durante a execução — não alterável por entrada do usuário

CAMADA 2 — Contexto Dinâmico de Curto Prazo
  O que é: Estado da sessão ativa por operador
  Função: Continuidade conversacional, processamento de mídia (áudio/imagem/PDF)
  TTL controlado — eliminado automaticamente após inatividade

CAMADA 3 — Contexto Dinâmico de Longo Prazo
  O que é: Perfil do produtor, histórico de interações, resumo contextual
  Função: Reconhece o operador entre sessões sem re-identificação manual
  Persistência seletiva — nem tudo é retido, apenas o relevante para decisões futuras
```

---

## Separação Dado vs. Instrução

Uma das decisões centrais de segurança: dados externos (clima, câmbio, histórico)
são injetados em seções delimitadas do contexto, separadas da instrução real.

O modelo processa os dados como **input de análise**, não como **comandos**.
Isso protege contra prompt injection via conteúdo de fontes externas.

---

## Anti-Hallucination por Design

O sistema não gera nomes, valores ou identificadores. Todos os elementos que
aparecem na saída — nomes de clientes, valores de produtos, datas — são
extraídos de queries SQL determinísticas e injetados como strings formatadas
no contexto do agente.

O modelo interpreta e comunica. Não inventa dados.

---

## Think Tool — Raciocínio Auditável

O agente roteador usa uma etapa explícita de raciocínio antes de cada decisão
de roteamento — registrando o processo de análise separado da resposta final.

Isso serve a dois propósitos: qualidade (o modelo explora trade-offs antes de
concluir) e auditabilidade (é possível inspecionar por que o agente tomou
determinada decisão).

---

## Decisões de Arquitetura

**Por que context engineering em vez de RAG puro?**
O volume de dados operacionais por cliente cabe integralmente no contexto de
cada execução — não é necessário busca semântica para recuperar os dados
relevantes. RAG seria overhead desnecessário para este caso de uso. A escolha
deliberada foi usar SQL preciso e contexto estruturado, não recuperação
aproximada por similaridade.

**Por que não usar um único prompt com tudo?**
Sub-agentes especializados com contextos menores produzem análises mais precisas
do que um único agente generalista com contexto grande. A separação também
permite isolar falhas — um erro no agente de câmbio não compromete o agente
documental.

**Por que persistir resumo contextual e não o histórico completo?**
Histórico completo cresce indefinidamente e introduz ruído nas respostas.
O sistema gera um resumo compacto após cada execução — preservando o que é
relevante para interações futuras sem carregar o peso de toda a conversa anterior.
