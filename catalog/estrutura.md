# Estrutura do Unity Catalog

O projeto foi organizado no Databricks utilizando o Unity Catalog.

```text
voebem
├── bronze
│   ├── 5 tabelas
│   └── volume: arquivos
├── silver
│   └── 5 tabelas
└── gold
    └── 3 tabelas
```

A separação em Bronze, Silver e Gold acompanha as diferentes etapas do
pipeline, desde os dados mais próximos da origem até as estruturas
preparadas para análise e consumo por IA.
