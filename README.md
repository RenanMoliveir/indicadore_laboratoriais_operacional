# LabInsight | PerformanceLab

Dashboard operacional laboratorial desenvolvido com foco em monitoramento de desempenho, SLA e Tempo Médio de Atendimento (TAT).

O projeto simula um ambiente real de análises clínicas, permitindo acompanhar indicadores operacionais, identificar gargalos, monitorar exames críticos e apoiar decisões baseadas em dados.

---

##  Objetivo

Construir uma solução de Business Intelligence capaz de monitorar a operação laboratorial através de indicadores de desempenho, com foco em:

- Controle de SLA dos exames
- Monitoramento do TAT (Turnaround Time)
- Identificação de exames críticos
- Análise operacional por origem, categoria e horário
- Investigação de causas de atraso
- Navegação detalhada até o nível do exame

---

## 🛠 Tecnologias Utilizadas

### Data Processing

- Python
- Pandas

### Business Intelligence

- Power BI
- DAX

### Modelagem

- Modelo Estrela (Star Schema)
- Tabela Fato e Dimensões

---

## 📊 Indicadores Desenvolvidos

### Dashboard Executivo

- Quantidade de Pedidos
- Quantidade de Exames
- % Fora SLA
- Média TAT
- Quantidade de Exames Atrasados

### Análises Operacionais

- Evolução diária de exames
- Evolução diária do SLA
- Evolução diária do TAT
- SLA por hora
- Origens com maior impacto no SLA
- Exames com maior quantidade de atrasos

### Páginas Analíticas

- Dashboard Geral
- Detalhamento Operacional
- Análise por Categoria (Apoio, Crítico e Urgente)
- Operação Horária
- Tooltips Contextuais

---

## Estrutura dos Dados

### Tabela Fato

**fato_exames**

Contém informações operacionais dos exames:

- Pedido
- Exame
- Origem
- Área
- Categoria
- Horário
- TAT
- Meta SLA

### Tabelas Dimensão

- dim_calendario
- dim_exame
- dim_origem
- dim_area
- dim_paciente

---

## Principais Métricas DAX

### % Fora SLA

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

## 🎯 Principais Aprendizados

Durante o desenvolvimento foram aplicados conceitos de:

- ETL em Python
- Limpeza e tratamento de dados
- Modelagem dimensional
- Criação de medidas DAX
- Storytelling com dados
- Design de dashboards
- Tooltips customizadas
- Navegação entre páginas
- Análise operacional laboratorial

---

## 🌐 Dashboard Online

Acesse a versão publicada do projeto:

👉 https://app.powerbi.com/reportEmbed?reportId=387555ce-66a1-46d2-a5c7-5acdaf144ffc&autoAuth=true&ctid=b142a9f4-1ae0-4309-913b-cc6fe2468213&actionBarEnabled=true

---

## 📷 Screenshots

### Dashboard Geral

<img width="1200" height="768" alt="image" src="https://github.com/user-attachments/assets/da704e70-1397-4dff-a110-fe0032f82f91" />


### Detalhamento Operacional

<img width="1200" height="768" alt="image" src="https://github.com/user-attachments/assets/fc70776b-8d4c-4408-b1ec-baf4ec64af7e" />


### Operação Horária

<img width="1200" height="768" alt="image" src="https://github.com/user-attachments/assets/8c10a12a-45c2-47eb-81b7-8049a572efeb" />

---

## 🚀 Próximos Passos

- Implementação de métricas de On Time
- Comparativo entre categorias
- Evolução mensal do SLA
- Benchmark entre origens
- Alertas automáticos para desvios operacionais
- Análises preditivas utilizando Machine Learning

---

## 👨‍💻 Autor

### Isac Renan Oliveira

Biomédico e Pós-graduando em Data Science

Áreas de interesse:

- Data Analytics
- Business Intelligence
- Power BI
- Python
- SQL
- Machine Learning
- Dados em Saúde

### GitHub

https://github.com/RenanMoliveir

### LinkedIn

(Adicionar link)

---

⭐ Projeto desenvolvido para estudo e aperfeiçoamento em análise de dados aplicada ao ambiente laboratorial.
