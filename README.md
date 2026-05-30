<div align="center">

<img src="https://raw.githubusercontent.com/airionntelligentsystems/Agro-e/main/evidencias/assets/logo_t.png" alt="AGRO-e Intelligence" width="320"/>

<br/>

<img src="https://img.shields.io/badge/Status-Em%20Produção-1a472a?style=for-the-badge"/>
<img src="https://img.shields.io/badge/n8n-6%20Workflows%20·%20244%20Nós-ea4b71?style=for-the-badge&logo=n8n&logoColor=white"/>
<img src="https://img.shields.io/badge/LLM-GPT--4.1--mini-412991?style=for-the-badge&logo=openai&logoColor=white"/>
<img src="https://img.shields.io/badge/Banco-Supabase%20%2B%20PostgreSQL-3ecf8e?style=for-the-badge&logo=supabase&logoColor=white"/>
<img src="https://img.shields.io/badge/El%20Niño%202026-82%25%20CHANCE-f59e0b?style=for-the-badge"/>
<img src="https://img.shields.io/badge/LGPD-Compliant-0ea5e9?style=for-the-badge"/>

<br/><br/>

# AGRO-e Intelligence
### Monitoramento Autônomo de Riscos, Oportunidades e Inteligência Comercial para o Agronegócio

**Sistema multi-agente de IA em operação real — monitora documentos, clima, El Niño, câmbio e oportunidades comerciais de forma completamente autônoma, 24/7, com entrega via WhatsApp e email.**

<br/>

[📋 Relatório de Evidências](https://htmlpreview.github.io/?https://raw.githubusercontent.com/airionntelligentsystems/Agro-e/main/evidencias/agroe-evidencias.html) &nbsp;•&nbsp; [📄 Documentação Técnica](evidencias/agroe-documentacao-tecnica-comercial-_maio26.pdf) &nbsp;•&nbsp; [🖼️ Evidências em PDF](evidencias/agroe-evidencias.pdf)

</div>

---

## Índice de Navegação

| # | Seção |
|---|---|
| 1 | [O Problema que Este Sistema Resolve](#-o-problema-que-este-sistema-resolve) |
| 2 | [Evidências de Funcionamento em Produção](#-evidências-de-funcionamento-em-produção) |
| **3** | [**🌊 El Niño 2026 — O Grande Diferencial**](#-el-niño-2026--o-grande-diferencial-da-plataforma) |
| 4 | [AGRO-e V2 — O Que Está Sendo Construído](#-agro-e-v2--o-que-está-sendo-construído) |
| 5 | [Todas as Capacidades — Visão Rápida](#-todas-as-capacidades--visão-rápida) |
| 6 | [Como o Sistema Opera](#-como-o-sistema-opera) |
| 7 | [Arquitetura — 6 Workflows, 244 Nós](#-arquitetura--6-workflows-244-nós) |
| 8 | [Funcionalidades Detalhadas](#-funcionalidades-detalhadas--como-e-quando-cada-uma-opera) |
| 9 | [Stack Tecnológico](#-stack-tecnológico) |
| 10 | [Proteção de Dados — LGPD](#-proteção-de-dados--lgpd) |
| 11 | [Roadmap V2](#-roadmap-v2) |
| 12 | [Evidências — Arquivos](#-evidências) |

---

## 🌱 O Problema que Este Sistema Resolve

Empresas do agronegócio com carteiras de 50–500 produtores enfrentam um problema estrutural silencioso: **informação crítica se perde entre planilhas, sistemas desconectados e comunicação manual.**

O custo não é a falta de dados — é a falta de inteligência sobre os dados. Um documento vencido bloqueia operações (R$50k–500k+ por incidente). Uma oportunidade de preço favorável expira sem contato. Um risco climático não monitorado compromete safras inteiras. **E agora, com o El Niño 2026 confirmado com 82% de probabilidade, quem não se preparar antes vai correr atrás depois.**

---

## 📸 Evidências de Funcionamento em Produção

> Sistema em produção real, atendendo mensagens via WhatsApp com respostas reais. Evidências capturadas em **29/05/2026**.

👉 **[Acessar Relatório de Evidências](https://htmlpreview.github.io/?https://raw.githubusercontent.com/airionntelligentsystems/Agro-e/main/evidencias/agroe-evidencias.html)**

| Indicador | Resultado |
|---|---|
| Execuções bem-sucedidas (29/05/2026) | **20+ · 100% success rate** |
| Latência P50 ponta-a-ponta | **7 segundos** (WhatsApp → IA → Resposta) |
| Oportunidades mapeadas em ciclo único | **14 oportunidades** |
| Receita potencial identificada | **R$ 1.562.000+** |
| Workflows ativos em produção | **6 workflows · 244 nós** |

---

## 🌊 El Niño 2026 — O Grande Diferencial da Plataforma

> **Esta é a cereja do sistema.** Nenhum concorrente está monitorando El Niño em tempo real e cruzando com a carteira de clientes, o estoque e as oportunidades comerciais. Quem tem o AGRO-e compra em março o que vai faltar em setembro.

### O Cenário — Dados Oficiais NOAA/INMET/CPTEC

O Centro de Previsão Climática da NOAA confirmou em **14 de maio de 2026**:

| Probabilidade | Período | Status NOAA |
|---|---|---|
| **82%** | Maio–Julho 2026 | 🟡 **EL NIÑO WATCH** |
| **90%+** | Agosto–Outubro 2026 | 🔴 Formação confirmada |
| **96%** | Dezembro 2026–Fevereiro 2027 | 🔴 Persistência garantida |

**ONI atual (Niño 3.4 SST): +0.47°C e subindo.** Próximo boletim NOAA: 11 de junho de 2026.

---

### Como o AGRO-e Monitora El Niño — Detalhamento Técnico

#### 📡 Fontes de Dados em Tempo Real

| Fonte | Dados | Frequência |
|---|---|---|
| **NOAA/CPC ENSO API** | ONI index, probabilidades mensais, categorização | Diária |
| **INMET API** | Temperatura superficial do mar (TSM), desvios regionais | Diária |
| **CPTEC/INPE** | Previsões sazonais por bioma, Zarc climático | Semanal |
| **Open-Meteo GPS** | Precipitação e temperatura por coordenada de cada fazenda | Horária |
| **AwesomeAPI** | Câmbio USD/BRL (insumos importados sob pressão cambial) | Em tempo real |

#### 🎯 Lógica de Classificação por Nível de Alerta

O sistema cruza o ONI atual com o mapa regional e classifica cada produtor da carteira:

```
ONI < +0.5°C  →  NEUTRO    — Monitoramento padrão
ONI ≥ +0.5°C  →  EL NIÑO FRACO   — Alertas preventivos
ONI ≥ +1.0°C  →  EL NIÑO MODERADO — Alertas urgentes
ONI ≥ +1.5°C  →  EL NIÑO FORTE   — Alertas críticos + escalada humana
```

Para cada produtor, o score composto de risco 0–100 **recebe um multiplicador El Niño** com base na:
- Região onde opera (Sul, Cerrado, Nordeste, Sudeste)
- Cultura cultivada (soja, milho, trigo, cana, pecuária)
- Vulnerabilidade histórica (dados CONAB por cultura × El Niño anterior)
- Posição no calendário agrícola (fase de plantio, desenvolvimento ou colheita)

---

### 🗺️ Impactos por Região — O Que o Sistema Monitora

#### 🟢 Região Sul (RS · SC · PR)
**El Niño = excesso de chuva e risco de enchente**

| Alerta | Situação | Ação Recomendada pelo Sistema |
|---|---|---|
| 🔴 CRÍTICO | Precipitação > 100mm/3 dias | Alerta imediato + comunicar produtor |
| 🟠 ALTO | 60–100mm · Risco de colheita perdida | Antecipar logística de colheita |
| 🟡 MODERADO | Chuvas irregulares · Plantio tardio | Ajustar janela de semeadura |
| 🟢 POSITIVO | Pastagens e reservatórios favorecidos | Oportunidade de expansão pecuária |

**Insumos estratégicos para estocar antes do pico (Ago–Nov):**
- Fungicidas (doenças fúngicas explodem com umidade) → escassez prevista
- Tratamento de sementes → demanda 3x acima do normal
- Drenagem e terraços → produto com alta demanda antecipada

#### 🟡 Cerrado · Matopiba (GO · MT · MS · MA · PI)
**El Niño = veranico (seca temporária) e janela de plantio mais curta**

| Alerta | Situação | Ação |
|---|---|---|
| 🟠 ALTO | Seca 14+ dias · Culturas de sequeiro em risco | Antecipar irrigação |
| 🟡 MODERADO | Janela de plantio reduzida | Sementes de ciclo curto prioritárias |
| 🟢 POSITIVO | Câmbio alta + preços de grãos sobem | Antecipar compra de fertilizantes agora |

**Janela de oportunidade:** MAP e Ureia com queda de -7.8% agora, mas câmbio subindo = comprar imediatamente antes de recuperação de preço.

#### 🔴 Nordeste · Norte (CE · PI · MA · PA · AM)
**El Niño = seca severa no 2º semestre**

| Alerta | Situação | Ação |
|---|---|---|
| 🔴 CRÍTICO | Seca prolongada · Lavoura de sequeiro em colapso | Escalada para responsável humano |
| 🔴 CRÍTICO | Pecuária: silagem e forragem esgotadas | Antecipar contratação de forragem |
| 🟠 ALTO | Reservatórios em nível crítico | Sistemas de captação e armazenamento d'água |

**Escassez prevista de insumos:** sistemas de irrigação, bombas, caixas d'água → comprar antes de julho para não enfrentar falta de produto e preço inflacionado.

---

### 💰 Como El Niño Vira Oportunidade Comercial

O sistema cruza automaticamente os alertas climáticos com o catálogo de produtos e histórico de compras de cada cliente:

```
ALERTA: Seca prevista Cerrado por 14 dias
+ HISTÓRICO: Carlos Mendes comprou bomba de irrigação em 2023
+ CATÁLOGO: Sistema gotejamento disponível, margem 38%
+ CONCORRENTE: AgroMinas sem estoque de irrigação
= OPORTUNIDADE: Abordagem urgente com proposta de gotejamento para Carlos Mendes
  Receita potencial: R$48.000 | Urgência: Esta semana | Concorrente: vulnerável
```

**A empresa que usa o AGRO-e sabe o que vai faltar antes de faltar. Isso é vantagem competitiva real.**

---

## 🚀 AGRO-e V2 — O Que Está Sendo Construído

> As funcionalidades abaixo estão em desenvolvimento ativo. A arquitetura V1 em produção comprova que a base técnica está correta — o V2 é a evolução natural.

### Preview do Dashboard CRM V2

![AGRO-e Intelligence · Dashboard CRM V2 Preview](https://raw.githubusercontent.com/airionntelligentsystems/Agro-e/main/assets/dashboard-v2-preview.png)

*Preview do dashboard CRM — El Niño Monitor, Score de Risco em Tempo Real, Radar de Oportunidades, Timeline Proativo, WhatsApp integrado.*

---

### Novas Funcionalidades V2

| Funcionalidade | Descrição | Status |
|---|---|---|
| 🌊 **Monitor El Niño NOAA/INMET** | ONI index real-time, alertas por região/cultura, multiplicador de risco | 🔨 Em construção |
| 🖥️ **CRM Dashboard Web** | Interface completa React/Next.js com autenticação e dados em tempo real | 🔨 Em construção |
| 📊 **Análise de Risco Visual** | Gauge de score 0–100, mapa de calor por região, histórico de risco | 🔨 Em construção |
| 🎯 **Radar de Oportunidades** | Gráfico polar + lista priorizada com receita potencial e urgência El Niño | 🔨 Em construção |
| 📦 **Recomendador de Estoque** | Sugere o que comprar/ampliar antes do pico El Niño por região | 🔨 Em construção |
| 🔔 **Alertas Push Multicanal** | Notificações WhatsApp + Email + Dashboard simultaneamente | 🔨 Em construção |
| 🧠 **RAG Semântico** | pgvector + Supabase para busca em contratos e documentos históricos | 📋 Planejado |
| 🏢 **Multi-Tenant** | Isolamento completo de dados entre clientes — SaaS ready | 📋 Planejado |
| 📈 **Score Learning** | Feedback loop: gestores validam alertas e ajustam pesos automaticamente | 📋 Planejado |
| 📱 **App Mobile** | Dashboard responsivo + notificações push para campo | 📋 Planejado |

---

## ⚡ Todas as Capacidades — Visão Rápida

O sistema possui **17 capacidades funcionais**. As marcadas com ★ são diferenciais multimodais ou estratégicos únicos.

| # | Capacidade | Tecnologia | Quando Ativa |
|---|---|---|---|
| ★ 1 | **🌊 Monitor El Niño NOAA/CPTEC** | ENSO API + Multiplicador de risco | Diariamente no ciclo proativo 8h |
| ★ 2 | **📦 Recomendação de Estoque Estratégico** | El Niño + Catálogo + Escassez prevista | Proativo + consulta reativa |
| ★ 3 | **🎙️ Áudio — Transcrição Automática** | OpenAI Whisper | Ao receber mensagem de voz |
| ★ 4 | **📄 Documentos — Leitura e Análise** | PDF Extract + Context Injection | Ao receber PDF/documento |
| ★ 5 | **🖼️ Imagens — Visão Computacional** | OpenAI Vision | Ao receber foto/imagem |
| 6 | 📱 WhatsApp Bidirecional Reativo | Evolution API + Redis | Ao receber qualquer mensagem |
| 7 | ⏰ Monitor Proativo Autônomo | Cron 8h seg–sáb | Automaticamente, 7 fontes |
| 8 | 🏗️ Motor de Inteligência Comercial | SQL + JS Engine 4 tipos | Ciclo proativo + consulta |
| 9 | 📋 Agente Analista Documental | Score 0–40pts + WF04 | Proativo + documentos |
| 10 | 🌧️ Agente Monitor Climático | Open-Meteo por GPS | Proativo + consulta regional |
| 11 | 💱 Agente Analista de Câmbio | AwesomeAPI USD/BRL | Proativo + consulta financeira |
| 12 | 📊 Score Composto de Risco 0–100 | 5 fatores ponderados | Ciclo proativo 8h |
| 13 | 📧 Email Real via Gmail API | Gmail OAuth2 + Tool Calling | Proativo 9h + solicitação |
| 14 | 📅 Alertas Google Calendar | Google Calendar OAuth2 | Solicitação reativa |
| 15 | 🧠 Memória Conversacional | Redis + Postgres + Supabase | Em toda interação |
| 16 | 📊 Relatórios de Gestão BI | WF05 + Supabase REST | Automaticamente às 9h |
| 17 | 👤 Onboarding Zero-Touch | Auto-register Supabase | Primeira mensagem |
| 18 | 🔁 Escalada HITL | WF03 + Context Handoff | Score >85 ou crítico |
| 19 | 🔌 Integração CRM/ERP Universal | WF06 + 5 conectores | Passivamente, todo evento |

---

## 🔄 Como o Sistema Opera

### Modo Proativo — Autônomo (8h)
**Cron:** `0 8 * * 1-6` — sem intervenção humana

```
08:00 → 7 fontes simultâneas: Postgres + Supabase + NOAA ENSO + Open-Meteo + AwesomeAPI
08:03 → Score composto + Multiplicador El Niño por cliente e região
08:05 → 5 sub-agentes: Documental, Climático, Câmbio, Proativo, Comercial
08:15 → WhatsApp + Email HTML executivo → Relatório salvo no Supabase
```

### Modo Reativo — Conversacional
**Quando:** Mensagem no WhatsApp — **texto, áudio, imagem ou documento**

O operador pergunta. O sistema responde com análise contextualizada, dados em tempo real, El Niño integrado e memória das interações anteriores. Latência P50: 7 segundos.

---

## 🏗️ Arquitetura — 6 Workflows, 244 Nós

```
┌──────────────────────────────────────────────────────────────────────────┐
│             WF01 — ENTRADA + MONITOR PROATIVO (133 nós)                  │
│  REATIVO:  WhatsApp → Evolution API → Normalizador Universal → WF02      │
│            └─ Texto · 🎙️ Áudio (Whisper) · 🖼️ Imagem (Vision) · 📄 PDF  │
│                                                                           │
│  PROATIVO: Schedule 8h → 7 fontes simultâneas → WF02                    │
│            └─ PostgreSQL · Supabase · NOAA ENSO · Open-Meteo · AwesAPI  │
└───────────────────────────────┬──────────────────────────────────────────┘
                                │
┌───────────────────────────────▼──────────────────────────────────────────┐
│             WF02 — CONSOLE MULTI-AGENTES (31 nós)                        │
│                                                                           │
│  🤖 Agente Roteador (GPT-4.1-mini · Postgres Chat Memory)                │
│  ├── 🤔 Think Tool × 2        (raciocínio explícito e auditável)         │
│  ├── 🌊 agente_elnino_monitor        → NOAA ENSO + impacto por região   │
│  ├── 📋 agente_analista_documental   → score 0–40pts                     │
│  ├── 🌦️  agente_monitor_climatico    → Open-Meteo por GPS                │
│  ├── 💱 agente_analista_cambio       → AwesomeAPI USD/BRL                │
│  ├── 📊 agente_monitoramento_autonomo → score composto 0–100             │
│  ├── 🏪 agente_inteligencia_comercial → 4 tipos + El Niño opportunities  │
│  ├── 📅 Google Calendar × 3 tools    → alertas automáticos              │
│  └── 🆘 encaminhar_responsavel_humano → WF03                             │
└──────────┬──────────────┬───────────────┬───────────────┬────────────────┘
           │              │               │               │
    ┌──────▼──────┐ ┌─────▼──────┐ ┌─────▼──────┐ ┌─────▼──────┐
    │    WF03     │ │    WF04    │ │    WF05    │ │    WF06    │
    │  Escalada   │ │Vencimentos │ │ Relatório  │ │  CRM/ERP   │
    │   13 nós    │ │  48 nós    │ │   8 nós    │ │   11 nós   │
    └─────────────┘ └────────────┘ └────────────┘ └────────────┘
```

---

## 📖 Funcionalidades Detalhadas — Como e Quando Cada Uma Opera

---

### 🌊 Monitor El Niño NOAA/CPTEC — Em Tempo Real

**Como funciona:**
1. O sistema consulta diariamente a NOAA/CPC ENSO API e obtém o ONI (Oceanic Niño Index) atualizado — o índice oficial de temperatura superficial do mar na região Niño 3.4 (5°N–5°S, 170°W–120°W)
2. Cruza o ONI com o mapa regional de impacto do El Niño no Brasil (baseado em dados históricos CONAB e CPTEC)
3. Para cada cliente da carteira, calcula um **multiplicador de risco El Niño** com base em: região, cultura cultivada, fase do calendário agrícola e vulnerabilidade histórica
4. Identifica oportunidades de estoque estratégico: produtos que terão escassez ou alta de preço durante o pico do fenômeno
5. Classifica alertas em quatro níveis com ações específicas para cada um

**Classificação de alertas:**
```
🔴 CRÍTICO  — Ação imediata. Escalada para responsável humano se necessário.
              Ex: Seca severa Nordeste, enchente Sul na colheita
🟠 ALTO     — Esta semana. Abordagem ao produtor com proposta preventiva.
              Ex: Veranico Cerrado, janela de plantio se fechando
🟡 MODERADO — Este mês. Planejamento e posicionamento de estoque.
              Ex: Variação cambial + insumos importados, chuvas irregulares
🟢 POSITIVO — Oportunidade. El Niño favorece produtividade nesta região/cultura.
              Ex: Pastagens sul, reservatórios Centro-Oeste, exportação grãos
```

**Estratégias que o sistema recomenda automaticamente:**

| Região | Alerta El Niño | Estratégia Recomendada | Urgência |
|---|---|---|---|
| Sul | Excesso chuva | Estocar fungicidas agora — escassez prevista Jul/Ago | CRÍTICO |
| Sul | Colheita em risco | Antecipar logística de colheita e secagem | ALTO |
| Cerrado | Veranico Jan/Fev | Proposta irrigação gotejamento antes de Dez | ALTO |
| Cerrado | Janela plantio curta | Sementes ciclo curto: comprar agora, vender depois | MODERADO |
| Nordeste | Seca severa | Irrigação e forragem: janela antes de Jul fecha logo | CRÍTICO |
| Nordeste | Pecuária risco | Contratos antecipados de silagem e reserva hídrica | CRÍTICO |

**Quando ativa:** Diariamente no ciclo proativo das 8h (WF07) e em toda consulta reativa sobre clima, região ou estoque.

---

### 📦 Recomendação de Estoque Estratégico

**Como funciona:** O sistema cruza os alertas El Niño com o catálogo de produtos disponíveis e o histórico de compras de cada cliente. Identifica produtos que terão escassez ou aumento de preço durante o pico do fenômeno e gera recomendações específicas de: o que comprar, quanto, quando e para qual cliente.

**Quando ativa:** No ciclo proativo 8h e em qualquer consulta sobre estoque, previsão de demanda ou planejamento comercial.

---

### 🎙️ Processamento de Áudio (ASR)

**Como funciona:** Download do áudio via Evolution API, decodificação OGG/Opus, transcrição com OpenAI Whisper. O texto entra no pipeline normalmente.

**Quando ativa:** Ao receber mensagem de voz no WhatsApp. Transparente para o operador.

---

### 📄 Leitura de Documentos (IDP)

**Como funciona:** PDFs enviados via WhatsApp são interceptados pelo Normalizador Universal. Texto extraído, armazenado no contexto de sessão e analisado pelo agente — contratos, laudos, licenças ambientais, certificados.

**Quando ativa:** Ao receber qualquer PDF ou documento no WhatsApp.

---

### 🖼️ Visão Computacional

**Como funciona:** Imagens enviadas (fotos de lavoura, pragas, documentos fotografados) são analisadas pelo OpenAI Vision. A análise é incorporada à resposta do agente.

**Quando ativa:** Ao receber qualquer imagem no WhatsApp.

---

### ⏰ Monitor Proativo Autônomo (8h)

**Como funciona:** `cron: 0 8 * * 1-6` — fan-out paralelo de 7 fontes: PostgreSQL, Supabase (5 tabelas), **NOAA ENSO**, Open-Meteo por GPS, AwesomeAPI. Score composto + multiplicador El Niño + 14 oportunidades. Relatório executivo WhatsApp + email.

**Quando ativa:** Automaticamente às 8h, todo dia útil. Zero intervenção humana.

---

### 🏗️ Motor de Inteligência Comercial

**4 tipos de oportunidade:**
- **Preço Favorável:** produto que o cliente já comprou caiu >3%
- **Antecipação Climática:** clima adverso + cultivo sensível + produto relevante (integrado com El Niño)
- **Expansão Estratégica:** região com baixa presença + ponto fraco do concorrente
- **Risco de Churn:** >120 dias sem compra + El Niño pode acelerar migração

**Quando ativa:** Ciclo proativo 8h e consulta reativa sobre oportunidades.

---

### 📋 Agente Analista Documental

**Score:** Vencido=40pts · ≤7d=35pts · ≤30d=25pts · ≤60d=15pts → CRÍTICO/ALTO/MÉDIO/BAIXO

**Quando ativa:** Proativo 8h + WF04 (7h urgentes / 12h próximos) + consulta reativa.

---

### 🌧️ Agente Monitor Climático

**Thresholds:** >60mm/3d → ALTO · >100mm → CRÍTICO · temp <5°C → geada · seca >7d → ALTO

**Quando ativa:** Proativo 8h e consulta por região.

---

### 💱 Agente Analista de Câmbio

**Thresholds:** >1.5% variação → ALERTA · >2.5% → CRÍTICO · alta >5 dias → hedge recomendado

**Quando ativa:** Proativo 8h e consulta financeira.

---

### 📊 Score Composto de Risco 0–100 com Multiplicador El Niño

| Fator | Critério | Pontuação |
|---|---|---|
| Documental | Vencido=40 · ≤7d=35 · ≤30d=25 | Máx 40pts |
| Chamados abertos | 7pts por chamado crítico | Máx 20pts |
| Histórico de atrasos | `historico_atrasos=true` | 15pts fixos |
| Exposição cambial | Crítica=15 · Alta=8 · Média=3 | Máx 15pts |
| Risco climático | >100mm=10 · >60mm=7 | Máx 10pts |
| **Multiplicador El Niño** | **Região × Cultura × ONI × Fase agrícola** | **+0–30%** |

**Classificação:** CRÍTICO >80 · ALTO 60–79 · MÉDIO 40–59 · BAIXO <40

**Quando ativa:** Ciclo proativo 8h.

---

### 📧 Email Real (Gmail OAuth2) · 📅 Google Calendar · 🧠 Memória 3 Camadas

Descritos em detalhe na documentação técnica. Todos funcionam em produção.

---

### 📊 Relatórios de Gestão (WF05)

**9h todo dia útil:** Email HTML executivo + flash WhatsApp de 5 linhas. Rastreabilidade: `pendente → em_andamento → resolvido`.

---

## 🖥️ Stack Tecnológico

| Componente | Tecnologia | Função |
|---|---|---|
| Orquestração | n8n self-hosted | 6 workflows, 244 nós |
| LLM / IA | GPT-4.1-mini (OpenAI) | Motor de análise multi-agente |
| ASR | OpenAI Whisper | Transcrição de áudios |
| Vision | OpenAI Vision | Análise de imagens |
| ENSO Monitor | NOAA/CPC + INMET + CPTEC APIs | El Niño em tempo real |
| Banco de Dados | Supabase + PostgreSQL | 15 tabelas, RLS, views |
| Memória Rápida | Redis (TTL 1h) | Debounce + sessão ativa |
| WhatsApp | Evolution API | Bidirecional multimodal |
| Email | Gmail OAuth2 | Relatórios executivos |
| Calendário | Google Calendar OAuth2 | Alertas automáticos |
| Clima | Open-Meteo API (gratuita) | GPS por região da carteira |
| Câmbio | AwesomeAPI / BCB (gratuita) | USD/BRL real-time |
| Proteção | RLS + Audit Trail + LGPD | Conformidade total |

---

## 🔒 Proteção de Dados — LGPD

| Medida | Implementação | Base Legal |
|---|---|---|
| Row Level Security | RLS em todas as tabelas Supabase | Art. 46 LGPD |
| Anonimização SQL | `agroe_anonimiza_telefone()` e `agroe_anonimiza_nome()` | Art. 12 LGPD |
| Retenção mínima | Chat: 90d · Logs: 180d · Execuções: 365d | Art. 15 LGPD |
| Audit Trail | `agroe_lgpd_acesso_log` — todas as operações com dados pessoais | Art. 37 LGPD |

---

## 🗺️ Roadmap V2

| Fase | Período | Entrega |
|---|---|---|
| **🔨 Fase 1** — El Niño Monitor | Jun–Jul 2026 | WF07 com NOAA ENSO API + multiplicador de risco + recomendador de estoque |
| **🔨 Fase 2** — CRM Dashboard | Jul–Ago 2026 | Frontend React/Next.js — risk dashboard, oportunidades, mapa El Niño |
| **📋 Fase 3** — RAG Semântico | Ago–Set 2026 | pgvector + busca em contratos e documentos históricos |
| **📋 Fase 4** — Multi-Tenant SaaS | Set–Nov 2026 | Isolamento de dados, billing, API REST, múltiplos clientes |
| **📋 Fase 5** — Score Learning | Nov 2026 | Feedback loop — gestores validam alertas, pesos ajustados por ML |

---

## 🗂️ Evidências

| Arquivo | Descrição |
|---|---|
| [Relatório HTML Interativo](https://htmlpreview.github.io/?https://raw.githubusercontent.com/airionntelligentsystems/Agro-e/main/evidencias/agroe-evidencias.html) | Página completa — prints, emails, log, motor comercial |
| [Relatório PDF](evidencias/agroe-evidencias.pdf) | Versão PDF do relatório |
| [Documentação Técnica e Comercial](evidencias/agroe-documentacao-tecnica-comercial-_maio26.pdf) | 11 páginas — produto completo |
| [Dashboard V2 Preview](assets/dashboard-v2-preview.png) | Mockup do CRM frontend com El Niño Monitor |
| [Assets](evidencias/assets/) | Screenshots reais: WhatsApp, emails, diagrama, logo |

---

<div align="center">

**AGRO-e Intelligence** · Monitoramento Autônomo de Riscos e Inteligência Comercial para o Agronegócio Brasileiro

André Fernandes · Maio 2026

*Em operação real · Pronto para produção · El Niño 2026 monitorado · Escalável e extensível · IP protegido*

</div>
