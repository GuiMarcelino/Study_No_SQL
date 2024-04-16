# Comandos para collections(tabelas):

- Criar uma Collection com regras default:
  ```json
  db.createCollection("minhaColecao")
  ```

- Criar uma Collection quando quiser definir opções específicas, como tamanho máximo ou regras de validação:
  ```json
  db.createCollection("people", {
    capped: true,        // Torna a coleção capped
    size: 5242880,       // Define o tamanho máximo da coleção para 5MB
    max: 5000,           // Limita o número de documentos a 5000
    validator: {         // Define regras de validação para os documentos
      $jsonSchema: {
        bsonType: "object",
        required: ["nome", "email"],  // Campos obrigatórios
        properties: {
          nome: {
            bsonType: "string",
            description: "deve ser uma string e é obrigatório"
          },
          email: {
            bsonType: "string",
            pattern: "^.+@.+\..+$",  // Valida o formato do email
            description: "deve ser uma string no formato de email e é obrigatório"
          },
          age: {
            bsonType: "int",
            minimum: 0,
            maximum: 120,
            description: "deve ser um inteiro entre 0 e 120"
          }
        }
      }
    },
    validationLevel: "strict",  // Validação estrita aplicada a todas as operações
    validationAction: "error"   // Rejeita documentos que não passam na validação
  });
  ```

- Alterar uma Collection:
  - Para modificar configurações de uma coleção existente, como sua capacidade ou regras de validação, você usa o comando **collMod**, este comando pode ser usado para modificar várias configurações da coleção, exemplo vamos atualizar o limite máximo da idade de 120 para 150.

    ```json
    db.runCommand({
      collMod: "people",
      validator: {
        $jsonSchema: {
          bsonType: "object",
          required: ["name", "email"],
          properties: {
            name: {
              bsonType: "string",
              description: "must be a string and is required"
            },
            email: {
              bsonType: "string",
              pattern: "^.+@.+\..+$",
              description: "must be a string in email format and is required"
            },
            age: {
              bsonType: "int",
              minimum: 0,
              maximum: 150,  // Atualizando idade maxima de 120 para 150
              description: "must be an integer between 0 and 150"
            }
          }
        }
      },
      validationLevel: "strict",
      validationAction: "error"
    });
    ```
- Deletar uma Collection:
  - Ponto de observação esse comando removerá completamente a coleção e seus índices do banco de dados:
    ```json
      db.userRecords.drop()
    ```

- visualizar Collections:
  - Visualizar todas:
    ```json
      show collections
    ```

    - Visualizar todas e suas propriedades e validações:
    ```json
      db.getCollectionInfos()
    ```

      - Visualizar uma collection especifíca e suas e validações:
    ```json
      db.getCollectionInfos({name: "people"})
    ```


# Inserção de documentos:
- **INSERT:**

  - Usando o **insertOne:**
    - Para inserir um único documento:
      ```json
      db.people.insertOne({name: 'Guilherme', age: 28});
      ```
  - Usando o **insertMany:**
    - Para inserir múltiplos documentos de uma vez:
      ```json
        db.people.insertMany([
          {name: 'Tom', age: 28},
          {name: 'John', age: 25},
          {name: 'Kathy', age: 23}
        ]);
      ```
