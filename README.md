# 🌱 agro-e — Inteligência Agrícola Autônoma

> **Sistema de monitoramento autônomo de riscos e oportunidades no agronegócio brasileiro.**  
> Em operação real. Não é um protótipo de demonstração — é um produto.

---

## O que é

O agro-e é uma plataforma de IA multi-agente que opera como um analista sênior digital, 24h por dia, monitorando operações agrícolas, identificando riscos documentais, climáticos e cambiais, e descobrindo oportunidades comerciais — sem depender de input humano.

**Resultado do monitoramento diário das 8h:**
- Quais operações estão com documentação em risco e por quê
- Qual o impacto da variação cambial em cada produtor
- Quais clientes devem ser acionados agora com oferta específica
- Quais regiões têm oportunidade de expansão frente à concorrência

---

## Arquitetura

```
╔══════════════════════════════════════════════════════════════╗
║  WF01 — ENTRADA + MONITOR PROATIVO (133 nós)                ║
║  ├── Reativo: WhatsApp → Normalizador → Redis → WF02        ║
║  └── Proativo: Schedule 8h → 7 fontes de dados → WF02       ║
╚══════════════════════════════════╦═══════════════════════════╝
                                   ║
╔══════════════════════════════════╩═══════════════════════════╗
║  WF02 — CONSOLE MULTI-AGENTES (31 nós)                      ║
║  ├── Agente Roteador (GPT-4.1-mini)                         ║
║  ├── Think Tool × 2 (raciocínio explícito)                  ║
║  ├── agente_analista_documental                             ║
║  ├── agente_monitor_climatico                               ║
║  ├── agente_analista_mercado_cambio                         ║
║  ├── agente_monitoramento_proativo                          ║
║  ├── agente_inteligencia_comercial ← diferencial            ║
║  ├── Google Calendar (3 tools)                              ║
║  ├── Postgres Chat Memory                                   ║
║  └── encaminhar_para_responsavel_humano → WF03              ║
╚══════════════════════════════════╦═══════════════════════════╝
            ┌──────────────────────┴──────────────────────┐
╔═══════════╩══════════════╗  ╔══════════════════╗  ╔═════╩════════════════════╗
║ WF03 — ESCALADA (13 nós) ║  ║ WF04 — VENCIM.  ║  ║ WF05 — GESTÃO (8 nós)   ║
║ Pausa IA · Notifica      ║  ║ 7h e 12h diários ║  ║ Email HTML + WhatsApp   ║
║ responsável via WA       ║  ║ Docs vencendo    ║  ║ Relatório rastreável    ║
╚══════════════════════════╝  ╚══════════════════╝  ╚══════════════════════════╝

╔══════════════════════════════════════════════════════════════╗
║  WF06 — INTEGRAÇÃO CRM/ERP — ADAPTADOR UNIVERSAL (11 nós)  ║
║  Salesforce · HubSpot · Siagri · TOTVS · AgroSmart · Custom ║
╚══════════════════════════════════════════════════════════════╝
```

---

## Técnicas Implementadas

| Técnica | Implementação | Evidência |
|---------|--------------|-----------|
| **Prompt Engineering** | 7 system prompts distintos com papel, escopo, formato, anti-hallucination e anti-injection | `docs/arquitetura/system-prompts.md` |
| **Context Engineering** | 3 camadas: Redis (1h) + PostgreSQL (90d) + Supabase (permanente) | `docs/arquitetura/context-engineering.md` |
| **RAG / Recuperação** | PostgreSQL filtrado + Supabase por telefone + Open-Meteo por GPS + AwesomeAPI | `logs/execucao-exemplo.json` |
| **Dados Estruturados** | 15 tabelas com constraints, índices, views e funções SQL | `data/schema.md` |
| **API Externa Real** | Open-Meteo (clima por GPS) + AwesomeAPI/BCB (USD/BRL) | `docs/evidencias/` |
| **Orquestração Autônoma** | Schedule 8h seg–sáb sem input humano | `docs/evidencias/execucoes-reais.md` |
| **Classificação de Risco** | Score composto 0-100 com 5 fatores ponderados, 4 níveis | `docs/arquitetura/score-risco.md` |
| **Resposta Estruturada** | JSON + Email HTML + WhatsApp + Google Calendar | `docs/evidencias/` |
| **Logs e Rastreabilidade** | 4 tabelas de audit trail + relatórios rastreáveis | `logs/` |
| **Tratamento de Erros** | continueOnFail em todos os nós + sanitizador de resposta | `docs/arquitetura/seguranca.md` |
| **Segurança / Anti-Injection** | Anti-injection nos 7 prompts + RLS Supabase + $vars | `docs/arquitetura/seguranca.md` |
| **Inteligência Comercial** | 4 tipos de oportunidade: preço, clima, expansão, retenção | `docs/arquitetura/comercial.md` |

---

## Score de Risco Composto

```
Score = Documental (max 40) + Chamados (max 20) + Histórico (15) + Câmbio (15) + Clima (10)

Documental:   vencido=40 | 0-7d=35 | 8-30d=25 | indefinido=20 | >30d=0
Chamados:     7pts por chamado crítico aberto (max 20)
Histórico:    histórico_atrasos=true → +15pts
Câmbio:       exposição crítica=15 | alta=8 | média=3
Climático:    >100mm precipitação=10 | >60mm=7 | moderado=5

CRÍTICO > 80  |  ALTO 60-79  |  MÉDIO 40-59  |  BAIXO < 40
```

---

## Fontes de Dados

### Internas (banco de dados)
| Tabela | Conteúdo | Registros |
|--------|----------|-----------|
| `agroe_operacoes` | Fazendas, produtores, coordenadas GPS, exposição cambial | 5 |
| `agroe_documentos` | Documentos com status, vencimento, órgão emissor | 8 |
| `agroe_chamados` | Chamados operacionais abertos | 6 |
| `agroe_clientes` | Perfil comercial dos produtores | 7 |
| `agroe_historico_comercial` | Transações históricas por cliente | 16 |
| `agroe_catalogo_produtos` | Produtos com variação de preço atual | 8 |
| `agroe_regioes_estrategicas` | Mapa competitivo regional | 7 |
| `agroe_concorrentes` | Concorrentes com pontos fortes/fracos | 4 |

### Externas (APIs públicas reais)
| API | Dados | Autenticação |
|-----|-------|-------------|
| Open-Meteo | Clima por coordenada GPS, previsão 5 dias | Pública, sem chave |
| AwesomeAPI/BCB | USD/BRL em tempo real | Pública, sem chave |

---

## Evidências de Funcionamento

Ver pasta `docs/evidencias/`:

- **Execuções reais:** prints de execuções com sucesso no n8n
- **WhatsApp:** mensagem real recebida e respondida em produção
- **Email de gestão:** HTML completo gerado automaticamente
- **Banco de dados:** registros reais acumulados (28 mensagens de memória conversacional)
- **Logs:** JSON completo de execução com fontes consultadas e alertas gerados

---

## Stack

| Componente | Tecnologia |
|-----------|-----------|
| Orquestração | n8n self-hosted |
| LLM | GPT-4.1-mini (OpenAI) |
| Banco de Dados | Supabase (PostgreSQL) |
| Memória rápida | Redis |
| WhatsApp | Evolution API |
| Email | Gmail OAuth2 |
| Calendário | Google Calendar OAuth2 |
| APIs externas | Open-Meteo + AwesomeAPI/BCB |

---

## Dados Simulados

A pasta `data/` contém os dados simulados utilizados para demonstração. Em produção, estas tabelas são substituídas pelos dados reais do ERP/CRM da empresa — a arquitetura permanece idêntica.

---

## Sobre

**Desenvolvido por:** Andre Fernandes — Airion  
**Versão:** agro-e v1.0 — Maio 2026  
**Status:** Em operação real

> Este repositório contém documentação, dados simulados, logs de execução e evidências de funcionamento do sistema agro-e. A implementação interna (workflows, prompts e lógica de score) é propriedade do autor e está disponível mediante licenciamento ou contrato de implementação.

---

*© 2026 Andre Fernandes. Disponibilizado para fins de avaliação técnica.*
