# Informações sobre MongoDB:

### Características: MongoDB é de código aberto, se destaca pela alta performance e utiliza o conceito de schema-free, utiliza Json(Bson) para armazenamento dos dados.

# Comparação de Unidades Estruturais: MongoDB vs SQL

Este documento apresenta uma comparação entre as unidades estruturais do MongoDB e bancos de dados SQL, facilitando o entendimento de suas diferenças e semelhanças.

## Unidades de Estrutura

A tabela abaixo compara as principais unidades estruturais do MongoDB e dos bancos de dados SQL:
| MongoDB                      | SQL                             | Descrição                                                                                     |
|------------------------------|---------------------------------|-----------------------------------------------------------------------------------------------|
| **Documento**                | **Tupla/Registro**              | A menor unidade de dados, equivalente a uma linha em uma tabela SQL.                         |
| **Coleção**                  | **Tabela**                      | Um conjunto de documentos, similar a uma tabela em bancos de dados SQL.                      |
| **Campo**                    | **Coluna**                      | Um identificador de dados dentro de um documento, equivalente a uma coluna em uma tabela SQL.|
| **Base de Dados (Database)** | **Base de Dados (Database)**    | Um agrupamento lógico de coleções, similar ao conceito de database em SQL.                    |
| **Índice**                   | **Índice**                      | Usado para otimizar as operações de busca e recuperação de dados, similar em ambos.           |

## Exemplo Prático

### Documento em MongoDB
Representa uma única instância de dados, contendo campos que são pares chave-valor exemplo:

```json
{
  "name": "Bob Esponja",
  "Age": 30,
  "type": "outros"
}
```
Este documento é similar a uma tupla/registro em uma tabela SQL, onde cada informação (name, age, type) seria armazenada em sua respectiva coluna.

**Coleção em MongoDB:**

Agrupa documentos relacionados, uma coleção de usuarios pode conter documentos de vários usuários, isso é equivalente a uma tabela de usuários em um banco de dados SQL.

**Estrutura no MongoDB:**
```json
[
  {
    "name": "Bob Esponja",
    "Age": 30,
    "type": "outros"
  },
  {
    "name": "Patrick Estrela",
    "Age": 28,
    "type": "outros"
  },
  {
    "name": "Sandy Bochechas",
    "Age": 25,
    "type": "outros"
  },
  {
    "name": "Seu Sirigueijo",
    "Age": 55,
    "type": "outros"
  }
]
```

**Estrutura no SQL:**
```
| ID | name           | Age | type  |
|----|----------------|-----|-------|
| 1  | Bob Esponja    |  30 | outros|
| 2  | Patrick Estrela|  28 | outros|
| 3  | Sandy Bochechas|  25 | outros|
| 4  | Seu Sirigueijo |  55 | outros|
```

# Embedding/Linking em MongoDB vs. JOIN em SQL

Este documento fornece uma visão geral sobre as técnicas de relacionamento de dados em MongoDB (embedding e linking) e como elas se comparam com a operação JOIN em bancos de dados SQL.

## Embedding e Linking em MongoDB

MongoDB permite relacionar dados usando duas principais abordagens: embedding (incorporação) e linking (vinculação).

### Embedding (Incorporação)

Embedding envolve armazenar dados relacionados dentro do mesmo documento. É útil para dados que são acessados juntos com frequência, melhorando a performance ao evitar múltiplas consultas.

```json
{
  "nome": "Bob Esponja",
  "endereco": {
    "rua": "Abacaxi",
    "numero": 124
  }
}
```

### Linking (Vinculação)
Linking refere-se ao armazenamento de referências entre documentos diferentes, permitindo relações mais flexíveis e normalizadas entre os dados, similar ao conceito de chaves estrangeiras em SQL.
 ```json
 {
  "nome": "Bob Esponja",
  "enderecoId": "endereco123"
}
```

### Join SQL:
```sql
SELECT P.nome, E.rua
FROM Personagens P
JOIN Endereco E ON P.enderecoId = E.ID
```


      