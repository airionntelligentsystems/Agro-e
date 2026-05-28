# Schema do Banco de Dados — agro-e

Projeto Supabase: Arion (`us-east-1`)  
Banco: PostgreSQL 17.6  
Total de tabelas: 15 + 3 views + 4 funções SQL

---

## Tabelas Operacionais

### agroe_operacoes
```sql
id              VARCHAR(20) PRIMARY KEY,
nome_fazenda    VARCHAR(200) NOT NULL,
municipio       VARCHAR(100),
estado          CHAR(2),
produtor        VARCHAR(200),
contato         VARCHAR(20),
cultivo         VARCHAR(50),
area_hectares   INTEGER,
status_documental VARCHAR(20) CHECK IN ('atualizado','pendente','critico','vencido','indefinido'),
dias_vencimento INTEGER,           -- negativo = já vencido
historico_atrasos BOOLEAN DEFAULT FALSE,
chamados_abertos  INTEGER DEFAULT 0,
exposicao_cambial VARCHAR(10) CHECK IN ('critica','alta','media','baixa'),
lat             DECIMAL(9,6),      -- coordenada GPS para Open-Meteo
lon             DECIMAL(9,6),
criado_em       TIMESTAMPTZ DEFAULT NOW()
```

### agroe_documentos
```sql
id              VARCHAR(20) PRIMARY KEY,
operacao_id     VARCHAR(20) REFERENCES agroe_operacoes(id),
tipo            VARCHAR(50),       -- licenca_ambiental, registro_produtor_rural, etc.
status          VARCHAR(15) CHECK IN ('valido','vencendo','vencido','indefinido','pendente'),
dias            INTEGER,           -- dias para vencimento (negativo = vencido)
orgao           VARCHAR(100),      -- SUPRAM, SEAPDR-RS, MAPA, CPRM, etc.
data_vencimento DATE,
renovacao_iniciada BOOLEAN DEFAULT FALSE
```

### agroe_contexto (RLS habilitado)
```sql
id              BIGSERIAL PRIMARY KEY,
phone           VARCHAR(20) UNIQUE NOT NULL,
nome            VARCHAR(200),
memoria_contexto TEXT,             -- resumo do contexto de longo prazo
ai_service      VARCHAR(10) DEFAULT 'active' CHECK IN ('active','pause'),
ultimo_acesso   TIMESTAMPTZ,
criado_em       TIMESTAMPTZ DEFAULT NOW()
```

---

## Tabelas Comerciais

### agroe_clientes (RLS habilitado)
```sql
id              VARCHAR(20) PRIMARY KEY,
nome            VARCHAR(200) NOT NULL,
telefone        VARCHAR(20),       -- protegido por RLS + anonimização
municipio       VARCHAR(100),
estado          CHAR(2),
cultivos        TEXT[],            -- ['soja','milho','cana_de_acucar']
area_hectares   INTEGER,
segmento        VARCHAR(50),       -- pequeno, medio, grande, cooperativa
potencial_compra VARCHAR(10),      -- alto, medio, baixo
ultima_compra   DATE
```

### agroe_catalogo_produtos
```sql
id              VARCHAR(20) PRIMARY KEY,
nome            VARCHAR(150) NOT NULL,
categoria       VARCHAR(50),       -- defensivo, fertilizante, semente, equipamento
preco_atual     DECIMAL(10,2),
preco_anterior  DECIMAL(10,2),
variacao_pct    DECIMAL(5,2),      -- negativo = queda de preço = oportunidade
sensivel_cambio BOOLEAN DEFAULT FALSE,
atualizado_em   TIMESTAMPTZ DEFAULT NOW()
```

### agroe_regioes_estrategicas
```sql
id              VARCHAR(20) PRIMARY KEY,
municipio       VARCHAR(100),
estado          CHAR(2),
potencial       VARCHAR(10),       -- alto, medio, baixo
presenca_empresa VARCHAR(10),      -- forte, media, fraca, ausente
participacao_mercado DECIMAL(5,2), -- % estimado de mercado
nivel_concorrencia VARCHAR(10),    -- alta, media, baixa
oportunidade_expansao BOOLEAN DEFAULT FALSE
```

---

## Tabelas de Gestão

### agroe_relatorios_gestao
```sql
id              BIGSERIAL PRIMARY KEY,
tipo            VARCHAR(50) CHECK IN (
                  'risco_documental','risco_climatico','risco_cambial',
                  'oportunidade_comercial','expansao_estrategica',
                  'risco_perda_cliente','alerta_operacional'),
prioridade      VARCHAR(10) CHECK IN ('critica','alta','media','baixa'),
score           INTEGER,           -- 0-100 para riscos
titulo          VARCHAR(300) NOT NULL,
descricao       TEXT NOT NULL,
acao_recomendada TEXT NOT NULL,
prazo_sugerido  VARCHAR(50),       -- imediato, esta_semana, este_mes
potencial_impacto TEXT,
status          VARCHAR(20) DEFAULT 'pendente'
                  CHECK IN ('pendente','em_andamento','resolvido','descartado','escalado'),
responsavel_nome VARCHAR(200),
notas_gestao    TEXT,
execucao_modo   VARCHAR(10),       -- proativo / reativo
fonte_dados     TEXT[],
criado_em       TIMESTAMPTZ DEFAULT NOW(),
atualizado_em   TIMESTAMPTZ DEFAULT NOW()
```

### VIEW: agroe_dashboard_gestao
```sql
-- Itens em aberto com SLA calculado
-- sla_vencido = true quando:
--   prioridade='critica' AND pendente > 4 horas
--   prioridade='alta'    AND pendente > 24 horas
SELECT *, 
  EXTRACT(EPOCH FROM (NOW() - criado_em))/3600 AS horas_em_aberto,
  CASE WHEN ... THEN true ELSE false END AS sla_vencido
FROM agroe_relatorios_gestao
WHERE status NOT IN ('resolvido', 'descartado')
ORDER BY prioridade, criado_em DESC
```

---

## Funções SQL (LGPD)

```sql
-- Anonimização para relatórios públicos
agroe_anonimiza_telefone(telefone TEXT) → TEXT
-- Ex: '5554996543210' → '5554****3210'

agroe_anonimiza_nome(nome TEXT) → TEXT
-- Ex: 'Roberto Gonçalves' → 'Roberto G*******'

-- Limpeza automática de dados por retenção mínima
agroe_limpa_dados_expirados() → void
-- chat_memory > 90 dias → DELETE
-- integracao_log > 180 dias → DELETE
-- historico_execucoes > 365 dias → DELETE
```

---

## Índices

```sql
-- Consultas por urgência (principal query proativa)
CREATE INDEX idx_operacoes_status ON agroe_operacoes(status_documental);
CREATE INDEX idx_documentos_status ON agroe_documentos(status, dias);

-- Memória conversacional por sessão
CREATE INDEX idx_agroe_chat_session ON agroe_chat_memory(session_id);

-- Gestão por prioridade e status
CREATE INDEX idx_gestao_status ON agroe_relatorios_gestao(status, prioridade);

-- Histórico comercial por cliente
CREATE INDEX idx_hist_comercial_cliente ON agroe_historico_comercial(cliente_id);
```

---

*Schema em produção no Supabase Arion. Dados pessoais protegidos por RLS.*  
*© 2026 Andre Fernandes — Documentação para fins de avaliação.*
