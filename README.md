<div align="center">
<img src="https://img.shields.io/badge/Spring_Boot-F2F4F9?style=for-the-badge&logo=spring-boot" alt="Spring Boot" />
  <img src="https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white" alt="Java" />
  <img src="https://img.shields.io/badge/PostgreSQL-316192?style=for-the-badge&logo=postgresql&logoColor=white" alt="PostgreSQL" />
  <img src="https://img.shields.io/badge/Maven-C71A36?style=for-the-badge&logo=apachemaven&logoColor=white" alt="Maven" />
  <img src="https://img.shields.io/badge/JWT-000000?style=for-the-badge&logo=json-web-tokens&logoColor=white" alt="JWT" />
  <img src="https://img.shields.io/badge/Swagger-85EA2D?style=for-the-badge&logo=swagger&logoColor=black" alt="Swagger" />
</div>

🚗 DesenvolvimentoApiVeiculos - API de Gestão de Veículos


Uma API RESTful robusta para gerenciamento de Montadoras e Modelos de Veículos, desenvolvida em Java com Spring Boot, Spring Security (JWT ) e PostgreSQL.

Projeto de backend que simula um sistema de gestão para o setor automotivo. Ele oferece funcionalidades completas para cadastrar, consultar, atualizar e remover informações de montadoras e seus respectivos modelos de veículos, com um foco especial em segurança através da autenticação JWT e documentação interativa com Swagger.




🚀 Principais Funcionalidades

Esta API foi projetada com uma arquitetura limpa e escalável, seguindo as melhores práticas de desenvolvimento:

•
Gestão de Montadoras: Operações CRUD completas para o cadastro de montadoras, incluindo a possibilidade de filtrar por país de origem.

•
Gestão de Modelos de Veículos: Operações CRUD para modelos, associando-os a uma montadora existente.

•
Autenticação e Autorização (JWT): Implementação de segurança robusta utilizando JSON Web Tokens (JWT) para proteger os endpoints da API, garantindo que apenas usuários autenticados e autorizados possam acessar os recursos.

•
Documentação Interativa: Integração com Springdoc OpenAPI (Swagger UI), permitindo a exploração e teste de todos os endpoints da API diretamente pelo navegador.

•
Tratamento de Exceções: Gerenciamento de erros de forma padronizada para fornecer respostas claras e informativas ao cliente da API.




🛠️ Tecnologias e Ferramentas

A aplicação foi construída com um stack moderno e amplamente utilizado no mercado:

| Tecnologia | Descrição |
| --- | --- |
| **Java 25** | Linguagem de programação principal. |
| **Spring Boot 4.0.6** | Framework base para criação da API REST. |
| **Spring Data JPA / Hibernate** | Mapeamento Objeto-Relacional (ORM) e abstração do banco de dados. |
| **PostgreSQL** | Banco de dados relacional (com suporte a colunas JSONB). |
| **Lombok** | Redução de boilerplate (Getters, Setters, Constructors). |
| **Spring Validation** | Validação de dados de entrada via DTOs (`@Valid`, `@NotBlank`, `@NotNull`). |
| **Springdoc OpenAPI** | Geração automática da documentação Swagger UI. |
| **Maven** | Gerenciamento de dependências e build do projeto. |







🏗️ Arquitetura do Projeto

O projeto segue uma arquitetura em camadas bem definida, promovendo a separação de responsabilidades e facilitando a manutenção:

•
controller: Gerencia as requisições HTTP, mapeando URLs para métodos e retornando respostas.

•
service: Contém a lógica de negócio principal, orquestrando as operações e aplicando as regras de validação.

•
repository: Interfaces do Spring Data JPA para interação com o banco de dados.

•
model: Entidades que representam as tabelas do banco de dados (Montadora, Modelo).

•
dto: Data Transfer Objects para entrada e saída de dados, garantindo a segurança e a validação das informações.

•
security: Componentes relacionados à autenticação e autorização JWT (TokenService, FiltroJwtAutenticacao).

•
config: Classes de configuração da aplicação, incluindo Spring Security e Swagger.




🔒 Segurança (Autenticação JWT)

A API implementa um fluxo de autenticação robusto com JWT:

1. Login: O endpoint /api/auth/login recebe credenciais (usuário/senha) e, se válidas, gera um JWT.

2. Geração de Token: O TokenService utiliza a biblioteca java-jwt para criar um token assinado com um segredo, contendo o login do usuário e um tempo de expiração.

3. Filtro de Autenticação: O FiltroJwtAutenticacao intercepta todas as requisições, extrai o token do cabeçalho Authorization e o valida.

4. Autorização: Se o token for válido, o usuário é autenticado no contexto do Spring Security, permitindo o acesso aos endpoints protegidos (/api/**).

