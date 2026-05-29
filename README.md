<div align="center">

<img src="https://raw.githubusercontent.com/airionntelligentsystems/Agro-e/main/evidencias/assets/logo_t.png" alt="AGRO-e Intelligence" width="320"/>

<br/>

<img src="https://img.shields.io/badge/Status-Em%20Produção-1a472a?style=for-the-badge"/>
<img src="https://img.shields.io/badge/n8n-6%20Workflows%20·%20244%20Nós-ea4b71?style=for-the-badge&logo=n8n&logoColor=white"/>
<img src="https://img.shields.io/badge/LLM-GPT--4.1--mini-412991?style=for-the-badge&logo=openai&logoColor=white"/>
<img src="https://img.shields.io/badge/Banco-Supabase%20%2B%20PostgreSQL-3ecf8e?style=for-the-badge&logo=supabase&logoColor=white"/>
<img src="https://img.shields.io/badge/LGPD-Compliant-0ea5e9?style=for-the-badge"/>

<br/><br/>

# AGRO-e Intelligence
### Monitoramento Autônomo de Riscos, Oportunidades e Inteligência Comercial para o Agronegócio

**Sistema multi-agente de IA em operação real — monitora documentos, clima, câmbio e oportunidades comerciais de forma completamente autônoma, 24/7, com entrega via WhatsApp e email.**

<br/>

[📋 Relatório de Evidências](https://htmlpreview.github.io/?https://raw.githubusercontent.com/airionntelligentsystems/Agro-e/main/evidencias/agroe-evidencias.html) &nbsp;•&nbsp; [📄 Documentação Técnica](evidencias/agroe-documentacao-tecnica-comercial-_maio26.pdf) &nbsp;•&nbsp; [🖼️ Evidências em PDF](evidencias/agroe-evidencias.pdf)

</div>

---

## O Problema que Este Sistema Resolve

Empresas do agronegócio com carteiras de 50–500 produtores enfrentam um problema estrutural silencioso: **informação crítica se perde entre planilhas, sistemas desconectados e comunicação manual.**

O custo não é a falta de dados — é a falta de inteligência sobre os dados. Um documento vencido que bloqueia uma operação pode custar R$50k–500k+. Uma oportunidade de preço favorável que expira sem contato pode ser a diferença entre fechar ou perder um cliente. Um risco cambial não monitorado pode corroer margens de forma silenciosa.

**O agro-e age antes que o problema vire perda.** Opera como um analista sênior permanente — coleta dados de 7 fontes, cruza informações, calcula scores de risco, identifica oportunidades comerciais e entrega análise via WhatsApp e email — tudo de forma completamente autônoma, todo dia útil, às 8h da manhã.

---

## Evidências de Funcionamento em Produção

> Este sistema está em produção real, atendendo mensagens via WhatsApp com respostas reais. As evidências abaixo foram capturadas durante sessão de validação em **29/05/2026**.

### 📋 Relatório Completo de Evidências

O relatório interativo inclui: prints reais do WhatsApp, emails entregues na caixa de entrada, log de execuções n8n, diagrama de arquitetura em operação e motor comercial com oportunidades calculadas em tempo real.

👉 **[Acessar Relatório de Evidências](https://htmlpreview.github.io/?https://raw.githubusercontent.com/airionntelligentsystems/Agro-e/main/evidencias/agroe-evidencias.html)**

| Indicador | Resultado |
|---|---|
| Execuções bem-sucedidas (29/05/2026) | **20+ · 100% success rate** |
| Latência P50 ponta-a-ponta | **7 segundos** (WhatsApp → IA → Resposta) |
| Oportunidades mapeadas em ciclo único | **14 oportunidades** |
| Receita potencial identificada | **R$ 1.562.000+** |
| Workflows ativos em produção | **6 workflows · 244 nós** |
| Sub-agentes especializados | **5 sub-agentes** |

---

## Como o Sistema Opera

O agro-e funciona em dois modos simultâneos, complementares e independentes:

### Modo Proativo — Autônomo
**Quando:** Todo dia útil às 8h, sem nenhum input humano. Cron: `0 8 * * 1-6`

O sistema acorda, coleta dados de 7 fontes em paralelo, analisa toda a carteira de clientes, calcula scores de risco, identifica oportunidades comerciais e entrega relatório executivo via WhatsApp + email antes do início do expediente.

### Modo Reativo — Conversacional
**Quando:** Sempre que o operador envia mensagem no WhatsApp — texto, áudio, imagem ou documento.

O operador pergunta, o sistema responde com análise contextualizada usando histórico da conversa, dados em tempo real e memória de interações anteriores. Latência P50: 7 segundos.

---

## Arquitetura — 6 Workflows, 244 Nós

```
┌─────────────────────────────────────────────────────────────────────────┐
│              WF01 — ENTRADA + MONITOR PROATIVO (133 nós)                │
│  REATIVO:  WhatsApp → Evolution API → Normalizador → Redis → WF02       │
│  PROATIVO: Schedule 8h → 7 fontes simultâneas → WF02                    │
│            └─ PostgreSQL · Supabase · Open-Meteo GPS · AwesomeAPI       │
└───────────────────────────────┬─────────────────────────────────────────┘
                                │
┌───────────────────────────────▼─────────────────────────────────────────┐
│              WF02 — CONSOLE MULTI-AGENTES (31 nós)                      │
│                                                                          │
│  🤖 Agente Roteador (GPT-4.1-mini · Postgres Chat Memory)               │
│  ├── 🤔 Think Tool × 2        (raciocínio explícito antes de agir)      │
│  ├── 📋 agente_analista_documental   → score 0–40pts                    │
│  ├── 🌦️  agente_monitor_climatico    → Open-Meteo por GPS               │
│  ├── 💱 agente_analista_cambio       → AwesomeAPI USD/BRL               │
│  ├── 📊 agente_monitoramento_autonomo → score composto 0–100            │
│  ├── 🏪 agente_inteligencia_comercial → 4 tipos de oportunidade         │
│  ├── 📅 Google Calendar × 3 tools    → alertas automáticos             │
│  └── 🆘 encaminhar_responsavel_humano → WF03                            │
└──────────┬──────────────┬───────────────┬──────────────────────────────┘
           │              │               │
    ┌──────▼──────┐ ┌─────▼──────┐ ┌─────▼──────┐ ┌─────────────┐
    │    WF03     │ │    WF04    │ │    WF05    │ │    WF06     │
    │  Escalada   │ │Vencimentos │ │ Relatório  │ │  CRM / ERP  │
    │   13 nós    │ │  48 nós    │ │   8 nós    │ │   11 nós    │
    └─────────────┘ └────────────┘ └────────────┘ └─────────────┘
```

---

## Funcionalidades Detalhadas — Como e Quando Cada Uma Opera

### 🎙️ Processamento de Áudio (ASR)
**Como funciona:** O operador envia uma mensagem de voz pelo WhatsApp. O sistema baixa o arquivo de áudio via Evolution API, decodifica o formato OGG/Opus e transcreve o conteúdo com OpenAI Whisper. O texto transcrito entra no pipeline de processamento normalmente — o agente recebe e responde como se fosse uma mensagem de texto.

**Quando ativa:** A qualquer momento em que o operador enviar um áudio no WhatsApp. Transparente para o usuário.

---

### 📄 Leitura de Documentos (IDP)
**Como funciona:** PDFs e documentos enviados pelo WhatsApp são interceptados pelo Normalizador Universal. O sistema extrai o texto do documento, armazena no contexto de sessão e disponibiliza ao agente para análise semântica. Contratos, laudos técnicos, licenças ambientais e certificados fitossanitários são processados sem configuração adicional.

**Quando ativa:** Sempre que um PDF ou documento for enviado via WhatsApp pelo operador.

---

### 🖼️ Visão Computacional
**Como funciona:** Imagens enviadas pelo WhatsApp (fotos de lavoura, registros de pragas, documentos fotografados) são processadas pelo modelo OpenAI Vision. O sistema descreve e interpreta o conteúdo visual e incorpora a análise na resposta do agente.

**Quando ativa:** Sempre que uma imagem for enviada via WhatsApp pelo operador.

---

### 📱 WhatsApp Bidirecional Reativo
**Como funciona:** Webhook persistente recebe mensagens da Evolution API. O Normalizador Universal identifica automaticamente se a origem é Evolution, UAZAPI ou ZAPI — sem configuração manual. Redis aplica debounce em mensagens fracionadas. O sistema deduplica por event ID para garantia de entrega exactly-once.

**Quando ativa:** Imediatamente ao receber qualquer mensagem no WhatsApp conectado. Latência P50: 7 segundos fim-a-fim.

---

### ⏰ Monitor Proativo Autônomo (8h)
**Como funciona:** Schedule Trigger executa automaticamente de segunda a sábado às 8h (`cron: 0 8 * * 1-6`). O sistema dispara fan-out paralelo para 7 fontes de dados: PostgreSQL (operações e documentos), Supabase (clientes, catálogo, histórico comercial, regiões estratégicas, concorrentes), Open-Meteo por GPS de cada região e AwesomeAPI para câmbio USD/BRL em tempo real. Os dados são consolidados, o score composto é calculado e o relatório executivo é entregue via WhatsApp + email.

**Quando ativa:** Automaticamente às 8h, todo dia útil. Zero intervenção humana.

---

### 🏗️ Motor de Inteligência Comercial
**Como funciona:** Uma única query SQL com `COALESCE` + `json_agg` retorna 5 datasets em uma roundtrip ao PostgreSQL. Um engine JavaScript processa os dados em memória em menos de 50ms e classifica 4 tipos de oportunidade:
- **Preço Favorável:** produto que o cliente já comprou caiu mais de 3% — acionar com oferta antecipada
- **Antecipação Climática:** clima adverso previsto + cultivo sensível + produto relevante no histórico
- **Expansão Estratégica:** região com baixa presença da empresa + ponto fraco identificado do concorrente
- **Risco de Churn:** cliente sem compra há mais de 120 dias com potencial de perda para concorrente

**Quando ativa:** Em todo ciclo proativo (8h) e em toda consulta reativa que mencione oportunidades comerciais.

---

### 📋 Agente Analista Documental
**Como funciona:** Sub-agente especializado em documentos agrícolas. Calcula score por documento com base na proximidade do vencimento:
- Vencido = 40 pontos (CRÍTICO)
- Vence em ≤7 dias = 35 pontos (ALTO)
- Vence em ≤30 dias = 25 pontos (MÉDIO)
- Vence em ≤60 dias = 15 pontos (BAIXO)

Monitora: licenças ambientais, certificados fitossanitários, ART, CAR, registros SEAPDR e outros documentos agrícolas.

**Quando ativa:** (1) No ciclo proativo das 8h para toda a carteira. (2) No WF04 em dois turnos: 7h para urgentes e 12h para próximos. (3) Em qualquer conversa reativa que mencione licenças, registros ou certificados.

---

### 🌧️ Agente Monitor Climático
**Como funciona:** Consulta Open-Meteo API usando as coordenadas GPS de cada região da carteira de clientes. Avalia precipitação acumulada, temperatura mínima e período de seca. Thresholds:
- Precipitação > 60mm em 3 dias → risco ALTO
- Precipitação > 100mm em 3 dias → risco CRÍTICO
- Temperatura mínima < 5°C → risco de geada
- Seca > 7 dias consecutivos → risco ALTO

O resultado é integrado ao score composto de risco e às estratégias de oportunidades comerciais (ex: recomendar sistema de irrigação em período de seca).

**Quando ativa:** No ciclo proativo das 8h e em qualquer pergunta sobre clima ou risco por região.

---

### 💱 Agente Analista de Câmbio
**Como funciona:** Consulta AwesomeAPI (dados do Banco Central do Brasil) para obter a cotação USD/BRL em tempo real. Avalia variação e tendência:
- Variação > 1.5% em 24h → ALERTA
- Variação > 2.5% em 24h → CRÍTICO
- Alta por mais de 5 dias consecutivos → recomendação de hedge cambial

O impacto cambial é integrado às propostas de insumos importados (fertilizantes, defensivos) e aos contratos de exportação.

**Quando ativa:** No ciclo proativo das 8h e em qualquer pergunta sobre câmbio, preço de insumos ou exposição financeira.

---

### 📊 Agente de Monitoramento Proativo (Score Composto 0–100)
**Como funciona:** Consolida os dados de todos os outros agentes em um score único por cliente/região. O score é calculado com 5 fatores ponderados:

| Fator | Critério | Pontuação |
|---|---|---|
| Documental | Vencido=40 · ≤7d=35 · ≤30d=25 · ≤60d=15 | Máx 40pts |
| Chamados abertos | 7pts por chamado crítico | Máx 20pts |
| Histórico de atrasos | Flag `historico_atrasos=true` | 15pts fixos |
| Exposição cambial | Crítica=15 · Alta=8 · Média=3 | Máx 15pts |
| Risco climático | >100mm=10 · >60mm=7 · Moderado=5 | Máx 10pts |

Classificação: **CRÍTICO** >80 · **ALTO** 60–79 · **MÉDIO** 40–59 · **BAIXO** <40

**Quando ativa:** Exclusivamente no ciclo proativo das 8h. Gera o relatório executivo completo com todos os alertas classificados por criticidade.

---

### 📧 Envio de Email Real (Gmail API)
**Como funciona:** Gmail Tool integrada ao agente roteador via OAuth2 com escopo `gmail.send`. O modelo GPT-4.1-mini decide autonomamente quando acionar o envio com base no contexto — quando o operador pede "envie por email" ou quando o ciclo proativo gera relatório. O email é composto pelo próprio agente com formatação adequada para gestores.

**Quando ativa:** (1) No ciclo proativo das 8h — email executivo enviado automaticamente. (2) No modo reativo — quando o operador solicitar explicitamente.

---

### 📅 Alertas no Google Calendar
**Como funciona:** Três Calendar Tools disponíveis ao agente: `create_event`, `update_event` e `cancel_event`. O agente cria eventos no calendário do operador para vencimentos documentais, visitas a clientes e marcos operacionais com base na análise de riscos.

**Quando ativa:** No modo reativo, quando o operador solicitar criar alertas, ou quando o agente identificar situação que justifique um lembrete calendário.

---

### 🧠 Memória Conversacional Persistente — 3 Camadas
**Como funciona:** O sistema mantém contexto em três camadas com durações diferentes:

| Camada | Tecnologia | Duração | O que armazena |
|---|---|---|---|
| Curto Prazo | Redis · TTL 1h | 1 hora | Contexto ativo da sessão. Debounce e idempotência. |
| Médio Prazo | PostgreSQL | 90 dias | Histórico conversacional por operador. Recuperado antes de cada análise. |
| Longo Prazo | Supabase | Permanente | Perfil do produtor, resumo de contexto, histórico de execuções. |

**Quando ativa:** Em toda interação. O agente recupera o histórico antes de responder — reconhece nome, email e contexto de sessões anteriores sem re-identificação.

---

### 📊 Relatórios de Gestão e Rastreabilidade (WF05)
**Como funciona:** Às 9h de cada dia útil, o WF05 busca todos os itens pendentes no Supabase e constrói um email HTML executivo completo com: cards de resumo (críticos, altos, médios, oportunidades, SLA vencido), cartões detalhados por item com ação recomendada e tabela completa. Paralelamente, envia flash executivo de 5 linhas via WhatsApp. Cada item tem rastreabilidade completa: `pendente → em_andamento → resolvido`.

**Quando ativa:** Automaticamente às 9h todo dia útil. Independente do ciclo proativo das 8h.

---

### 👤 Onboarding Zero-Touch
**Como funciona:** Quando um número de telefone ainda não cadastrado envia mensagem no WhatsApp, o sistema automaticamente cria o registro em `agroe_contexto` com `ai_service='active'`. Nenhuma configuração manual necessária — o sistema está operacional desde a primeira mensagem recebida.

**Quando ativa:** Na primeira interação de qualquer novo número de telefone.

---

### 🔁 Escalada para Humano — Human-in-the-Loop (WF03)
**Como funciona:** Quando o agente identifica score > 85, embargo documental, produtor irresponsivo há mais de 10 dias, ou o operador solicita explicitamente, o WF03 é acionado: a IA é pausada para aquele número (`ai_service=pause`), o responsável humano é notificado via WhatsApp com contexto completo, e a retomada é automática quando o status voltar para `active`. Compatível com Evolution API, UAZAPI e ZAPI.

**Quando ativa:** Por decisão autônoma do agente (score >85 ou situação crítica) ou por solicitação explícita do operador.

---

### 🔌 Integração CRM/ERP Universal (WF06)
**Como funciona:** Camada de integração com schema padronizado que conecta o agro-e a qualquer CRM ou ERP sem reescrever a lógica do agente. 5 conectores pré-configurados prontos para ativação:

| Conector | Tipo | Para Ativar |
|---|---|---|
| Salesforce | CRM | Definir `SALESFORCE_CLIENT_ID` e `CLIENT_SECRET` |
| HubSpot | CRM | Definir `HUBSPOT_API_KEY` |
| Siagri | ERP Agro | Definir `SIAGRI_API_KEY` e `SIAGRI_EMPRESA_ID` |
| TOTVS Agri | ERP | Definir `TOTVS_CLIENT_ID` e `CLIENT_SECRET` |
| AgroSmart | BI Agro | Definir `AGROSMART_API_KEY` |
| Webhook Genérico | Qualquer | Definir `CUSTOM_WEBHOOK_URL` — já ativo |

**Quando ativa:** Passivamente — todo evento gerado (alerta, oportunidade, atualização) é normalizado e enviado ao CRM/ERP configurado.

---

## Stack Tecnológico

| Componente | Tecnologia | Função |
|---|---|---|
| Orquestração | n8n self-hosted | 6 workflows, 244 nós — coordena todo o fluxo |
| LLM / IA | GPT-4.1-mini (OpenAI) | Motor de análise de todos os 5 sub-agentes |
| ASR | OpenAI Whisper | Transcrição de áudios enviados pelo WhatsApp |
| Vision | OpenAI Vision | Análise de imagens enviadas pelo WhatsApp |
| Banco de Dados | Supabase + PostgreSQL | 15 tabelas, RLS, views, funções — persistência e contexto |
| Memória Rápida | Redis (TTL 1h) | Contexto de curto prazo + debounce de sessão |
| WhatsApp | Evolution API | Recebimento e envio de mensagens |
| Email | Gmail OAuth2 | Relatórios de gestão e notificações |
| Calendário | Google Calendar OAuth2 | Criação de alertas e lembretes |
| Clima | Open-Meteo API (gratuita) | Dados climáticos por coordenada GPS |
| Câmbio | AwesomeAPI / BCB (gratuita) | USD/BRL em tempo real |
| Proteção LGPD | RLS + Anonimização + Audit Trail | Conformidade com Lei nº 13.709/2018 |

---

## Proteção de Dados — LGPD

| Medida | Implementação | Base Legal |
|---|---|---|
| Row Level Security | RLS em todas as tabelas com dados pessoais no Supabase | Art. 46 LGPD |
| Anonimização SQL | Funções `agroe_anonimiza_telefone()` e `agroe_anonimiza_nome()` | Art. 12 LGPD |
| Retenção mínima | Chat: 90d · Logs: 180d · Execuções: 365d — limpeza automática | Art. 15 LGPD |
| Audit Trail | `agroe_lgpd_acesso_log` registra todas as operações com dados pessoais | Art. 37 LGPD |
| Consentimento | Tabela `agroe_lgpd_consentimento` com base legal e finalidade por titular | Art. 7 LGPD |

---

## Técnicas de IA Implementadas — Nível Avançado

| Técnica | Implementação |
|---|---|
| Engenharia de Prompt | 7 system prompts distintos por agente com papel, objetivo, escopo, anti-hallucination e proteção anti-injection |
| Context Engineering | 3 camadas: fixo (system prompts), dinâmico curto (Redis TTL 1h) e longo prazo (Supabase) |
| RAG / Recuperação | PostgreSQL queries filtradas, Supabase por telefone, Redis por sessão, Open-Meteo por GPS, AwesomeAPI real-time |
| Dados Estruturados | 15 tabelas com índices, constraints CHECK, foreign keys, views e funções SQL |
| Orquestração Autônoma | Schedule 8h seg–sáb: executa sem input. Agente decide subagentes, ordem e canais de saída autonomamente |
| Classificação de Risco | Score composto 0–100 com 5 fatores ponderados. 4 níveis de risco. 4 tipos de oportunidade comercial |
| Rastreabilidade | `agroe_historico_execucoes` (audit trail), `agroe_relatorios_gestao` (itens rastreáveis) |
| Tratamento de Erros | `continueOnFail` em todos os nós HTTP. Fallback para APIs. Sanitizador de resposta WhatsApp |
| Segurança | Anti-injection nos 7 system prompts. Credenciais via n8n nativo. RLS no Supabase. `$vars` para secrets |

---

## Roadmap

| Fase | Período | Entrega |
|---|---|---|
| **Fase 1** — Dados Reais | Meses 1–2 | Conectar ERP/CRM real, calibrar scores com histórico operacional, configurar WhatsApp de produção |
| **Fase 2** — RAG Semântico | Meses 2–3 | `pgvector` no Supabase para busca em contratos e documentos históricos. Perguntas em linguagem natural |
| **Fase 3** — Aprendizado Contínuo | Meses 3–4 | Feedback loop: gestores validam alertas, ajustando pesos do score automaticamente por região e cultivo |
| **Fase 4** — Dashboard + Multi-Tenant | Meses 4–6 | Dashboard web em tempo real, API REST, suporte a múltiplas empresas com isolamento completo de dados |

---

## Evidências

| Arquivo | Descrição |
|---|---|
| [Relatório HTML Interativo](https://htmlpreview.github.io/?https://raw.githubusercontent.com/airionntelligentsystems/Agro-e/main/evidencias/agroe-evidencias.html) | Página completa com prints, emails, log de execuções e motor comercial |
| [Relatório PDF](evidencias/agroe-evidencias.pdf) | Versão PDF do relatório de evidências |
| [Documentação Técnica e Comercial](evidencias/agroe-documentacao-tecnica-comercial-_maio26.pdf) | Documentação completa — 11 páginas |
| [Assets de Evidências](evidencias/assets/) | Screenshots reais: WhatsApp, emails, diagrama de arquitetura, logo |

---

<div align="center">

**AGRO-e Intelligence** · Monitoramento Autônomo de Riscos e Inteligência Comercial para o Agronegócio Brasileiro

André Fernandes · Maio 2026

*Em operação real · Pronto para produção · Escalável e extensível · IP protegido*

</div>
