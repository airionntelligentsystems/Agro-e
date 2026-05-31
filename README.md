<div align="center">

<img src="https://raw.githubusercontent.com/airionntelligentsystems/Agro-e/main/evidencias/assets/logo_t.png" alt="AGRO-e Intelligence" width="300"/>

<br/>

<img src="https://img.shields.io/badge/Status-Em%20Produção-1a472a?style=for-the-badge"/>
<img src="https://img.shields.io/badge/n8n-6%20Workflows%20·%20244%20Nós-ea4b71?style=for-the-badge&logo=n8n&logoColor=white"/>
<img src="https://img.shields.io/badge/Supabase%20%2B%20PostgreSQL%20%2B%20Redis-Persistência%20Multicamada-3ecf8e?style=for-the-badge&logo=supabase&logoColor=white"/>
<img src="https://img.shields.io/badge/El%20Niño%202026-NOAA%2090%25%20Confirmado-f59e0b?style=for-the-badge"/>
<img src="https://img.shields.io/badge/LGPD-Compliant-0ea5e9?style=for-the-badge"/>

<br/><br/>

# AGRO-e Intelligence

### Plataforma Autônoma de Inteligência Operacional, Comercial e Climática para o Agronegócio

**Antecipa riscos, identifica oportunidades e transforma sinais dispersos em decisões acionáveis sem dependência de intervenção humana.**

<br/>

[📋 Evidências em Produção](https://htmlpreview.github.io/?https://raw.githubusercontent.com/airionntelligentsystems/Agro-e/main/evidencias/agroe-evidencias.html) &nbsp;•&nbsp; [📄 Relatório PDF](evidencias/agroe-evidencias.pdf) &nbsp;•&nbsp; [🖥️ CRM Dashboard](assets/dashboard-crm-preview.png)

</div>

---

## Índice

| # | Seção |
|---|---|
| 1 | [Executive Summary](#-executive-summary) |
| 2 | [Capacidades Estratégicas](#-capacidades-estratégicas) |
| 3 | [O Diferencial Mais Forte](#-o-diferencial-mais-forte) |
| 4 | [Por que o AGRO-e é diferente](#-por-que-o-agro-e-é-diferente) |
| 5 | [Como o Sistema Pensa](#-como-o-sistema-pensa) |
| 6 | [Evidências de Funcionamento em Produção](#-evidências-de-funcionamento-em-produção) |
| 7 | [CRM · Painel de Controle](#️-crm--painel-de-controle) |
| 8 | [Arquitetura — 6 Workflows, 244 Nós](#️-arquitetura--6-workflows-244-nós) |
| 9 | [Decisões de Engenharia](#-decisões-de-engenharia) |
| 10 | [Stack Tecnológico](#️-stack-tecnológico) |
| 11 | [Proteção de Dados — LGPD](#-proteção-de-dados--lgpd) |
| 12 | [Roadmap](#-roadmap) |
| 13 | [Evidências — Todos os Arquivos](#-evidências--todos-os-arquivos) |

---

## 📊 Executive Summary

> Dimensão completa do projeto em menos de 30 segundos.

| Dimensão | Resultado |
|---|---|
| **Workflows ativos em produção** | 6 workflows · 244 nós |
| **Sub-agentes especializados** | 5 sub-agentes de IA independentes |
| **Fontes de dados integradas** | 7 fontes simultâneas (PostgreSQL · Supabase · NOAA ENSO · Open-Meteo GPS · AwesomeAPI/BCB · Gmail OAuth2 · Google Calendar OAuth2) |
| **Modos de operação** | Autônomo (schedule 8h, seg–sáb) + Reativo (WhatsApp 24/7) |
| **Multimodalidade** | Texto · Áudio (Whisper ASR) · Imagem (Vision) · Documento (PDF Extract) |
| **Execuções validadas em produção** | 20+ execuções · 100% success rate · 29/05/2026 |
| **Latência P50 ponta-a-ponta** | 7 segundos (WhatsApp → análise → resposta) |
| **Oportunidades mapeadas em ciclo único** | 14 oportunidades identificadas |
| **Receita potencial em um ciclo de análise** | R$ 1.562.000+ |
| **Conformidade** | LGPD · Row Level Security · Audit Trail · Anti-injection |
| **Canais de entrega** | WhatsApp bidirecional · Email HTML · CRM Dashboard |

---

## ✦ Capacidades Estratégicas

As capacidades abaixo foram projetadas para operar de forma integrada e autônoma — sem configuração manual por execução. Cada uma tem escopo definido, dados específicos e entrega acionável.

---

### 1 · Inteligência Climática Operacional

**O que faz:** Monitora condições meteorológicas em tempo real para cada região da carteira de produtores — 24 horas por dia, 7 dias por semana.

**Como funciona:** Open-Meteo API consultada com coordenadas GPS de cada região cadastrada. Atualização horária de cinco variáveis por região: precipitação acumulada (3 e 7 dias), temperatura máxima e mínima, umidade relativa, período de seca acumulada e velocidade do vento. No ciclo das 8h, os dados são consolidados em um score climático regional que alimenta o score composto de risco de cada cliente.

**Impacto operacional:** O operador sabe, antes de qualquer visita, quais regiões estão sob estresse hídrico, risco de enchente ou condições favoráveis a pragas — e recebe recomendação de ação junto com o alerta.

| Variável | Threshold ALTO | Threshold CRÍTICO |
|---|---|---|
| Precipitação acumulada 3d | >60mm | >100mm |
| Temperatura mínima | — | <5°C (geada) |
| Temperatura máxima | — | >38°C (estresse hídrico) |
| Umidade relativa | >90% (fungos) | <30% (incêndio) |
| Período de seca | >7 dias | >14 dias |

---

### 2 · Inteligência Preditiva El Niño 2026/2027

**O que faz:** Monitora o fenômeno El Niño em tempo real via NOAA/CPC ENSO API e aplica um multiplicador de risco ao score composto de cada cliente com base em região, cultura e fase agrícola.

**Como funciona:** Consulta diária ao ONI (Oceanic Niño Index). Cruza com previsões do INMET e CPTEC por bioma brasileiro. Para cada cliente, o sistema calcula um multiplicador que eleva o score de risco em até +30% em cenários críticos. O resultado não é um alerta genérico — é uma recomendação específica de insumo, quantidade e janela de compra antes da escassez.

**Impacto operacional:** A empresa que opera o AGRO-e age em março sobre o que vai faltar em setembro. O concorrente descobre quando já não há produto disponível.

| Probabilidade NOAA | Período | Status (14/05/2026) |
|---|---|---|
| **82%** | Maio–Julho 2026 | 🟡 El Niño Watch |
| **90%+** | Agosto–Outubro 2026 | 🔴 Formação confirmada pelos modelos |
| **96%** | Dezembro 2026–Fevereiro 2027 | 🔴 Persistência garantida |

---

### 3 · Inteligência Cambial e Compras

**O que faz:** Monitora USD/BRL em tempo real e calcula o impacto direto nos preços de cada insumo do catálogo, disparando alertas quando janelas de compra se abrem ou se fecham.

**Como funciona:** AwesomeAPI/Banco Central com polling contínuo. Variação acima de 1.5%/24h aciona alerta de pressão sobre fertilizantes importados. Variação acima de 2.5% aciona CRÍTICO com recomendação de antecipação. Quando câmbio sobe e preço do insumo está em queda simultânea, o sistema identifica automaticamente a janela dupla e gera proposta com prazo.

**Impacto operacional:** A diferença entre agir em 48h e não agir pode ser a diferença entre comprar MAP a R$2.100/t ou a R$2.350/t — na mesma semana.

---

### 4 · Radar de Oportunidades Comerciais

**O que faz:** Identifica oportunidades de venda cruzando preço, clima, câmbio e histórico de compras de cada cliente — sem input humano, a cada ciclo.

**Como funciona:** Motor SQL determinístico em quatro tipos de detecção:

| Tipo | Lógica | Gatilho |
|---|---|---|
| Preço Favorável | Insumo caiu >3% + câmbio sobe | Janela que se fecha em horas |
| Antecipação Climática | Alerta regional ativo + cultivo sensível cadastrado | Proposta com prazo de urgência |
| Expansão Estratégica | Baixa presença + fraqueza de concorrente identificada | El Niño cria momento ideal |
| Risco de Churn | +120 dias sem compra + potencial ALTO | Risco de migração durante crise |

**Impacto operacional:** O operador recebe a lista priorizada de ações comerciais junto com o relatório das 8h — sem pesquisa, sem cruzamento manual.

---

### 5 · Inteligência Documental

**O que faz:** Monitora vencimentos de documentos operacionais e regulatórios de toda a carteira, executado duas vezes ao dia.

**Como funciona:** Score 0–40pts por documento. Documentos de bloqueio operacional (licença ambiental, registro de produtor rural, certificado fitossanitário, aval geológico) recebem classificação CRÍTICO automática. Executa às 7h para urgentes (≤2 dias) e às 12h para proximidades (3–14 dias). Notificação via WhatsApp humanizada por fazenda.

**Impacto operacional:** Elimina o risco de descobrir um documento vencido no momento de uma operação crítica — que pode custar entre R$50k e R$500k por incidente.

---

### 6 · CRM Inteligente

**O que faz:** Consolida histórico de clientes, score de risco, oportunidades e alertas em um painel unificado acessível por todos os times — comercial, compras, financeiro e gestão.

**Como funciona:** Supabase com 15 tabelas, Row Level Security por perfil de acesso e Redis para contexto de sessão. Score composto recalculado diariamente por cliente. Dashboard web com módulos independentes por área funcional.

**Impacto operacional:** Todos os times operam com a mesma visão de risco e oportunidade — sem planilhas paralelas, sem informação fragmentada entre departamentos.

---

### 7 · Orquestração Autônoma

**O que faz:** Executa o ciclo completo de inteligência sem nenhuma intervenção humana — do gatilho ao relatório entregue.

**Como funciona:**

```
Modo Autônomo  ·  cron: 0 8 * * 1-6
  → Fan-out paralelo de 7 fontes simultâneas
  → Consolidação em contexto estruturado único
  → 5 sub-agentes rodando em paralelo
  → Think Tool × 2 para raciocínio auditável
  → WhatsApp + Email HTML + Supabase em um único ciclo
  → Tempo médio de ciclo completo: ~15 minutos

Modo Reativo  ·  WhatsApp 24/7
  → Texto · Áudio (Whisper ASR) · Imagem (Vision) · PDF (Extract)
  → Latência P50: 7 segundos
  → Memória 3 camadas: Redis (1h) · PostgreSQL (90d) · Supabase (permanente)
  → Contexto preservado entre sessões sem re-identificação
```

**Impacto operacional:** O analista de inteligência está ativo antes do expediente começar — todos os dias úteis, sem custo adicional por execução.

---

## ⬡ O Diferencial Mais Forte

O maior diferencial do AGRO-e não está em nenhuma capacidade isolada. Está na **inteligência de correlação** — a capacidade de transformar variáveis independentes em uma recomendação acionável para cada cliente específico.

```
┌─────────────────────────────────────────────────────────────────┐
│                                                                  │
│         CLIMA REGIONAL                                           │
│         Open-Meteo GPS · 5 regiões · Atualização horária        │
│              +                                                   │
│         EL NIÑO 2026                                             │
│         NOAA ENSO API · ONI +0.47°C · 96% confirmado            │
│              +                                                   │
│         CÂMBIO USD/BRL                                           │
│         AwesomeAPI/BCB · Polling contínuo · Alerta >1.5%        │
│              +                                                   │
│         PREÇO DE INSUMOS                                         │
│         Catálogo real · Variação % em tempo real                 │
│              +                                                   │
│         HISTÓRICO COMERCIAL DO CLIENTE                           │
│         PostgreSQL · O que comprou · Quando · Quanto             │
│                                                                  │
│                          ↓                                       │
│                                                                  │
│              RECOMENDAÇÃO DE COMPRA                              │
│     Cliente específico · Produto · Quantidade · Prazo            │
│                                                                  │
│                          ↓                                       │
│                                                                  │
│                PROTEÇÃO DE MARGEM                                │
│       Compra antes da reversão de preço e da escassez            │
│                                                                  │
│                          ↓                                       │
│                                                                  │
│               OPORTUNIDADE COMERCIAL                             │
│    Receita real · Urgência real · Ação antes do concorrente      │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

Este cruzamento não existe de forma automatizada em nenhuma outra plataforma voltada ao agronegócio brasileiro. É o que transforma monitoramento em inteligência operacional.

---

## ⚡ Por que o AGRO-e é diferente

| Monitoramento Tradicional | AGRO-e Intelligence |
|---|---|
| Exibe dados | Interpreta contexto e entrega recomendação acionável |
| Monitora eventos em silos | Correlaciona clima, câmbio, preços e histórico simultaneamente |
| Reage após o fato | Antecipa com base em padrões e fenômenos previstos |
| Depende de análise humana | Produz análise autônoma antes do expediente |
| Variáveis isoladas por sistema | Inteligência contextual multi-dimensional |
| Dashboard que ninguém abre | Canal WhatsApp — onde o operador já está |
| Relatório gerado manualmente | Ciclo autônomo às 8h sem nenhum acionamento humano |
| Sem memória conversacional | 3 camadas de memória — contexto preservado entre sessões |
| Integração pontual e manual | 5 conectores CRM/ERP pré-configurados |
| Alerta genérico por região | Score composto 0–100 por cliente com multiplicador El Niño |

---

## 🧠 Como o Sistema Pensa

Antes da arquitetura técnica, o fluxo de inteligência:

```
┌────────────────────────┐     ┌─────────────────────────┐
│    FONTES INTERNAS     │     │    FONTES EXTERNAS      │
│                        │     │                         │
│  PostgreSQL            │     │  NOAA ENSO API          │
│  Supabase (15 tabelas) │────▶│  Open-Meteo GPS         │
│  Histórico Comercial   │     │  AwesomeAPI / BCB       │
│  Carteira de Clientes  │     │  INMET · CPTEC          │
│  Catálogo de Insumos   │     │                         │
└──────────┬─────────────┘     └────────────┬────────────┘
           │                                │
           └─────────────┬──────────────────┘
                         ↓
           ┌─────────────────────────────┐
           │     MOTOR DE CONTEXTO       │
           │  Score de Risco 0-100       │
           │  Multiplicador El Niño      │
           │  Detecção de Oportunidades  │
           └──────────────┬──────────────┘
                          ↓
           ┌──────────────────────────────────┐
           │     SUBAGENTES ESPECIALIZADOS    │
           │  ├─ Monitor Climático            │
           │  ├─ El Niño / ENSO              │
           │  ├─ Câmbio e Insumos            │
           │  ├─ Analista Documental         │
           │  └─ Inteligência Comercial      │
           └──────────────┬───────────────────┘
                          ↓
     ┌──────────────────────────────────────────────┐
     │               ENGINE DE DECISÃO             │
     │  ✓ Recomendação acionável por cliente       │
     │  ✓ Priorização por urgência e impacto       │
     │  ✓ Rastreabilidade de cada decisão          │
     └─────────────────────────────────────────────┘
                          ↓
        📱 WhatsApp   🖥️ CRM   📧 Email   📊 Relatórios
```

---

## 📸 Evidências de Funcionamento em Produção

> Sistema validado em ambiente de produção real. Capturas realizadas em **29/05/2026**, sem edição ou simulação.

👉 **[Acessar Relatório Completo de Evidências](https://htmlpreview.github.io/?https://raw.githubusercontent.com/airionntelligentsystems/Agro-e/main/evidencias/agroe-evidencias.html)**

### WhatsApp — Canal em Operação Real

| | |
|---|---|
| ![WhatsApp — Análise de Risco Composto](https://raw.githubusercontent.com/airionntelligentsystems/Agro-e/main/evidencias/assets/wpp1.jpeg) | ![WhatsApp — Motor de Inteligência Comercial](https://raw.githubusercontent.com/airionntelligentsystems/Agro-e/main/evidencias/assets/wpp2.jpeg) |
| *Análise de risco composto entregue via WhatsApp em produção real* | *Motor de inteligência comercial — 14 oportunidades identificadas* |
| ![WhatsApp — Ciclo Proativo das 8h](https://raw.githubusercontent.com/airionntelligentsystems/Agro-e/main/evidencias/assets/wpp3.jpeg) | ![WhatsApp — Processamento Multimodal](https://raw.githubusercontent.com/airionntelligentsystems/Agro-e/main/evidencias/assets/wpp4.jpeg) |
| *Ciclo proativo autônomo das 8h — relatório entregue sem intervenção* | *Processamento multimodal — áudio transcrito e respondido em 7s* |

### Email — Relatório Executivo na Inbox

![Relatório Executivo enviado via Gmail OAuth2 — recebido na inbox real](https://raw.githubusercontent.com/airionntelligentsystems/Agro-e/main/evidencias/assets/email3.jpeg)

*Email HTML executivo enviado via Gmail OAuth2 — confirmado na inbox. Envio real, não simulado.*

### Workflows — Arquitetura de Execução

**WF01 · Entrada WhatsApp + Monitor Proativo (133 nós)**

![WF01 — Entrada e Monitor Proativo](https://raw.githubusercontent.com/airionntelligentsystems/Agro-e/main/docs/prints/wf01-entrada-monitor-proativo.svg)

**WF02 · Console Multi-Agentes (31 nós)**

![WF02 — Console Multi-Agentes](https://raw.githubusercontent.com/airionntelligentsystems/Agro-e/main/docs/prints/wf02-console-multiagentes.svg)

**WF03 · Escalada para Humano · WF04 · Monitor Documental · WF05 · Relatório · WF06 · CRM/ERP**

![WF03 — Escalada Humana](https://raw.githubusercontent.com/airionntelligentsystems/Agro-e/main/docs/prints/wf03-escalada-humano.svg)
![WF04 — Monitor de Vencimentos](https://raw.githubusercontent.com/airionntelligentsystems/Agro-e/main/docs/prints/wf04-monitor-vencimentos.svg)
![WF05 — Relatório de Gestão](https://raw.githubusercontent.com/airionntelligentsystems/Agro-e/main/docs/prints/wf05-relatorio-gestao.svg)
![WF06 — Integração CRM/ERP](https://raw.githubusercontent.com/airionntelligentsystems/Agro-e/main/docs/prints/wf06-integracao-crm-erp.svg)

---

## 🖥️ CRM · Painel de Controle

Interface web completa com dashboards em tempo real, cobrindo todos os times da operação — comercial, compras, financeiro, gestão de estoque e controle de riscos.

![AGRO-e Intelligence · CRM Dashboard Premium](https://raw.githubusercontent.com/airionntelligentsystems/Agro-e/main/assets/dashboard-crm-preview.png)

*Monitor Climático por região · Score de Risco em tempo real · Radar de Oportunidades · Câmbio e Preços de Insumos · Estoque Estratégico · Timeline de execução autônoma · WhatsApp integrado.*

| Área | Módulos |
|---|---|
| **CRM Comercial** | Carteira de Clientes · Cadastro · Pipeline de Vendas · Radar de Oportunidades · Histórico Comercial |
| **Monitor de Riscos** | Score de Risco · Monitor Climático · El Niño 2026 · Monitor Câmbio · Documentos |
| **Compras e Estoque** | Estoque Estratégico · Catálogo de Insumos · Preços de Mercado · Fornecedores |
| **Financeiro** | Dashboard Financeiro · Análise de Margens |
| **Automação** | WhatsApp · Emails e Alertas · Workflows n8n |

---

## 🏗️ Arquitetura — 6 Workflows, 244 Nós

```
┌──────────────────────────────────────────────────────────────────────────┐
│             WF01 — ENTRADA + MONITOR PROATIVO (133 nós)                  │
│  REATIVO:  WhatsApp → Evolution API → Normalizador Universal → WF02      │
│            └─ Texto · Áudio (Whisper) · Imagem (Vision) · PDF (Extract)  │
│                                                                           │
│  PROATIVO: Schedule 8h → 7 fontes simultâneas → WF02                    │
│            └─ PostgreSQL · Supabase · NOAA ENSO · Open-Meteo 5 regiões  │
│               AwesomeAPI/BCB · Score climático · Multiplicador El Niño   │
└───────────────────────────────┬──────────────────────────────────────────┘
                                │
┌───────────────────────────────▼──────────────────────────────────────────┐
│             WF02 — CONSOLE MULTI-AGENTES (31 nós)                        │
│                                                                           │
│  Agente Roteador (GPT-4.1-mini · Postgres Chat Memory · Think Tool × 2)  │
│  ├── agente_monitor_climatico     → Open-Meteo GPS · 5 regiões           │
│  ├── agente_elnino_monitor        → NOAA ENSO · impacto por região       │
│  ├── agente_analista_cambio       → AwesomeAPI USD/BRL · insumos         │
│  ├── agente_analista_documental   → score 0–40pts · SLA tracking         │
│  ├── agente_monitoramento_autonomo → score composto 0–100                │
│  ├── agente_inteligencia_comercial → 4 tipos de oportunidade             │
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

### Score Composto de Risco 0–100

| Fator | Critério | Pontuação |
|---|---|---|
| Documental | Vencido=40 · ≤7d=35 · ≤30d=25 · ≤60d=15 | Máx 40pts |
| Chamados abertos | 7pts por chamado crítico | Máx 20pts |
| Histórico de atrasos | `historico_atrasos=true` no perfil | 15pts fixos |
| Exposição cambial | Crítica=15 · Alta=8 · Média=3 | Máx 15pts |
| Risco climático | >100mm=10 · >60mm=7 · Seca>14d=8 | Máx 10pts |
| **Multiplicador El Niño** | **Região × Cultura × ONI × Fase agrícola** | **+0–30%** |

**Classificação:** CRÍTICO >80 · ALTO 60–79 · MÉDIO 40–59 · BAIXO <40

---

## 🔧 Decisões de Engenharia

Registradas para demonstrar raciocínio de design — não apenas o que foi construído, mas por que foi construído assim.

---

**Por que múltiplos agentes em vez de um único agente genérico?**

Cada sub-agente tem system prompt especializado e escopo de dados específico. Um agente genérico para análise climática, documental, cambial e comercial simultânea produz respostas médias em tudo. Sub-agentes especializados produzem análises precisas em cada domínio, com menor risco de confusão de contexto e maior rastreabilidade de erros.

---

**Por que Supabase + PostgreSQL em vez de apenas Supabase?**

PostgreSQL via conexão direta é usado para operações que exigem SQL complexo — JOINs multi-tabela para o motor de oportunidades, queries de score composto com múltiplos fatores e memória conversacional de longo prazo (90 dias). Supabase REST API é usado para operações simples de leitura e escrita de linhas únicas, onde a overhead do SQL não é necessária e a velocidade é crítica.

---

**Por que Redis como camada de memória de curto prazo?**

Redis resolve dois problemas simultaneamente: debounce de mensagens WhatsApp (usuários frequentemente enviam mensagens fragmentadas — o sistema aguarda antes de processar, acumulando a mensagem completa) e armazenamento de contexto de mídia (transcrições de áudio, análises de imagem e extrações de PDF ficam em cache TTL 1h para não reprocessar em follow-ups imediatos).

---

**Por que monitoramento proativo às 8h em vez de alertas em tempo real?**

Alertas em tempo real para uma carteira de 50–500 produtores gerariam dezenas de notificações diárias — a maioria sem ação imediata necessária. O ciclo das 8h consolida todos os sinais, prioriza por urgência e entrega um relatório executivo estruturado antes do início do expediente. O operador recebe o que importa, na ordem que importa, no momento em que pode agir.

---

**Como o sistema reduz hallucination?**

O nome de cada cliente é extraído diretamente do banco via SQL — nunca gerado pelo modelo. O system prompt proíbe a criação de nomes ou dados ausentes dos dados injetados. As oportunidades comerciais são calculadas por código JavaScript determinístico e passadas ao agente como strings formatadas. O modelo interpreta e comunica — não inventa dados.

---

**Como trata rastreabilidade?**

Cada execução gera um `execucao_id` único. O histórico é salvo no Supabase com timestamp, modo (proativo/reativo), telefone e output. Relatórios de gestão (`agroe_relatorios_gestao`) armazenam cada alerta com tipo, prioridade, ação recomendada e status de rastreamento: pendente → em andamento → resolvido.

---

**Como protege contra prompt injection?**

7 system prompts em camadas distintas: roteador principal e cada sub-agente individualmente. Nenhum dado do usuário é injetado no system prompt — apenas no campo `text` controlado. O sanitizador de saída detecta e bloqueia JSON Schema, stack traces e conteúdo técnico interno antes do envio ao WhatsApp.

---

## 🛠️ Stack Tecnológico

| Componente | Tecnologia | Função |
|---|---|---|
| Orquestração | n8n self-hosted | 6 workflows · 244 nós |
| LLM | GPT-4.1-mini (OpenAI) | Motor de análise multi-agente |
| ASR | OpenAI Whisper | Transcrição de áudios WhatsApp |
| Vision | OpenAI Vision | Análise de imagens e documentos |
| Monitor Climático | Open-Meteo API | GPS por região · atualização horária |
| Monitor ENSO | NOAA/CPC + INMET + CPTEC | El Niño · ONI index em tempo real |
| Câmbio | AwesomeAPI / Banco Central | USD/BRL real-time · impacto por insumo |
| Banco de Dados | Supabase + PostgreSQL | 15 tabelas · RLS · Views |
| Memória Rápida | Redis (TTL 1h) | Debounce + contexto de sessão |
| WhatsApp | Evolution API | Canal bidirecional multimodal |
| Email | Gmail OAuth2 | Relatórios executivos reais |
| Calendário | Google Calendar OAuth2 | Alertas automáticos |

---

## 🔒 Proteção de Dados — LGPD

| Medida | Implementação | Base Legal |
|---|---|---|
| Row Level Security | RLS em todas as tabelas com dados pessoais | Art. 46 LGPD |
| Anonimização SQL | `agroe_anonimiza_telefone()` · `agroe_anonimiza_nome()` | Art. 12 LGPD |
| Retenção mínima | Chat: 90d · Logs: 180d · Execuções: 365d · limpeza automática | Art. 15 LGPD |
| Audit Trail | `agroe_lgpd_acesso_log` — operações com dados pessoais | Art. 37 LGPD |
| Anti-injection | 7 system prompts com proteção contra manipulação | Segurança |

---

## 🗺️ Roadmap

| Fase | Foco | Entrega |
|---|---|---|
| **Fase 1** | Evolução da inteligência | Calibração com dados operacionais reais · ajuste de scores e thresholds por histórico |
| **Fase 2** | Ampliação de fontes | Novas APIs climáticas regionais · fontes de preço de insumos em tempo real |
| **Fase 3** | Modelos preditivos | Feedback loop · pesos do score ajustados automaticamente por região e cultivo |
| **Fase 4** | Integrações corporativas | Conectores adicionais ERP/CRM · API REST pública · exportação para BI externo |
| **Fase 5** | Escalabilidade | Infraestrutura de escala horizontal · isolamento de dados multi-empresa |

---

## 🗂️ Evidências — Todos os Arquivos

| Arquivo | Descrição |
|---|---|
| [Relatório HTML Interativo](https://htmlpreview.github.io/?https://raw.githubusercontent.com/airionntelligentsystems/Agro-e/main/evidencias/agroe-evidencias.html) | Evidências completas — prints WhatsApp, emails, log de execuções, motor comercial |
| [Relatório de Evidências PDF](evidencias/agroe-evidencias.pdf) | Versão PDF do relatório completo de evidências |
| [Relatório de Email Enviado (PDF)](docs/evidencias/relatorio-email-real-27052026.pdf) | PDF do relatório executivo real recebido na inbox |
| [Relatório de Gestão (HTML)](docs/evidencias/relatorio-gestao-email.html) | Email HTML executivo gerado pelo sistema |
| [Execuções Reais Documentadas](docs/evidencias/execucoes-reais.md) | Log detalhado de execuções com IDs e resultados |
| [WF01 — Entrada + Monitor Proativo](docs/prints/wf01-entrada-monitor-proativo.svg) | Diagrama do workflow de entrada e ciclo proativo |
| [WF02 — Console Multi-Agentes](docs/prints/wf02-console-multiagentes.svg) | Diagrama do console de orquestração dos agentes |
| [WF03 — Escalada Humana](docs/prints/wf03-escalada-humano.svg) | Diagrama do workflow de escalada HITL |
| [WF04 — Monitor Documental](docs/prints/wf04-monitor-vencimentos.svg) | Diagrama do monitor de vencimentos |
| [WF05 — Relatório de Gestão](docs/prints/wf05-relatorio-gestao.svg) | Diagrama do workflow de relatório |
| [WF06 — Integração CRM/ERP](docs/prints/wf06-integracao-crm-erp.svg) | Diagrama do adaptador universal CRM/ERP |
| [WhatsApp — Print 1](evidencias/assets/wpp1.jpeg) | Análise de risco composto via WhatsApp |
| [WhatsApp — Print 2](evidencias/assets/wpp2.jpeg) | Motor de inteligência comercial em operação |
| [WhatsApp — Print 3](evidencias/assets/wpp3.jpeg) | Ciclo proativo autônomo das 8h |
| [WhatsApp — Print 4](evidencias/assets/wpp4.jpeg) | Processamento multimodal — áudio |
| [Email — Relatório na inbox](evidencias/assets/email3.jpeg) | Relatório executivo real recebido via Gmail OAuth2 |
| [Diagrama de Arquitetura](evidencias/assets/diagrama.png) | Fluxo completo dos workflows e integrações |
| [CRM Dashboard Preview](assets/dashboard-crm-preview.png) | Painel de controle premium — todos os módulos |
| [Schema do Banco de Dados](data/schema.md) | Estrutura das 15 tabelas Supabase |
| [Context Engineering — Arquitetura](docs/arquitetura/context-engineering.md) | Decisões de engenharia de contexto |

---

<div align="center">

**AGRO-e Intelligence** · Inteligência Operacional, Comercial e Climática Autônoma para o Agronegócio Brasileiro

André Fernandes · Maio 2026

*Em operação real · Arquitetura production-grade · El Niño 2026 monitorado · IP protegido*

</div>
