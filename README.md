# Engenharia de Dados com IA | Databricks

Projeto desenvolvido durante a **Imersão de Engenharia de Dados com IA da Alura**, utilizando Databricks para construir um pipeline de dados completo, desde a ingestão dos dados brutos até uma camada preparada para consultas com Inteligência Artificial.

O projeto utiliza dados públicos da **ANAC** e uma base fictícia de uma empresa aérea, permitindo trabalhar com informações de voos, aeroportos, atrasos e cancelamentos.

## 🚀 Sobre o projeto

A proposta foi construir um pipeline organizado em diferentes etapas, acompanhando o caminho dos dados desde a sua chegada até o consumo para análises.

Durante o desenvolvimento, trabalhei com:

- ingestão e tratamento de dados
- PySpark e SQL
- arquitetura em camadas Bronze, Silver e Gold
- modelagem de dados
- qualidade e validação dos dados
- Unity Catalog
- Databricks Genie
- preparação dos dados para consultas utilizando IA

## 🏗️ Arquitetura

```text
Dados públicos da ANAC
        ↓
     Bronze
        ↓
     Silver
        ↓
 Qualidade dos dados
        ↓
      Gold
        ↓
 Dados preparados para análise
        ↓
 Databricks Genie
```

### Bronze

Na primeira etapa, os dados são carregados para o Databricks mantendo as informações próximas do formato original.

Além da ingestão, são adicionadas informações que ajudam no controle e acompanhamento dos dados dentro do pipeline.

### Silver

Na camada Silver, os dados passam por tratamentos e padronizações.

Essa etapa deixa as informações mais organizadas e consistentes para que possam ser utilizadas nas próximas etapas do projeto.

### Qualidade dos dados

Antes de disponibilizar os dados para consumo, são aplicadas verificações para identificar possíveis problemas.

Os registros que apresentam inconsistências podem ser direcionados para processos de auditoria e quarentena, evitando que dados com problemas avancem para as etapas seguintes.

### Gold

A camada Gold concentra os dados preparados para análise.

Foram criadas estruturas como:

- `dim_aeroporto`
- `fato_voos`
- `obt_voos`

A `obt_voos` reúne as principais informações necessárias para as consultas, reduzindo a necessidade de realizar diversos relacionamentos entre tabelas durante a análise.

## 🗂️ Unity Catalog

O projeto foi organizado no Databricks utilizando o Unity Catalog.

```text
voebem
├── bronze
│   ├── 5 tabelas
│   └── volume: arquivos
│
├── silver
│   └── 5 tabelas
│
└── gold
    └── 3 tabelas
```

Essa organização separa os dados de acordo com o estágio em que eles se encontram no pipeline e facilita o gerenciamento das diferentes camadas.

A documentação da estrutura está em [`catalog/estrutura.md`](catalog/estrutura.md).

## 🤖 IA com Databricks Genie

Depois de preparar os dados na camada Gold, utilizei o **Databricks Genie** para fazer perguntas sobre a base utilizando linguagem natural.

Alguns exemplos de perguntas trabalhadas:

- Quais aeroportos concentram os maiores atrasos?
- Como os atrasos variam ao longo do dia?
- Quais rotas apresentam maior atraso médio?
- Qual é a taxa de cancelamento das companhias aéreas?
- Existem diferenças de pontualidade entre voos domésticos e internacionais?

### Exemplo de consulta

O Genie foi utilizado para analisar os dados de pontualidade e atrasos a partir de perguntas em linguagem natural.

![Databricks Genie - análise de atrasos](./genie-analise-atrasos.png)

A resposta apresenta tanto os resultados da análise quanto uma visualização dos dados, facilitando a interpretação das informações.

Também configurei um espaço do Genie para realizar as consultas sobre a base:

![Databricks Genie - VoeBem Analytics](./genie-voebem-analytics.png)

A utilização do Genie permite consultar os dados sem precisar escrever manualmente uma consulta SQL para cada pergunta, utilizando a camada preparada no pipeline como base para as respostas.

## 🛠️ Tecnologias utilizadas

- **Databricks**
- **Apache Spark / PySpark**
- **SQL**
- **Delta Lake**
- **Unity Catalog**
- **Databricks Genie**
- **Python**

## 📁 Estrutura do projeto

```text
engenharia-dados-ia-alura/
│
├── catalog/          # Estrutura do Unity Catalog
├── docs/             # Documentação e referências
├── genie/            # Configurações relacionadas ao Genie
├── notebooks/        # Notebooks desenvolvidos no Databricks
├── pipelines/        # Processos de qualidade dos dados
├── scripts/          # Scripts auxiliares
├── sql/              # Scripts SQL do projeto
│
├── .gitignore
└── README.md
```

## 📊 Dados

Os dados utilizados no projeto são públicos e disponibilizados pela **ANAC**.

Os arquivos brutos não foram incluídos no repositório devido ao tamanho. As fontes e informações necessárias para obtê-los novamente estão documentadas na pasta `docs/`.

## 💡 Principais aprendizados

Este projeto me permitiu colocar em prática conceitos de Engenharia de Dados, principalmente:

- construção de pipelines de dados
- arquitetura Bronze, Silver e Gold
- transformação de dados com PySpark
- consultas e modelagem utilizando SQL
- qualidade e organização dos dados
- utilização do Unity Catalog
- preparação de dados para aplicações de IA
- consultas em linguagem natural com Databricks Genie

## 🎓 Sobre a imersão

Projeto desenvolvido durante a **Imersão de Engenharia de Dados com IA da Alura**, em setembro de 2026.

O material disponibilizado pela Alura foi utilizado como base de estudo e desenvolvimento do projeto.
