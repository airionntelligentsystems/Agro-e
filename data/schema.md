# Modelo de Dados — AGRO-e Intelligence

Banco de dados relacional (PostgreSQL) com 15 tabelas, 3 views analíticas e 4 funções SQL.
Row Level Security (RLS) habilitado em todas as tabelas com dados sensíveis.

---

## Grupos de Tabelas

### Grupo 1 — Operações e Documentos
Armazena o portfólio de clientes operacionais. Cada registro contém dados geoespaciais
(coordenada por propriedade) para integração com fontes de dados climáticos.
Inclui campos de scoring documental, histórico operacional e classificação de exposição
a fatores externos.

### Grupo 2 — Inteligência Comercial
Histórico de transações, catálogo de produtos com variação de preços e regiões
estratégicas com análise de presença de mercado e concorrência.

### Grupo 3 — Contexto e Memória (RLS habilitado)
Memória conversacional multi-camada por operador. Suporte a estados de sessão,
resumos de contexto de longo prazo e controle de fluxo de atendimento.

### Grupo 4 — Rastreabilidade e Auditoria
Registro completo de execuções do sistema, histórico de alertas gerados, itens
rastreáveis por status e log de conformidade com LGPD.

---

## Conformidade e Segurança

| Medida | Implementação |
|---|---|
| Row Level Security | Habilitado em todas as tabelas com dados pessoais |
| Anonimização | Funções SQL para dados pessoais em relatórios externos |
| Retenção | Políticas automáticas por categoria de dado |
| Audit Trail | Log de acesso a dados sensíveis com base legal |

---

## Views Analíticas

Três views consolidam os dados operacionais para o engine de scoring e para os
relatórios executivos — eliminando queries complexas nos workflows e centralizando
a lógica de negócio no banco.

---

## Design Decisions

**Por que 15 tabelas separadas em vez de uma estrutura flat?**
Separar operações, documentos, histórico comercial e contexto de memória em tabelas
distintas permite aplicar políticas de acesso, retenção e anonimização por categoria —
o que é exigido pelo Art. 15 da LGPD (princípio da necessidade) e torna cada
política auditável independentemente.

**Por que coordenadas geoespaciais por propriedade?**
O sistema faz chamadas a APIs climáticas com coordenadas reais — não por município.
A precisão geoespacial reduz a margem de erro do risco climático calculado e aumenta
a qualidade das recomendações por cliente.

**Por que armazenar score de risco como campo calculado?**
O score é persistido após cada ciclo proativo (não apenas calculado em tempo real)
para permitir rastreabilidade de evolução, alertas de deterioração e auditoria de
decisões históricas — incluindo quando e por que um cliente foi classificado como CRÍTICO.
