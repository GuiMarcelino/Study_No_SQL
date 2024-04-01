# Diferenças Estruturais entre SQL e NoSQL

Este documento oferece uma visão introdutória sobre as principais diferenças estruturais entre os bancos de dados SQL (Relacionais) e NoSQL.

## SQL (Sistemas de Gerenciamento de Banco de Dados Relacionais)

Os bancos de dados SQL são estruturados em tabelas, onde cada tabela é composta por linhas e colunas. 

Cada coluna em uma tabela tem um tipo de dados específico, e cada linha é um registro que contém dados para cada coluna.

Podem conter relacionamentos entre as tabelas, que são representados por (PK)Chave Primária e (FK)Chave Estrangeira.

- **Tabelas:** Estruturas que armazenam dados em linhas e colunas.
- **Relacionamentos:** Definidos por chaves primárias e estrangeiras, permitindo a integração de dados entre diferentes tabelas.
- **Colunas e Tipos de Dados:** Cada coluna possui um tipo de dado específico, como inteiro, string, data, etc.

## NoSQL

Diferentemente dos bancos de dados SQL, os NoSQL não seguem um modelo de dados tabular. Eles são projetados para armazenar e gerenciar dados em formatos que podem ser mais flexíveis e escaláveis, dependendo do tipo de NoSQL. 

Aqui estão os principais tipos e como eles lidam com estruturas de dados, semelhantes a tabelas e relacionamentos:

- **Bancos de Dados de Documentos:** Armazenam dados em documentos (geralmente formatos JSON, BSON), que são análogos a registros/linhas em bancos de dados SQL, mas podem conter estruturas complexas e aninhadas. Exemplo: MongoDB.
  
- **Bancos de Dados de Colunas:** Otimizados para leituras e escritas rápidas em grandes volumes de dados, armazenando dados por colunas ao invés de linhas. Isso é útil para análises em tempo real. Exemplo: Cassandra.
  
- **Bancos de Dados de Grafos:** Focados em armazenar entidades (nós) e seus relacionamentos (arestas), ideais para dados interconectados, como redes sociais. Exemplo: Neo4j.
  
- **Bancos de Dados de Chave-Valor:** Os mais simples, onde cada item é armazenado como uma chave com seu valor correspondente. Exemplo: Redis.

## Transição de SQL para NoSQL

- **Chaves Primárias e Estrangeiras:** Enquanto os bancos de dados SQL usam chaves primárias e estrangeiras para relacionamentos, NoSQL lida com relacionamentos de maneiras variadas, como documentos aninhados (em bancos de dados de documentos) ou relações explicitamente definidas (em bancos de dados de grafos).

- **Estruturas de Dados Flexíveis:** NoSQL oferece mais flexibilidade em termos de estruturas de dados, não exigindo um esquema fixo. Isso permite um desenvolvimento mais rápido e iterativo de aplicações.

## Diferenças SQL"ACID"  NoSQL(BASE)

## SQL:

Os bancos de dados SQL seguem o modelo ACID para transações, garantindo:

- **Atomicidade:** Uma transação é uma unidade indivisível de operação. Isso significa que todas as operações dentro da transação são executadas ou nenhuma é.
- **Consistência:** As transações levam o banco de dados de um estado consistente para outro, mantendo a integridade dos dados.
- **Isolamento:** Transações executadas simultaneamente não interferem umas nas outras.
- **Durabilidade:** Uma vez que a transação é confirmada, ela permanece gravada no banco de dados, mesmo em caso de falha.

## NoSQL:

Os bancos de dados NoSQL seguem o modelo BASE, que é mais flexível que o ACID e se concentra em:

- **Basically Available:** Garante a disponibilidade básica do banco de dados em larga escala, mesmo em face de falhas parciais.
- **Soft-State:** O estado do banco de dados pode mudar com o tempo, mesmo sem input.
- **Eventually Consistent:** O banco de dados pode não ser imediatamente consistente, mas chegará a um estado consistente eventualmente.

