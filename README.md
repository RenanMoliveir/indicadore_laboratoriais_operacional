# LabInsight

Sistema de Business Intelligence para monitoramento operacional laboratorial desenvolvido com Python, Pandas, Power BI e DAX.

O projeto simula um ambiente real de análises clínicas, permitindo acompanhar indicadores operacionais, identificar gargalos, monitorar exames críticos e apoiar decisões baseadas em dados.

---

## Problema de Negócio

Laboratórios clínicos processam milhares de exames diariamente, exigindo monitoramento constante dos tempos de atendimento e cumprimento dos SLAs definidos para cada tipo de exame.

A ausência de indicadores consolidados dificulta a identificação de gargalos operacionais, atrasos críticos e oportunidades de melhoria operacional.

O LabInsight foi desenvolvido para transformar dados operacionais em informações acionáveis, permitindo monitorar a eficiência da operação laboratorial e apoiar decisões orientadas por dados.

---

## Objetivo

Construir uma solução de Business Intelligence capaz de monitorar a operação laboratorial por meio de indicadores de desempenho, com foco em:

* Controle de SLA dos exames
* Monitoramento do TAT (Turnaround Time)
* Identificação de exames críticos
* Análise operacional por origem, categoria e horário
* Investigação de causas de atraso
* Navegação detalhada até o nível do exame

---

## Dashboard Interativo

Acesse a versão publicada do projeto:

https://app.powerbi.com/reportEmbed?reportId=387555ce-66a1-46d2-a5c7-5acdaf144ffc&autoAuth=true&ctid=b142a9f4-1ae0-4309-913b-cc6fe2468213&actionBarEnabled=true

---

## Tecnologias Utilizadas

### Data Processing

* Python
* Pandas

### Business Intelligence

* Power BI
* DAX

### Modelagem de Dados

* Modelo Estrela (Star Schema)
* Tabela Fato e Dimensões

---

## Arquitetura da Solução

```text
Dados Operacionais
        │
        ▼
Python (ETL)
        │
        ▼
Tratamento e Padronização
        │
        ▼
Modelo Estrela
        │
        ▼
Power BI
        │
        ▼
Dashboard Operacional
```

---

## Dataset

A base simula uma operação laboratorial contendo:

* Pedidos laboratoriais
* Exames realizados
* Origens de atendimento
* Categorias de exames
* Horários de coleta e liberação
* Tempo de processamento (TAT)
* Metas de SLA

Os dados foram estruturados para reproduzir cenários operacionais encontrados em ambientes laboratoriais.

---

## Indicadores de Negócio

### Dashboard Executivo

* Quantidade de Pedidos
* Quantidade de Exames
* Percentual Fora do SLA
* Média de TAT
* Quantidade de Exames Atrasados

### Análises Operacionais

* Evolução diária de exames
* Evolução diária do SLA
* Evolução diária do TAT
* SLA por hora
* Origens com maior impacto no SLA
* Exames com maior incidência de atrasos

### Páginas Analíticas

* Dashboard Geral
* Detalhamento Operacional
* Análise por Categoria (Apoio, Crítico e Urgente)
* Operação Horária
* Tooltips Contextuais

---

## Dashboard

### Dashboard Geral

<img width="1200" height="768" alt="image" src="https://github.com/user-attachments/assets/da704e70-1397-4dff-a110-fe0032f82f91" />

### Detalhamento Operacional

<img width="1200" height="768" alt="image" src="https://github.com/user-attachments/assets/fc70776b-8d4c-4408-b1ec-baf4ec64af7e" />

### Operação Horária

<img width="1200" height="768" alt="image" src="https://github.com/user-attachments/assets/8c10a12a-45c2-47eb-81b7-8049a572efeb" />

---

## Modelagem de Dados

### Tabela Fato

**fato_exames**

Contém informações operacionais dos exames:

* Pedido
* Exame
* Origem
* Área
* Categoria
* Horário
* TAT
* Meta SLA

### Tabelas Dimensão

* dim_calendario
* dim_exame
* dim_origem
* dim_area
* dim_paciente

---

## Principais Métricas DAX

### Percentual Fora do SLA

```DAX
DIVIDE(
    [Qtde Fora SLA],
    [Qtde Exames],
    0
)
```

### Média TAT Operacional

```DAX
AVERAGEX(
    FILTER(
        fato_exames,
        fato_exames[TAT_Minutos_Duração] <= 1440
    ),
    fato_exames[TAT_Minutos_Duração]
)
```

---

## Insights Obtidos

A análise permitiu:

* Identificar os períodos de maior concentração operacional.
* Detectar origens com maior impacto nos indicadores de SLA.
* Mapear exames com maior incidência de atrasos.
* Avaliar a relação entre aumento de demanda e crescimento do TAT.
* Apoiar a identificação de oportunidades de melhoria operacional.

Esses indicadores permitem direcionar ações de monitoramento contínuo da qualidade assistencial e eficiência da operação laboratorial.

---

## Principais Aprendizados

Durante o desenvolvimento foram aplicados conceitos de:

* ETL em Python
* Limpeza e tratamento de dados
* Modelagem dimensional
* Desenvolvimento de medidas DAX
* Storytelling com dados
* Design de dashboards
* Tooltips customizadas
* Navegação entre páginas
* Business Intelligence aplicado à saúde
* Análise operacional laboratorial

---

## Roadmap

Próximas evoluções planejadas:

* Implementação de métricas On-Time
* Comparativo entre categorias de exames
* Evolução mensal do SLA
* Benchmark entre origens
* Alertas automáticos para desvios operacionais
* Análises preditivas utilizando Machine Learning

---

## Autor

### Isac Renan Oliveira

Analista de Dados com experiência em operações laboratoriais e projetos de Business Intelligence voltados para saúde.

Especializado em SQL, Python, Power BI e análise de indicadores operacionais.

### GitHub

https://github.com/RenanMoliveir

---

Projeto de Business Intelligence desenvolvido para simular o monitoramento operacional de laboratórios clínicos, aplicando conceitos de ETL, modelagem dimensional, análise de desempenho e visualização de dados.
