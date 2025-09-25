# Start Example - API REST com Spring Boot e MongoDB

Este é um projeto de exemplo de uma API REST desenvolvida com Spring Boot e MongoDB, criado para a disciplina de Programação Backend para Microsserviços do IFTM.

## 📋 Pré-requisitos

- **Java 17** ou superior
- **Maven 3.6+**
- **MongoDB** (local ou MongoDB Atlas)
- **Git**

## 🚀 Tecnologias Utilizadas

- **Spring Boot 3.5.6**
- **Spring Data MongoDB**
- **Spring Web**
- **Spring Boot Actuator**
- **Lombok** (para reduzir código boilerplate)
- **MongoDB** (banco de dados NoSQL)

## ⚙️ Configuração do Ambiente

### 1. Clone o repositório

### 2. Configure o MongoDB

#### Opção A: MongoDB Local

1. Instale o MongoDB Community Server
2. Inicie o serviço MongoDB:
   ```cmd
   net start MongoDB
   ```

#### Opção B: MongoDB Atlas (Cloud)

1. Crie uma conta no [MongoDB Atlas](https://cloud.mongodb.com/)
2. Configure seu cluster
3. Atualize o `application.properties` com sua URI de conexão

### 3. Configure as propriedades da aplicação

Edite o arquivo `src/main/resources/application.properties`:

```properties
spring.application.name=start-example

# MongoDB Local
spring.data.mongodb.uri=mongodb://localhost:27017
spring.data.mongodb.database=aula04set25-LAURA

# OU MongoDB Atlas
# spring.data.mongodb.uri=mongodb+srv://usuario:senha@cluster.mongodb.net/nome-do-banco

spring.data.mongodb.auto-index-creation=true
```

## 🏃‍♂️ Como Executar

### Usando Maven Wrapper (Recomendado)

```bash
./mvnw spring-boot:run        # Linux/Mac
.\mvnw spring-boot:run        # Windows
```

### Usando Maven

```bash
mvn spring-boot:run
```

A aplicação estará disponível em: `http://localhost:8080`

## 📡 Endpoints da API

| Método | Endpoint                | Descrição                  |
| ------ | ----------------------- | -------------------------- |
| GET    | `/api/v1/users`         | Lista todos os usuários    |
| GET    | `/api/v1/users/id/{id}` | Busca usuário por ID       |
| POST   | `/api/v1/users`         | Cria novo usuário          |
| PUT    | `/api/v1/users`         | Atualiza usuário existente |
| DELETE | `/api/v1/users/id/{id}` | Remove usuário por ID      |

## 🏗️ Estrutura do Projeto

```
src/
├── main/
│   ├── java/com/iftm/start_example/
│   │   ├── StartExampleApplication.java      # Classe principal
│   │   ├── controllers/
│   │   │   └── UserController.java           # Controlador REST
│   │   ├── models/
│   │   │   ├── User.java                     # Modelo de usuário
│   │   │   ├── Address.java                  # Modelo de endereço
│   │   │   └── dto/
│   │   │       └── UserDTO.java              # DTO para transferência de dados
│   │   ├── repositories/
│   │   │   └── UserRepository.java           # Interface do repositório
│   │   └── services/
│   │       └── UserService.java              # Lógica de negócio
│   └── resources/
│       └── application.properties            # Configurações da aplicação
└── test/
    └── java/com/iftm/start_example/
        └── first-example-iftm.postman_collection.json # Coleção Postman
```

## 📊 Modelo de Dados

### User

```json
{
  "id": "ObjectId gerado automaticamente",
  "name": "String",
  "age": "Integer",
  "address": {
    "street": "String",
    "number": "Integer"
  }
}
```

## 🔧 Testando com Postman

1. Importe o arquivo `src/test/java/com/iftm/start_example/first-example-iftm.postman_collection.json`
2. Execute as requisições da coleção

---

Este projeto é desenvolvido para fins educacionais.
