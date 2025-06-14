# 🎮 GG API – Backend do App de Avaliação de Jogos

> Backend da plataforma social para gamers, inspirada no Letterboxd, com foco em avaliações, listas e descobertas de jogos.

![Java](https://img.shields.io/badge/Java-17-blue?style=flat-square&logo=java)
![Spring Boot](https://img.shields.io/badge/Spring_Boot-3.x-success?style=flat-square&logo=spring-boot)
![Clean Architecture](https://img.shields.io/badge/Clean%20Architecture-%E2%9C%94%EF%B8%8F-blueviolet?style=flat-square)
![Keycloak](https://img.shields.io/badge/Auth-Keycloak-important?style=flat-square&logo=keycloak)

---

## 📚 Descrição

A **GG API** é o núcleo do backend de uma plataforma de avaliações de jogos, que permite que usuários:

- Avaliem e comentem jogos
- Criem listas personalizadas (ex: "Meus RPGs favoritos")
- Sigam amigos e vejam atividades recentes
- Autentiquem-se com Google ou Steam via Keycloak

Este repositório contém a API RESTful construída com **Spring Boot**, estruturada usando princípios da **Clean Architecture**, para alta testabilidade e desacoplamento.

---

## ⚙️ Tecnologias

- **Java 21**
- **Spring Boot 3.x**
- **Spring Data JPA**
- **PostgreSQL** (banco de dados relacional)
- **Keycloak** (autenticação e autorização)
- **Docker** (ambiente local e deployment)
- **Clean Architecture** (organização em camadas)
- **Swagger/OpenAPI** (documentação da API)
- **JUnit** (testes de unidade)

---

## 🏗️ Estrutura do Projeto
O projeto seguirá a estrutura abaixo, podendo sofrer alterações ao longo do desenvolvimento, conforme o negócio necessitar:

```bash
src
├── domain
│   ├── model           -> Entidades (ex: Game, Review, User)
│   ├── repository      -> Interfaces (ex: ReviewRepository)
│   └── service         -> Regras de negócio puras (ex: ReviewDomainService)
├── application
│   ├── usecase         -> Casos de uso (ex: CriarReviewUseCase)
│   └── dto             -> DTOs de entrada/saída dos casos de uso
├── infrastructure
│   ├── config          -> Beans, JWT, Swagger, etc.
│   ├── persistence     -> Implementações dos repositórios (ex: JPA)
│   ├── external        -> APIs externas (ex: RAWG)
│   └── security        -> Keycloak, OAuth2, etc.
└── interface
    ├── controller      -> REST Controllers
    └── mapper          -> Conversores entre DTOs e Entidades
```

---

## 🔐 Autenticação
A autenticação é feita com Keycloak, com suporte a:

* Login com Google (OAuth2)
* Login com Steam
* Tokens JWT para proteger os endpoints

---

## 🚀 Como Executar Localmente

#### Pré-requisitos

* Java 21
* Docker + Docker Compose
* Maven 3.9+

#### Passos
```bash
# 1. Clone o repositório
git clone https://github.com/ronny-souza/gg-api.git
cd gg-api

# 2. Suba os containers do Keycloak e PostgreSQL
docker-compose up -d

# 3. Execute a aplicação
./mvnw spring-boot:run
```

## 🧪 Testes
```bash
./mvnw test
```

## 📒 Documentação da API
Acesse via Swagger:

http://localhost:8080/swagger-ui.html
