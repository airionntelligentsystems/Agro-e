<div align="center">

<img src="https://raw.githubusercontent.com/airionntelligentsystems/Agro-e/main/evidencias/assets/logo_t.png" alt="AGRO-e Intelligence" width="320"/>

<br/>

<img src="https://img.shields.io/badge/Status-Em%20Produção-1a472a?style=for-the-badge"/>
<img src="https://img.shields.io/badge/n8n-6%20Workflows%20·%20244%20Nós-ea4b71?style=for-the-badge&logo=n8n&logoColor=white"/>
<img src="https://img.shields.io/badge/LLM-GPT--4.1--mini-412991?style=for-the-badge&logo=openai&logoColor=white"/>
<img src="https://img.shields.io/badge/Banco-Supabase%20%2B%20PostgreSQL-3ecf8e?style=for-the-badge&logo=supabase&logoColor=white"/>
<img src="https://img.shields.io/badge/El%20Niño%202026-90%25%20Confirmado-f59e0b?style=for-the-badge"/>
<img src="https://img.shields.io/badge/LGPD-Compliant-0ea5e9?style=for-the-badge"/>

<br/><br/>

# AGRO-e Intelligence
### Monitoramento Autônomo de Riscos, Oportunidades e Inteligência Comercial

**Plataforma de IA em operação real. Monitora documentos, El Niño, câmbio e preços de insumos de forma autônoma — entrega análise acionável via WhatsApp e email, antes que o problema vire perda.**

<br/>

[📋 Evidências de Funcionamento](https://htmlpreview.github.io/?https://raw.githubusercontent.com/airionntelligentsystems/Agro-e/main/evidencias/agroe-evidencias.html) &nbsp;•&nbsp; [📄 Documentação Técnica](evidencias/agroe-documentacao-tecnica-comercial-_maio26.pdf) &nbsp;•&nbsp; [🖼️ Relatório PDF](evidencias/agroe-evidencias.pdf)

</div>

---

## Índice de Navegação

| # | Seção |
|---|---|
| 1 | [O Problema que Este Sistema Resolve](#-o-problema-que-este-sistema-resolve) |
| 2 | [Evidências de Funcionamento em Produção](#-evidências-de-funcionamento-em-produção) |
| **3** | [**🌊 El Niño 2026 — Monitoramento e Inteligência Estratégica**](#-el-niño-2026--monitoramento-e-inteligência-estratégica) |
| 4 | [CRM · Painel de Controle](#-crm--painel-de-controle) |
| 5 | [Todas as Capacidades](#-todas-as-capacidades) |
| 6 | [Como o Sistema Opera](#-como-o-sistema-opera) |
| 7 | [Arquitetura — 6 Workflows, 244 Nós](#-arquitetura--6-workflows-244-nós) |
| 8 | [Funcionalidades Detalhadas](#-funcionalidades-detalhadas) |
| 9 | [Stack Tecnológico](#-stack-tecnológico) |
| 10 | [Proteção de Dados — LGPD](#-proteção-de-dados--lgpd) |
| 11 | [Roadmap](#-roadmap) |
| 12 | [Arquivos de Evidência](#-arquivos-de-evidência) |

---

## 🌱 O Problema que Este Sistema Resolve

Empresas do agronegócio com carteiras de 50 a 500 produtores operam com um risco estrutural que nenhuma planilha resolve: **informação crítica chega tarde, quando o dano já está feito.**

Um documento vencido bloqueia uma operação e custa entre R$50 mil e R$500 mil por incidente. Uma janela de preço favorável em fertilizante importado fecha em 48 horas — enquanto o câmbio deteriora. Um produtor de soja no Cerrado planta na época errada porque ninguém cruzou o dado climático com a janela agrícola. E com o El Niño 2026 confirmado com **90%+ de probabilidade a partir de agosto**, quem não se posicionou antes vai competir por insumos em falta com preços inflacionados.

**O AGRO-e opera como um analista permanente.** Coleta 7 fontes de dados em paralelo, cruza com a carteira de clientes, calcula score de risco e entrega análise acionável — todo dia útil, às 8h, sem intervenção humana. A empresa que usa o AGRO-e adquire em março o que vai faltar em setembro.

---

## 📸 Evidências de Funcionamento em Produção

> Sistema validado em ambiente de produção real. Todas as evidências foram capturadas em **29/05/2026** sem edição ou simulação.

👉 **[Acessar Relatório Completo de Evidências](https://htmlpreview.github.io/?https://raw.githubusercontent.com/airionntelligentsystems/Agro-e/main/evidencias/agroe-evidencias.html)**

| Indicador | Resultado |
|---|---|
| Execuções validadas em 29/05/2026 | **20+ execuções · 100% success rate** |
| Latência P50 ponta-a-ponta | **7 segundos** (WhatsApp → IA → Resposta) |
| Oportunidades mapeadas em ciclo único | **14 oportunidades identificadas** |
| Receita potencial em um ciclo de análise | **R$ 1.562.000+** |
| Workflows ativos em produção | **6 workflows · 244 nós** |
| Sub-agentes especializados | **5 sub-agentes** |

---

## 🌊 El Niño 2026 — Monitoramento e Inteligência Estratégica

O AGRO-e monitora o El Niño em tempo real, cruzando os índices climáticos oficiais com a carteira de clientes, o histórico de compras, os preços de insumos e a cotação do câmbio. O resultado não é apenas um alerta — é uma recomendação comercial específica com janela de ação.

### Dados Oficiais — NOAA/CPC · INMET · CPTEC

| Probabilidade | Período | Status Oficial |
|---|---|---|
| **82%** | Maio–Julho 2026 | 🟡 **El Niño Watch** (NOAA, 14/05/2026) |
| **90%+** | Agosto–Outubro 2026 | 🔴 Formação confirmada pelos modelos |
| **96%** | Dezembro 2026–Fevereiro 2027 | 🔴 Persistência garantida |

**ONI atual (Niño 3.4 SST): +0.47°C e subindo.** Próximo boletim NOAA: 11 de junho de 2026.

---

### Como o Sistema Integra El Niño + Câmbio + Preços de Insumos

O monitoramento climático isolado não gera valor comercial. O AGRO-e cruza três dimensões simultaneamente:

```
NOAA ENSO (ONI index)          →  intensidade e probabilidade do fenômeno
Open-Meteo por GPS da fazenda  →  impacto localizado por região e cultura
AwesomeAPI / BCB (USD/BRL)     →  pressão cambial sobre insumos importados
Catálogo de preços (Supabase)  →  janela atual de oportunidade por produto
Histórico de compras (Postgres) →  perfil do cliente e necessidade real
```

**O sistema identifica automaticamente:**

- Produtos que terão escassez durante o pico do El Niño, com janela de compra antecipada
- Clientes vulneráveis por região e cultura — com score de risco atualizado diariamente
- Oportunidades de antecipação: insumos em queda de preço + câmbio subindo = janela crítica
- Recomendação de estoque estratégico por produto, com urgência e receita potencial

---

### Impactos por Região — O Que o Sistema Monitora e Recomenda

#### 🔴 Região Sul (RS · SC · PR) — Excesso de Chuva

| Alerta | Situação | Ação Gerada pelo Sistema |
|---|---|---|
| CRÍTICO | Precipitação >100mm em 3 dias | Alerta imediato ao produtor + notificação ao operador |
| ALTO | 60–100mm · Colheita em risco | Antecipar logística; proposta de seguro agrícola |
| ESTOQUE | Fungicidas com escassez prevista Jul–Set | Comprar agora enquanto preço está favorável |

#### 🟠 Cerrado · Matopiba (GO · MT · MS) — Veranico e Câmbio

| Alerta | Situação | Ação Gerada pelo Sistema |
|---|---|---|
| ALTO | Veranico Jan–Fev · janela de plantio reduzida | Proposta de irrigação gotejamento (demanda explosiva) |
| ALTO | MAP/Ureia em queda + câmbio subindo | Janela de 48–72h para compra antecipada com margem |
| MODERADO | Câmbio +1.8%/24h · fertilizantes importados | Alerta cambial + projeção de impacto por cliente |

#### 🔴 Nordeste · Norte (CE · PI · MA · PA) — Seca Severa

| Alerta | Situação | Ação Gerada pelo Sistema |
|---|---|---|
| CRÍTICO | Seca prolongada 2º semestre | Escalada para responsável humano |
| CRÍTICO | Pecuária: silagem esgotada antes do fim do ano | Janela de contratação de forragem fecha em julho |
| ALTO | Bombas e cisternas em escassez prevista | Estoque estratégico antes do pico de demanda |

---

### Monitoramento de Preços de Insumos — Integrado ao El Niño e Câmbio

O sistema monitora o catálogo de preços em tempo real e cruza com o contexto El Niño:

| Insumo | Variação Atual | Contexto El Niño + Câmbio | Recomendação |
|---|---|---|---|
| MAP Fertilizante | −7.8% | Câmbio +1.8%/24h · reversão iminente | **Comprar imediatamente** |
| KCL Cloreto Potássio | −7.0% | Demanda Cerrado vai subir com irrigação | **Comprar esta semana** |
| Glifosato 480 SC | −9.2% | Preço mínimo do ciclo | **Oportunidade imediata** |
| Ureia Granulada | −5.7% | Câmbio sobe → preço sobe | **Janela: 48–72h** |
| Fungicida Elatus | +10.4% ⚠ | Escassez prevista Sul · El Niño | **Estocar antes de julho** |
| Sistema Gotejamento | +12% ⚠ | Demanda vai explodir Jul–Ago | **Proposta antecipada** |

> **A empresa que usa o AGRO-e fecha negócio em março com o insumo que vai faltar em setembro.** Isso não é análise retrospectiva — é posicionamento estratégico com dados em tempo real.

---

## 🖥️ CRM · Painel de Controle

Interface web completa com dashboards em tempo real — monitor El Niño, score de risco por cliente, radar de oportunidades, cotação de câmbio e preços de insumos integrados.

![AGRO-e Intelligence · CRM Dashboard — El Niño Monitor, Score de Risco, Radar de Oportunidades](https://raw.githubusercontent.com/airionntelligentsystems/Agro-e/main/assets/dashboard-crm-preview.png)

*Painel de controle com monitor El Niño (ONI gauge em tempo real), score de risco composto por cliente, radar de oportunidades com preços de insumos, câmbio USD/BRL e timeline de execução autônoma.*

---

## ⚡ Todas as Capacidades

| # | Capacidade | Tecnologia | Quando Ativa |
|---|---|---|---|
| ★ 1 | **🌊 Monitor El Niño · NOAA/CPTEC** | ENSO API + score multiplier | Diariamente · ciclo proativo 8h |
| ★ 2 | **📦 Estoque Estratégico · Escassez Prevista** | El Niño + catálogo + câmbio | Proativo + consulta reativa |
| ★ 3 | **💱 Câmbio USD/BRL · Impacto Insumos** | AwesomeAPI/BCB real-time | Contínuo · alerta >1.5% |
| ★ 4 | **🎙️ Áudio — Transcrição por Voz** | OpenAI Whisper | Ao receber mensagem de voz |
| ★ 5 | **📄 Documentos — Leitura e Análise** | PDF Extract + Injeção de Contexto | Ao receber PDF/documento |
| ★ 6 | **🖼️ Imagens — Visão Computacional** | OpenAI Vision | Ao receber foto/imagem |
| 7 | 📱 WhatsApp Bidirecional | Evolution API + Redis | Ao receber qualquer mensagem |
| 8 | ⏰ Monitor Proativo Autônomo | Cron 8h seg–sáb | Automaticamente · 7 fontes |
| 9 | 🏗️ Motor de Inteligência Comercial | SQL + JS Engine · 4 tipos | Ciclo proativo + consulta |
| 10 | 📋 Agente Analista Documental | Score 0–40pts · WF04 | Proativo + menção documentos |
| 11 | 🌧️ Agente Monitor Climático | Open-Meteo por GPS | Proativo + consulta regional |
| 12 | 📊 Score Composto de Risco 0–100 | 5 fatores + multiplicador El Niño | Ciclo proativo 8h |
| 13 | 📧 Email Real via Gmail API | Gmail OAuth2 + Tool Calling | Proativo 9h + solicitação |
| 14 | 📅 Alertas Google Calendar | Google Calendar OAuth2 | Solicitação reativa |
| 15 | 🧠 Memória Conversacional | Redis + PostgreSQL + Supabase | Em toda interação |
| 16 | 📊 Relatórios Executivos BI | WF05 + Supabase REST | Automaticamente às 9h |
| 17 | 👤 Onboarding Zero-Touch | Auto-register Supabase | Primeira mensagem |
| 18 | 🔁 Escalada Humana HITL | WF03 + Context Handoff | Score >85 ou situação crítica |
| 19 | 🔌 Integração CRM/ERP Universal | WF06 + 5 conectores | Passivamente · todo evento |

---

## 🔄 Como o Sistema Opera

### Modo Proativo — Autônomo (8h)
`cron: 0 8 * * 1-6` — zero intervenção humana

```
08:00 → Fan-out paralelo: Postgres + Supabase + NOAA ENSO + Open-Meteo + AwesomeAPI/BCB
08:03 → Score composto + multiplicador El Niño + análise de câmbio + preços insumos
08:05 → 5 sub-agentes: Documental, Climático, Câmbio, Proativo, Comercial
08:15 → WhatsApp + Email HTML executivo + Relatório salvo no Supabase
```

### Modo Reativo — Conversacional
Texto · áudio · imagem · documento — qualquer mídia enviada pelo WhatsApp. Latência P50: 7 segundos.

---

## 🏗️ Arquitetura — 6 Workflows, 244 Nós

```
┌──────────────────────────────────────────────────────────────────────────┐
│             WF01 — ENTRADA + MONITOR PROATIVO (133 nós)                  │
│  REATIVO:  WhatsApp → Evolution API → Normalizador Universal → WF02      │
│            └─ Texto · Áudio (Whisper) · Imagem (Vision) · PDF (Extract)  │
│                                                                           │
│  PROATIVO: Schedule 8h → 7 fontes simultâneas → WF02                    │
│            └─ PostgreSQL · Supabase · NOAA ENSO · Open-Meteo · AwesAPI  │
└───────────────────────────────┬──────────────────────────────────────────┘
                                │
┌───────────────────────────────▼──────────────────────────────────────────┐
│             WF02 — CONSOLE MULTI-AGENTES (31 nós)                        │
│                                                                           │
│  Agente Roteador (GPT-4.1-mini · Postgres Chat Memory)                   │
│  ├── Think Tool × 2          (raciocínio explícito e auditável)          │
│  ├── agente_elnino_monitor       → NOAA ENSO + câmbio + preços insumos  │
│  ├── agente_analista_documental  → score 0–40pts                         │
│  ├── agente_monitor_climatico    → Open-Meteo por GPS                    │
│  ├── agente_analista_cambio      → AwesomeAPI USD/BRL                    │
│  ├── agente_monitoramento_autonomo → score composto 0–100                │
│  ├── agente_inteligencia_comercial → 4 tipos + El Niño opportunities     │
│  ├── Google Calendar × 3 tools   → alertas automáticos                  │
│  └── encaminhar_responsavel_humano → WF03                                │
└──────────┬──────────────┬───────────────┬───────────────┬────────────────┘
           │              │               │               │
    ┌──────▼──────┐ ┌─────▼──────┐ ┌─────▼──────┐ ┌─────▼──────┐
    │    WF03     │ │    WF04    │ │    WF05    │ │    WF06    │
    │  Escalada   │ │Vencimentos │ │ Relatório  │ │  CRM/ERP   │
    │   13 nós    │ │  48 nós    │ │   8 nós    │ │   11 nós   │
    └─────────────┘ └────────────┘ └────────────┘ └────────────┘
```

---

## 📖 Funcionalidades Detalhadas

### 🌊 Monitor El Niño NOAA/CPTEC — Em Tempo Real

**Como funciona:**
1. Consulta diária à NOAA/CPC ENSO API para obter o ONI (Oceanic Niño Index) — índice oficial de temperatura superficial do mar
2. Cruza com previsões do INMET e CPTEC para impacto regional por bioma
3. Para cada cliente da carteira, calcula multiplicador de risco El Niño com base em: região, cultura cultivada, fase agrícola e vulnerabilidade histórica
4. Integra com cotação USD/BRL em tempo real para calcular impacto nos preços de insumos importados
5. Gera recomendações específicas de estoque estratégico com janela de ação e receita potencial

**Classificação de alertas:**
```
CRÍTICO  — Ação imediata. Escalada para responsável humano se necessário.
ALTO     — Esta semana. Abordagem ao produtor com proposta preventiva.
MODERADO — Este mês. Posicionamento de estoque e planejamento.
POSITIVO — El Niño favorece esta região/cultura. Oportunidade de expansão.
```

**Quando ativa:** Diariamente no ciclo proativo 8h e em toda consulta reativa sobre clima, estoque ou câmbio.

---

### 💱 Agente Analista de Câmbio — Integrado ao El Niño

**Como funciona:** Consulta AwesomeAPI (Banco Central do Brasil) para cotação USD/BRL em tempo real. Cruza com o catálogo de insumos importados e calcula impacto por produto:

```
Variação >1.5%/24h → ALERTA: notifica sobre pressão nos fertilizantes importados
Variação >2.5%/24h → CRÍTICO: recomendação de antecipação de compra
Alta >5 dias consecutivos → Recomendação de hedge para exportadores
El Niño + Câmbio subindo → Janela dupla: preço atual baixo vai reverter
```

**Quando ativa:** Ciclo proativo 8h e qualquer consulta financeira ou sobre preços.

---

### 🏗️ Motor de Inteligência Comercial — 4 Tipos de Oportunidade

```
1. Preço Favorável + Câmbio:   insumo caiu >3% mas câmbio sobe → janela se fecha
2. Antecipação Climática:      clima adverso previsto + produto relevante no histórico
3. Expansão Estratégica:       presença baixa + fraqueza do concorrente identificada
4. Risco de Churn:             cliente sem compra >120 dias + El Niño pode acelerar saída
```

---

### 📊 Score Composto de Risco 0–100

| Fator | Critério | Pontuação |
|---|---|---|
| Documental | Vencido=40 · ≤7d=35 · ≤30d=25 | Máx 40pts |
| Chamados abertos | 7pts por chamado crítico | Máx 20pts |
| Histórico de atrasos | `historico_atrasos=true` | 15pts fixos |
| Exposição cambial | Crítica=15 · Alta=8 · Média=3 | Máx 15pts |
| Risco climático | >100mm=10 · >60mm=7 | Máx 10pts |
| **Multiplicador El Niño** | **Região × Cultura × ONI × Fase agrícola** | **+0–30%** |

**Classificação:** CRÍTICO >80 · ALTO 60–79 · MÉDIO 40–59 · BAIXO <40

---

### 🎙️ Áudio · 📄 Documentos · 🖼️ Imagens

O Normalizador Universal do WF01 identifica o tipo de mídia e processa automaticamente:
- **Áudio** → Whisper ASR → texto → pipeline padrão
- **PDF/Documento** → extração de texto → injeção no contexto → análise pelo agente
- **Imagem** → OpenAI Vision → interpretação visual → incorporada à resposta

Nenhuma configuração necessária. Transparente para o operador.

---

## 🖥️ Stack Tecnológico

| Componente | Tecnologia | Função |
|---|---|---|
| Orquestração | n8n self-hosted | 6 workflows · 244 nós |
| LLM / IA | GPT-4.1-mini (OpenAI) | Motor de análise multi-agente |
| ASR | OpenAI Whisper | Transcrição de áudios WhatsApp |
| Vision | OpenAI Vision | Análise de imagens WhatsApp |
| ENSO Monitor | NOAA/CPC + INMET + CPTEC | El Niño em tempo real |
| Câmbio | AwesomeAPI / Banco Central | USD/BRL real-time |
| Banco de Dados | Supabase + PostgreSQL | 15 tabelas · RLS · Views |
| Memória Rápida | Redis (TTL 1h) | Debounce + contexto de sessão |
| WhatsApp | Evolution API | Canal bidirecional multimodal |
| Email | Gmail OAuth2 | Relatórios executivos |
| Calendário | Google Calendar OAuth2 | Alertas automáticos |
| Clima | Open-Meteo API (gratuita) | Dados GPS por região da carteira |

---

## 🔒 Proteção de Dados — LGPD

| Medida | Implementação | Base Legal |
|---|---|---|
| Row Level Security | RLS em todas as tabelas com dados pessoais | Art. 46 LGPD |
| Anonimização SQL | `agroe_anonimiza_telefone()` · `agroe_anonimiza_nome()` | Art. 12 LGPD |
| Retenção mínima | Chat: 90d · Logs: 180d · Execuções: 365d · limpeza automática | Art. 15 LGPD |
| Audit Trail | `agroe_lgpd_acesso_log` — todas as operações com dados pessoais | Art. 37 LGPD |
| Anti-injection | 7 system prompts com proteção contra manipulação | Segurança |

---

## 🗺️ Roadmap

| Fase | Período | Entrega |
|---|---|---|
| **Fase 1** — Dados Reais | Meses 1–2 | Integração ERP/CRM real · calibração de scores com histórico operacional |
| **Fase 2** — RAG Semântico | Meses 2–3 | pgvector + Supabase · busca em contratos e documentos históricos |
| **Fase 3** — Aprendizado Contínuo | Meses 3–4 | Feedback loop · pesos do score ajustados automaticamente por região e cultivo |
| **Fase 4** — Multi-Tenant SaaS | Meses 4–6 | Isolamento de dados · billing · API REST · múltiplas empresas |

---

## 🗂️ Arquivos de Evidência

| Arquivo | Descrição |
|---|---|
| [Relatório HTML Interativo](https://htmlpreview.github.io/?https://raw.githubusercontent.com/airionntelligentsystems/Agro-e/main/evidencias/agroe-evidencias.html) | Evidências completas — prints WhatsApp, emails, log execuções, motor comercial |
| [Relatório PDF](evidencias/agroe-evidencias.pdf) | Versão PDF do relatório de evidências |
| [Documentação Técnica e Comercial](evidencias/agroe-documentacao-tecnica-comercial-_maio26.pdf) | 11 páginas · produto completo |
| [CRM Dashboard Preview](assets/dashboard-crm-preview.png) | Painel de controle com El Niño Monitor e radar de oportunidades |

---

<div align="center">

**AGRO-e Intelligence** · Monitoramento Autônomo de Riscos e Inteligência Comercial para o Agronegócio Brasileiro

André Fernandes · Maio 2026

*Sistema em operação real · Pronto para produção · El Niño 2026 monitorado · Escalável · IP protegido*

</div>
