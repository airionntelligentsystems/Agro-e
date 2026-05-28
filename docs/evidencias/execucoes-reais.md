# Evidências de Funcionamento — agro-e

## Execuções Reais Confirmadas

Todas as execuções abaixo ocorreram em produção, no ambiente n8n real conectado ao Supabase Arion (`enfxvayjioiskdfplfex`), com WhatsApp real via Evolution API.

---

## 1. Resposta Real via WhatsApp

**Data:** 27/05/2026  
**Mensagem enviada:** "olá, bom dia! tudo bem?"  
**Resposta recebida:**

```
Olá! Como posso ajudar você hoje no monitoramento
de riscos e oportunidades no agronegócio?
```

**Evidência:** Mensagem recebida diretamente no WhatsApp conectado à instância Evolution.  
**Fluxo confirmado:** WhatsApp → Evolution API → Webhook WF01 → Normalizador → Supabase → WF02 → Agente Roteador → Resposta → WhatsApp.

---

## 2. Execuções com Sucesso — WF01

| ID Execução | Modo | Status | Duração |
|-------------|------|--------|---------|
| 27187 | Reativo (webhook) | ✅ success | ~4s |
| 27188 | Reativo (webhook) | ✅ success | ~4s |
| 27189 | Reativo (webhook) | ✅ success | ~4s |
| 27192 | Reativo (webhook) | ✅ success | ~3.7s |

---

## 3. Execuções com Sucesso — WF02 (Console Multi-Agentes)

| ID Execução | Agentes Acionados | Status | Saída |
|-------------|-------------------|--------|-------|
| 27155 | Roteador + Documental | ✅ success | Análise de risco |
| 27156 | Roteador + Climático + Câmbio | ✅ success | Relatório completo |
| 27157 | Roteador + Proativo | ✅ success | Score da carteira |

---

## 4. Memória Conversacional Funcionando

**Tabela:** `agroe_chat_memory` (PostgreSQL)  
**Registros acumulados:** 28 mensagens reais  
**Sessões ativas:** Múltiplas sessões por número de telefone  

```sql
-- Resultado real do banco:
SELECT COUNT(*) FROM agroe_chat_memory;
-- Resultado: 28
```

---

## 5. Relatório de Gestão por Email

**Disparado via:** WF05 — Schedule 9h + Webhook de teste  
**Destinatário:** andre_henrique.fernandes@outlook.com  
**Avaliação do usuário após receber:** *"ficou excelente, altíssimo nível"*

O email HTML inclui:
- Cards de resumo executivo (críticos, altos, médios, oportunidades)
- Alerta de SLA vencido quando aplicável
- Cartões detalhados com ação recomendada por item
- Tabela completa de itens pendentes

---

## 6. Relatórios de Gestão no Banco

**Tabela:** `agroe_relatorios_gestao`  
**Registros inseridos:** 6 itens com dados simulados reais

```
ID | Tipo                  | Prioridade | Status   | Título
---|-----------------------|------------|----------|----------------------------------
1  | risco_documental      | critica    | pendente | [RS-012] Registro vencido há 5d
2  | risco_climatico       | alta       | pendente | [MG-001] Chuva 68mm + Licença 3d
3  | oportunidade_comercial| alta       | pendente | Roberto — Ureia caiu 5.7%
4  | oportunidade_comercial| alta       | pendente | Carlos — Seca + Gotejamento
5  | expansao_estrategica  | alta       | pendente | Jataí/GO — Coop. Cerrado Verde
6  | risco_perda_cliente   | alta       | pendente | Marina Costa — CanaSul avançando
```

---

## 7. Integração CRM Webhook — WF06

**Teste:** POST para `/agroe-crm-entrada` com payload de alerta  
**Resposta:** HTTP 200 OK com payload normalizado e evento_id único  
**Tempo de resposta:** ~930ms

---

## 8. Estado do Banco de Dados

Resultado real de `SELECT COUNT(*) FROM` em cada tabela:

| Tabela | Registros |
|--------|-----------|
| agroe_chat_memory | 28 |
| agroe_historico_comercial | 16 |
| agroe_catalogo_produtos | 8 |
| agroe_documentos | 8 |
| agroe_regioes_estrategicas | 7 |
| agroe_clientes | 7 |
| agroe_relatorios_gestao | 6 |
| agroe_chamados | 6 |
| agroe_integracao_conectores | 6 |
| agroe_operacoes | 5 |
| agroe_contexto | 4 |
| agroe_concorrentes | 4 |
| agroe_historico_execucoes | 4 |

---

## 9. Workflows Ativos em Produção

| Workflow | ID | Nós | Status |
|----------|----|-----|--------|
| WF01 — Entrada + Monitor Proativo | RhoVjWOJQmLQRvW7 | 133 | ✅ Ativo |
| WF02 — Console Multi-Agentes | WFUV3XhM8geoTXP3 | 31 | ✅ Ativo |
| WF03 — Escalada Humano | lAvbWUF4W2dyZZms | 13 | ✅ Ativo |
| WF04 — Monitor Vencimentos | KROmG5dlSA3KMhDh | 48 | ✅ Ativo |
| WF05 — Relatório de Gestão | WHpdDwmQOCTO0W1V | 8 | ✅ Ativo |
| WF06 — Integração CRM/ERP | y5xUndqtLnr2TzBU | 11 | ✅ Ativo |

---

*Evidências coletadas em 27–28/05/2026. Sistema em operação contínua.*
