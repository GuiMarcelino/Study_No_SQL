# Json e Bson características:

## Json:
- O JSON é um formato que armazena informações estruturadas e é principalmente usado para transferir dados entre um servidor e um cliente.

## Sintaxe do JSON:
- Existem dois elementos centrais em um objeto JSON: Keys (chaves) e Values (valores).
  
  - **Keys** devem ser strings que contêm uma sequência de caracteres cercadas por aspas.

  - **Values** são um tipo válido de dados JSON, eles podem ter um formato de array, object, string, boolean, number ou null.

  ## Tipos do valores:

- **Array:**
  - Um array é uma coleção ordenada de valores. É cercado por colchetes [] e cada valor dentro é separado por uma vírgula, um valor de array pode conter objetos JSON, isso significa que ele usa o mesmo conceito de key/value exemplo:
```json
"students":[      
  {"firstName":"Guilherme", "lastName":"Marcelino"},
  {"firstName":"Carlos", "lastName":"Silva"},
  {"firstName":"Ana", "lastName":"Cooper"}
]
```

- **Object:**
    - Um objeto contém uma key e value, tem dois pontos depois de cada key e uma vírgula depois de cada value, que também diferencia cada objeto ambos estão dentro de aspas exemplo:

```json
"employees": {"firstName":"Guilherme", "lastName":"Marcelino"}
```

- **Strings:**
    - Uma string é uma sequência definida de zero ou mais caracteres Unicode é colocado entre duas aspas duplas. exemplo:

```json
"firstName":"Guilherme"
```

- **Number:**
    - Number em JSON deve ser do tipo inteiro(integer) ou um tipo fracionado(float):

```json
{"age": 30}
```

- **Boolean:**
    - Boolean você pode usar as opções true (verdadeiro) ou false (falso) exemplo:

```json
{"married": true}
```

- **Null:**
  - Boolean você pode usar as opções true (verdadeiro) ou false (falso) exemplo:

```json
{"bloodType": null}
```

## Tipos BSON Adicionais Suportados pelo MongoDB:

### O BSON (Binary JSON) é uma extensão do JSON, e foi protagonizado inicialmente pelo MongoDB, um NoSQL Document DB, que o usa para performar o armazenamento de dados, além de todos os dados do JSON (null, String, Number, Array, Object), o BSON suporta:

- MinKey, MaxKey, Timestamp — tipos utilizados internamente no MongoDB:

```json
{
  "_id": ObjectId("507f191e810c19729de860ea"),
  "nome": "Item Especial",
  "categoria": "Especial",
  "ordem": MinKey(),
  "ultima_atualizacao": Timestamp(1615296000)
}

{
  "_id": ObjectId("507f191e810c19729de860eb"),
  "nome": "Item Comum",
  "categoria": "Comum",
  "ordem": 100,
  "ultima_atualizacao": Timestamp(1615296000)
}
```

- BinData — Array de Bytes para Dados Binários:

```json
{
  "_id": ObjectId("507f1f77bcf86cd799439011"),
  "arquivo": BinData(0, "SGVsbG8gV29ybGQ=")
}
```

- ObjectId — Identificador Único de um Registro do MongoDB:

```json
{
  "_id": ObjectId("507f1f77bcf86cd799439011"),
  "nome": "Item Exemplo",
  "descricao": "Este é um item de exemplo."
}
```

- Date — Representação de Data:

```json
{
  "_id": ObjectId("507f1f77bcf86cd799439011"),
  "nome": "Item Exemplo",
  "descricao": "Este é um item de exemplo."
}
```

# Diferenças entre JSON e BSON:

- Formato de Armazenamento:
  - JSON é um formato de texto legível por humanos, enquanto BSON é uma representação binária para armazenamento e transferência de dados eficientes.

- Tamanho:
  - JSON suporta tipos básicos como strings, números, objetos, arrays, booleanos e null. BSON estende essa lista com tipos adicionais como Date, Binary Data, e ObjectID, tornando-o mais versátil para diferentes tipos de dados.

- Velocidade:
  - BSON é projetado para ser eficiente na codificação e decodificação, o que pode ser particularmente benéfico em ambientes onde a performance de leitura e escrita é crítica.

- Uso:
  - JSON é amplamente utilizado para troca de dados na web devido à sua simplicidade e legibilidade. BSON, por outro lado, é especificamente otimizado para armazenamento e manipulação de documentos no MongoDB, oferecendo velocidades mais rápidas e suporte a uma gama maior de tipos de dados.