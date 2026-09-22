[![Status do Projeto](https://img.shields.io/badge/Status-Concluído-success.svg)](https://github.com/Isabelardg/engenharia-dados-ia-alura)
[![Tecnologias](https://img.shields.io/badge/Databricks%20%7C%20PySpark%20%7C%20SQL%20%7C%20Delta%20Lake-blue.svg)](https://github.com/Isabelardg/engenharia-dados-ia-alura)
[![IA](https://img.shields.io/badge/IA-Databricks%20Genie-orange.svg)](https://www.databricks.com/)
[![Tipo](https://img.shields.io/badge/Projeto-Engenharia%20de%20Dados%20%2B%20IA-purple.svg)](https://github.com/Isabelardg/engenharia-dados-ia-alura)

# ✈️ VoeBem Analytics — Engenharia de Dados com IA

O **VoeBem Analytics** é um projeto de Engenharia de Dados desenvolvido para construir um pipeline completo de dados utilizando **Databricks**, desde a ingestão dos dados brutos até a preparação de uma base estruturada para análises com Inteligência Artificial.

O projeto utiliza dados públicos relacionados à aviação brasileira, trabalhando com informações de **voos, aeroportos, atrasos e cancelamentos**.

A etapa final utiliza o **Databricks Genie** para permitir consultas sobre os dados utilizando linguagem natural.

---

## 🎯 Sobre o projeto

A ideia do projeto foi acompanhar todo o caminho dos dados dentro de um pipeline de Engenharia de Dados.

Os dados passam por diferentes etapas de tratamento e organização até chegarem a uma camada preparada para análise.

Durante o desenvolvimento, trabalhei com:

* ingestão de dados;
* transformação e tratamento utilizando PySpark;
* consultas utilizando SQL;
* arquitetura em camadas Bronze, Silver e Gold;
* modelagem dos dados;
* validação e qualidade dos dados;
* organização utilizando Unity Catalog;
* preparação dos dados para análise;
* utilização do Databricks Genie para consultas com IA.

---

## 🧠 Como funciona

O pipeline foi organizado em diferentes camadas para separar cada etapa do processamento:

```text
             ┌─────────────────────┐
             │    Dados públicos   │
             │       da ANAC       │
             └──────────┬──────────┘
                        │
                        ▼
             ┌─────────────────────┐
             │       Bronze        │
             │   Dados brutos      │
             └──────────┬──────────┘
                        │
                        ▼
             ┌─────────────────────┐
             │       Silver        │
             │ Dados tratados      │
             └──────────┬──────────┘
                        │
                        ▼
             ┌─────────────────────┐
             │ Qualidade dos dados │
             │ Validação e controle│
             └──────────┬──────────┘
                        │
                        ▼
             ┌─────────────────────┐
             │        Gold         │
             │ Dados para análise  │
             └──────────┬──────────┘
                        │
                        ▼
             ┌─────────────────────┐
             │   Databricks Genie  │
             │ Consultas com IA    │
             └─────────────────────┘
```

### Bronze

A camada Bronze recebe os dados em seu formato inicial, mantendo as informações próximas da origem.

Essa etapa também permite organizar os dados dentro do ambiente do Databricks para que eles possam seguir para os próximos processos.

### Silver

Na camada Silver, os dados passam por tratamentos e transformações.

O objetivo é deixar as informações mais organizadas e consistentes, preparando os dados para as etapas seguintes do pipeline.

### Qualidade dos dados

Também foram implementadas etapas para verificar a qualidade das informações.

Os registros podem passar por processos de marcação, auditoria e quarentena, permitindo identificar dados que apresentam inconsistências antes que eles sejam utilizados nas análises.

### Gold

Na camada Gold, os dados são estruturados para facilitar o consumo e a análise.

Entre as estruturas utilizadas estão:

* `dim_aeroporto`
* `fato_voos`
* `obt_voos`

A `obt_voos` reúne informações necessárias para diferentes análises, facilitando o acesso aos dados sem a necessidade de realizar diversos relacionamentos a cada consulta.

---

## 🗂️ Unity Catalog

A organização dos dados foi realizada utilizando o **Unity Catalog** do Databricks.

O projeto ficou estruturado da seguinte forma:

```text
voebem
│
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

A separação das camadas ajuda a organizar o fluxo dos dados desde a ingestão até as informações preparadas para análise.

---

## 🤖 Inteligência Artificial com Databricks Genie

Depois da construção e organização do pipeline, utilizei o **Databricks Genie** para realizar perguntas sobre os dados utilizando linguagem natural.

A ideia foi permitir que as informações preparadas na camada Gold pudessem ser exploradas sem precisar escrever manualmente uma consulta SQL para cada análise.

### Exemplos de perguntas

* Como o atraso evoluiu ao longo do dia?
* Quais aeroportos apresentam maior atraso?
* Quais companhias possuem maior taxa de cancelamento?
* Quais horários concentram mais voos atrasados?
* Quais rotas apresentam maior atraso médio?

---

## 📸 Demonstração

### Espaço VoeBem Analytics

O Genie foi configurado para trabalhar com os dados do projeto e responder perguntas relacionadas à pontualidade, atrasos e cancelamentos de voos.

<img width="1364" height="686" alt="VoeBem Analytics no Databricks Genie" src="./genie-voebem-analytics.png" />

### Exemplo de análise

A partir de uma pergunta em linguagem natural, o Genie realizou a análise dos dados e apresentou os resultados acompanhados de uma visualização.

<img width="839" height="541" alt="Análise da evolução dos atrasos ao longo do dia" src="./genie-analise-atrasos.png" />

Nesse exemplo, a análise mostra como o percentual de voos atrasados varia ao longo do dia, permitindo identificar horários com maior concentração de atrasos.

---

## 🛠️ Tecnologias utilizadas

* **Databricks**
* **Apache Spark / PySpark**
* **SQL**
* **Delta Lake**
* **Unity Catalog**
* **Databricks Genie**
* **Python**

  \

  # ✈️ VoeBem Analytics — Engenharia de Dados com IA

  O **VoeBem Analytics** é um projeto de Engenharia de Dados desenvolvido para construir um pipeline completo de dados utilizando **Databricks**, desde a ingestão dos dados brutos até a preparação de uma base estruturada para análises com Inteligência Artificial.

  O projeto utiliza dados públicos relacionados à aviação brasileira, trabalhando com informações de **voos, aeroportos, atrasos e cancelamentos**.

  ## A etapa final utiliza o **Databricks Genie** para permitir consultas sobre os dados utilizando linguagem natural.

  ## 🎯 Sobre o projeto

  A ideia do projeto foi acompanhar todo o caminho dos dados dentro de um pipeline de Engenharia de Dados.

  Os dados passam por diferentes etapas de tratamento e organização até chegarem a uma camada preparada para análise.

  Durante o desenvolvimento, trabalhei com:

  * ingestão de dados;
  * transformação e tratamento utilizando PySpark;
  * consultas utilizando SQL;
  * arquitetura em camadas Bronze, Silver e Gold;
  * modelagem dos dados;
  * validação e qualidade dos dados;
  * organização utilizando Unity Catalog;
  * preparação dos dados para análise;
  * utilização do Databricks Genie para consultas com IA.

  ---

  ## 🧠 Como funciona

  O pipeline foi organizado em diferentes camadas para separar cada etapa do processamento:

  ```text
               ┌─────────────────────┐
               │    Dados públicos   │
               │       da ANAC       │
               └──────────┬──────────┘
                          │
                          ▼
               ┌─────────────────────┐
               │       Bronze        │
               │   Dados brutos      │
               └──────────┬──────────┘
                          │
                          ▼
               ┌─────────────────────┐
               │       Silver        │
               │ Dados tratados      │
               └──────────┬──────────┘
                          │
                          ▼
               ┌─────────────────────┐
               │ Qualidade dos dados │
               │ Validação e controle│
               └──────────┬──────────┘
                          │
                          ▼
               ┌─────────────────────┐
               │        Gold         │
               │ Dados para análise  │
               └──────────┬──────────┘
                          │
                          ▼
               ┌─────────────────────┐
               │   Databricks Genie  │
               │ Consultas com IA    │
               └─────────────────────┘

  ```

  ### Bronze

  A camada Bronze recebe os dados em seu formato inicial, mantendo as informações próximas da origem.

  Essa etapa também permite organizar os dados dentro do ambiente do Databricks para que eles possam seguir para os próximos processos.

  ### Silver

  Na camada Silver, os dados passam por tratamentos e transformações.

  O objetivo é deixar as informações mais organizadas e consistentes, preparando os dados para as etapas seguintes do pipeline.

  ### Qualidade dos dados

  Também foram implementadas etapas para verificar a qualidade das informações.

  Os registros podem passar por processos de marcação, auditoria e quarentena, permitindo identificar dados que apresentam inconsistências antes que eles sejam utilizados nas análises.

  ### Gold

  Na camada Gold, os dados são estruturados para facilitar o consumo e a análise.

  Entre as estruturas utilizadas estão:

  * `dim_aeroporto`
  * `fato_voos`
  * `obt_voos`
    A `obt_voos` reúne informações necessárias para diferentes análises, facilitando o acesso aos dados sem a necessidade de realizar diversos relacionamentos a cada consulta.

  ---

  ## 🗂️ Unity Catalog

  A organização dos dados foi realizada utilizando o **Unity Catalog** do Databricks.

  O projeto ficou estruturado da seguinte forma:

  ```text
  voebem
  │
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

  ## A separação das camadas ajuda a organizar o fluxo dos dados desde a ingestão até as informações preparadas para análise.

  ## 🤖 Inteligência Artificial com Databricks Genie

  Depois da construção e organização do pipeline, utilizei o **Databricks Genie** para realizar perguntas sobre os dados utilizando linguagem natural.

  A ideia foi permitir que as informações preparadas na camada Gold pudessem ser exploradas sem precisar escrever manualmente uma consulta SQL para cada análise.

  ### Exemplos de perguntas

  * Como o atraso evoluiu ao longo do dia?
  * Quais aeroportos apresentam maior atraso?
  * Quais companhias possuem maior taxa de cancelamento?
  * Quais horários concentram mais voos atrasados?
  * Quais rotas apresentam maior atraso médio?

  ---

  ## 📸 Demonstração

  ### Espaço VoeBem Analytics

  O Genie foi configurado para trabalhar com os dados do projeto e responder perguntas relacionadas à pontualidade, atrasos e cancelamentos de voos.

  ### Exemplo de análise

  A partir de uma pergunta em linguagem natural, o Genie realizou a análise dos dados e apresentou os resultados acompanhados de uma visualização.

  ## Nesse exemplo, a análise mostra como o percentual de voos atrasados varia ao longo do dia, permitindo identificar horários com maior concentração de atrasos.

  ## 🛠️ Tecnologias utilizadas

  * **Databricks**
  * **Apache Spark / PySpark**
  * **SQL**
  * **Delta Lake**
  * **Unity Catalog**
  * **Databricks Genie**
  * **Python**
  * **Git e GitHub**

  ---

  ## 📁 Estrutura do projeto

  ```text
  engenharia-dados-ia-alura/
  │
  ├── catalog/
  │   └── estrutura.md
  │
  ├── docs/
  │   ├── fontes.md
  │   └── perguntas-de-negocio.md
  │
  ├── genie/
  │   ├── instrucoes.md
  │   └── genie_space.json
  │
  ├── notebooks/
  │   ├── 03_bronze_vra.py
  │   ├── 04_bronze_referencias.py
  │   ├── 05_silver_espelho.py
  │   └── 09_governanca_gold.py
  │
  ├── pipelines/
  │   └── qualidade/
  │       ├── 01_vra_marcado.sql
  │       ├── 02_vra_auditado.sql
  │       └── 03_vra_quarentena.sql
  │
  ├── scripts/
  │   ├── baixar_anac.py
  │   ├── perguntar_genie.py
  │   ├── montar_genie_space.py
  │   ├── rodar_notebook.sh
  │   └── rodar_pipeline.sh
  │
  ├── sql/
  │   ├── 00_preparar_ambiente.sql
  │   ├── metricas_qualidade.sql
  │   └── gold/
  │       ├── 01_dim_aeroporto.sql
  │       ├── 02_fato_voos.sql
  │       └── 03_obt_voos.sql
  │
  ├── genie-analise-atrasos.png
  ├── genie-voebem-analytics.png
  ├── .gitignore
  └── README.md

  ```

  ---

  ## 📊 Dados utilizados

  Os dados utilizados no projeto são provenientes de bases públicas relacionadas à aviação brasileira, incluindo informações disponibilizadas pela **ANAC**.

  ## Os arquivos brutos não foram incluídos no repositório devido ao tamanho. As fontes utilizadas e informações sobre os dados estão disponíveis na pasta [`docs`](https://chatgpt.com/c/docs).

  ## 💡 Aprendizados

  Durante o desenvolvimento do projeto, pude colocar em prática conceitos relacionados a:

  * Engenharia de Dados;
  * construção de pipelines;
  * arquitetura Bronze, Silver e Gold;
  * transformação de dados com PySpark;
  * consultas e modelagem utilizando SQL;
  * qualidade e validação dos dados;
  * organização e governança utilizando Unity Catalog;
  * utilização do Databricks;
  * preparação de dados para aplicações de IA;
  * consultas em linguagem natural utilizando Databricks Genie.

  ---

  ## 🎓 Imersão de Engenharia de Dados com IA

  Projeto desenvolvido durante a **Imersão de Engenharia de Dados com IA da Alura**, em setembro de 2026.

  ## O material disponibilizado durante a imersão foi utilizado como base de estudo e desenvolvimento, permitindo colocar em prática os conceitos apresentados ao longo do projeto.
* **Git e GitHub**

---

## 📁 Estrutura do projeto

```text
engenharia-dados-ia-alura/
│
├── catalog/
│   └── estrutura.md
│
├── docs/
│   ├── fontes.md
│   └── perguntas-de-negocio.md
│
├── genie/
│   ├── instrucoes.md
│   └── genie_space.json
│
├── notebooks/
│   ├── 03_bronze_vra.py
│   ├── 04_bronze_referencias.py
│   ├── 05_silver_espelho.py
│   └── 09_governanca_gold.py
│
├── pipelines/
│   └── qualidade/
│       ├── 01_vra_marcado.sql
│       ├── 02_vra_auditado.sql
│       └── 03_vra_quarentena.sql
│
├── scripts/
│   ├── baixar_anac.py
│   ├── perguntar_genie.py
│   ├── montar_genie_space.py
│   ├── rodar_notebook.sh
│   └── rodar_pipeline.sh
│
├── sql/
│   ├── 00_preparar_ambiente.sql
│   ├── metricas_qualidade.sql
│   └── gold/
│       ├── 01_dim_aeroporto.sql
│       ├── 02_fato_voos.sql
│       └── 03_obt_voos.sql
│
├── genie-analise-atrasos.png
├── genie-voebem-analytics.png
├── .gitignore
└── README.md
```

---

## 📊 Dados utilizados

Os dados utilizados no projeto são provenientes de bases públicas relacionadas à aviação brasileira, incluindo informações disponibilizadas pela **ANAC**.

Os arquivos brutos não foram incluídos no repositório devido ao tamanho. As fontes utilizadas e informações sobre os dados estão disponíveis na pasta [`docs`](./docs).

---

## 💡 Aprendizados

Durante o desenvolvimento do projeto, pude colocar em prática conceitos relacionados a:

* Engenharia de Dados;
* construção de pipelines;
* arquitetura Bronze, Silver e Gold;
* transformação de dados com PySpark;
* consultas e modelagem utilizando SQL;
* qualidade e validação dos dados;
* organização e governança utilizando Unity Catalog;
* utilização do Databricks;
* preparação de dados para aplicações de IA;
* consultas em linguagem natural utilizando Databricks Genie.

