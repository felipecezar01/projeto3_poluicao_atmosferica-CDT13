# Projeto 03 — Alerta Vermelho: Crise Ambiental Misteriosa

> **Disciplina:** Programação para Ciência de Dados
> **Curso:** MBA em Ciência de Dados — UNIFOR
> **Professor:** Cássio Pinheiro
> **Formato:** Datathon Investigativo
> **Trabalho:** Em duplas ou trios (formação livre)
> **Classificação:** Grupo B — Analítico Realista (semi-investigativo: descobrir fonte poluidora)

---

## Briefing da Operação

A Secretaria de Meio Ambiente detectou um **aumento alarmante de internações por doenças respiratórias** em bairros específicos da cidade. As estações de monitoramento de qualidade do ar registram dados há 2 anos, mas ninguém ainda cruzou esses dados com os registros hospitalares. Sua missão é descobrir: **de onde vem a poluição, quando ela acontece e quem está sendo afetado**.

Há 8 estações de monitoramento, um cadastro de indústrias e dados de internações. A resposta está no cruzamento.

---

## Datasets Fornecidos

### 1. `data/projeto_03_qualidade_ar.csv`
Medições de qualidade do ar em 8 estações (2023-2024), com leituras em 5 horários por dia.

| Coluna | Descrição |
|--------|-----------|
| `data` | Data da medição |
| `hora` | Hora da medição (0, 6, 12, 18, 22) |
| `estacao` | Nome da estação de monitoramento |
| `tipo_zona` | Tipo da zona (urbana, industrial, residencial, parque) |
| `mp25_ugm3` | Material Particulado 2.5 (µg/m³) |
| `mp10_ugm3` | Material Particulado 10 (µg/m³) |
| `o3_ugm3` | Ozônio (µg/m³) |
| `no2_ugm3` | Dióxido de Nitrogênio (µg/m³) — **atenção: pode conter valores negativos** |
| `so2_ugm3` | Dióxido de Enxofre (µg/m³) |
| `temperatura_c` | Temperatura (°C) |
| `umidade_relativa_pct` | Umidade relativa (%) |

### 2. `data/projeto_03_internacoes_respiratorias.csv`
Internações por doenças respiratórias por bairro.

| Coluna | Descrição |
|--------|-----------|
| `internacao_id` | Identificador da internação |
| `data_internacao` | Data da internação |
| `bairro_residencia` | Bairro de residência do paciente |
| `idade_paciente` | Idade |
| `sexo` | Sexo (M/F) |
| `diagnostico` | Diagnóstico (Asma, Bronquite, DPOC, Pneumonia, etc.) |
| `gravidade` | Gravidade (Leve, Moderada, Grave) |
| `dias_internacao` | Dias de internação |
| `uti` | Se precisou de UTI (0/1) |

### 3. `data/projeto_03_cadastro_industrias.csv`
Cadastro de indústrias na região monitorada.

| Coluna | Descrição |
|--------|-----------|
| `industria_id` | Identificador |
| `nome` | Nome da indústria |
| `bairro` | Bairro onde está localizada |
| `tipo_atividade` | Tipo de atividade industrial |
| `porte` | Porte (Pequeno, Médio, Grande) |
| `licenca_ambiental` | Status da licença (Vigente, Vencida) |
| `data_ultima_fiscalizacao` | Data da última fiscalização |
| `horario_operacao_declarado` | Horário de operação declarado |
| `emissoes_declaradas_ton_ano` | Emissões declaradas (ton/ano) |

---

## Missão

Investigue os dados e responda:

1. **Qual estação apresenta os piores índices de qualidade do ar?** Compare MP2.5, MP10, SO2 e NO2 entre todas as estações. Há alguma que se destaca dramaticamente?
2. **Existe um padrão horário na poluição?** Compare os níveis de poluentes por hora do dia em cada estação. Alguma estação tem picos em horários inesperados (noite/madrugada)?
3. **Os bairros com mais internações respiratórias coincidem com as estações mais poluídas?** Cruze dados de qualidade do ar com internações por bairro.
4. **O período seco agrava a situação?** Compare internações e poluição entre meses secos e chuvosos.
5. **O cadastro de indústrias aponta um suspeito?** Cruze o bairro da estação mais poluída com as indústrias cadastradas. Há alguma com licença vencida ou que opere fora do horário declarado?
6. **Construa um índice de qualidade do ar** (IQA) composto e classifique cada estação/período.

---

## Pistas Iniciais

- Compare os níveis de **SO2 e NO2 às 22h e 0h** entre todas as estações — uma delas tem comportamento muito diferente
- O bairro **Jurema** merece atenção especial — cruze com internações e cadastro de indústrias
- Procure indústrias com **licença ambiental vencida** ou com **fiscalização desatualizada**
- Compare o **horário de operação declarado** das indústrias com o horário dos picos de poluição
- Os valores negativos de NO2 são erros de medição — precisam de tratamento

---

## Desafio de Dados Reais

Enriqueça sua investigação com dados públicos reais:

| Fonte | URL | O que buscar |
|-------|-----|-------------|
| **OpenAQ** | https://openaq.org/ | Dados reais de qualidade do ar em cidades brasileiras |
| **CETESB** | https://cetesb.sp.gov.br/ar/qualar/ | Padrões de referência de qualidade do ar no Brasil |
| **DataSUS** | https://datasus.saude.gov.br/ | Internações respiratórias reais por região |

**Perguntas de cruzamento:**
- Os níveis de poluentes encontrados estão acima dos limites da OMS e do CONAMA?
- A sazonalidade de internações respiratórias no dataset é compatível com dados reais do Nordeste?

---

## Técnicas Esperadas

| Módulo | Técnicas |
|--------|----------|
| **M1 — Python** | Tratamento de valores negativos, criação de IQA com funções, leitura de múltiplos CSVs |
| **M2 — Pandas/NumPy** | `merge` entre datasets, análise temporal por hora/dia/mês, `groupby` multi-nível, percentis para classificação, criação de features derivadas |
| **M3 — Visualização** | Heatmaps calendário, violinplots por estação, FacetGrid do Seaborn, lineplot temporal comparativo, subplots por horário |

---

## Estrutura do Projeto

```
projeto_03/
├── README.md          ← Este arquivo
├── data/              ← 3 datasets do projeto
├── notebooks/         ← Notebook(s) Jupyter com a investigação
├── scripts/           ← Scripts Python auxiliares (se necessário)
└── docs/              ← Documentação adicional, apresentação
```

## Entregáveis

1. **Notebook Python (.ipynb)** em `notebooks/` contendo:
   - Importação e inspeção dos 3 datasets
   - Limpeza e transformação (nulos, tipos, valores negativos, outliers)
   - Cruzamento entre datasets (merge/join)
   - Análise investigativa com estatísticas descritivas
   - Mínimo de **8 visualizações** (mix de Matplotlib e Seaborn)
   - Respostas à missão com **evidências nos dados**
   - Células Markdown narrando a investigação (storytelling)
   - Conclusões: qual é a fonte poluidora e como ela afeta a saúde

2. **Apresentação oral** (5-7 minutos) — arquivo em `docs/`

## Critérios de Avaliação

| Critério | Peso | O que será observado |
|----------|------|----------------------|
| **Limpeza e transformação dos dados** | 20% | Tratamento de nulos, duplicatas, tipos incorretos, outliers. Justificativa das decisões. |
| **Profundidade da investigação** | 25% | Cruzamento entre os 3 datasets. Respostas fundamentadas à missão. Descoberta de padrões ocultos. |
| **Qualidade e variedade das visualizações** | 20% | Mínimo 8 gráficos. Pelo menos 3 tipos diferentes. Títulos, rótulos, legendas. |
| **Storytelling investigativo** | 20% | Narrativa coerente. Evidências visuais. Conclusões defendidas com dados. Apresentação oral. |
| **Organização do código e boas práticas** | 15% | Código limpo. Funções quando apropriado. Notebook autoexplicativo. |

### Bonificações
- **Enriquecimento com dados reais** (integração de fonte pública): **+1.0 ponto**
- Uso criativo de feature engineering: **+0.5 ponto**
- Visualização avançada além do esperado: **+0.5 ponto**
- Análise adicional não solicitada com insights valiosos: **+0.5 ponto**

### Penalizações
- Notebook sem células Markdown explicativas: **-1.0 ponto**
- Gráficos sem título, rótulos ou legendas: **-0.5 ponto por gráfico**
- Código copiado sem adaptação (entre grupos): **nota zero para ambos**
- Entrega após o prazo: **-2.0 pontos por dia**

---

*Prof. Cássio Pinheiro — MBA Ciência de Dados — UNIFOR — 2026*
