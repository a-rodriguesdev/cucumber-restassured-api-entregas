# 🧪 Testes Automatizados — API de Entregas

Automação de testes de API REST com **Java**, **Cucumber (BDD)**, **Rest Assured** e **JUnit**, validando os endpoints de uma API de entregas executada em **Docker**.

Projeto acadêmico desenvolvido no curso de **Análise e Desenvolvimento de Sistemas — FIAP** (Fase 7).

---

## 📋 Sobre o projeto

Os cenários de teste são escritos em **Gherkin** (linguagem natural, em português) e automatizados em Java. Eles cobrem as principais operações da API de entregas:

- ✅ Cadastro de entregas (caminho feliz e cenários de erro)
- ✅ Validação do status code e do corpo das respostas
- ✅ Exclusão de entregas
- ✅ Validação de contrato (JSON Schema)

## 🛠️ Tecnologias

| Tecnologia | Versão | Uso |
|---|---|---|
| Java | 21 | Linguagem |
| Maven | 3.x | Build e dependências |
| Cucumber Java / JUnit | 7.18.1 | BDD e execução dos cenários |
| Rest Assured | 5.5.0 | Requisições HTTP e validações |
| Gson | 2.11.0 | Serialização/deserialização JSON |
| Lombok | 1.18.34 | Redução de código repetitivo |
| Docker | — | Execução da API sob teste |

## 📁 Estrutura

```
src
└── test
    ├── java
    │   ├── model       # Classes que representam o corpo das requisições
    │   ├── services    # Lógica de chamada aos endpoints da API
    │   └── steps       # Step definitions (ligação Gherkin → Java)
    └── resources
        └── features    # Cenários de teste em Gherkin (.feature)
```

## ▶️ Como executar

### Pré-requisitos

- Java 21
- Maven
- Docker Desktop

### 1. Subir a API de entregas no Docker

No diretório do projeto da API (`ON_TDS_JAVA_ADVANCED_MICROSSERVICES_ENTREGAS`):

```bash
docker build -t api-entregas-image .
docker run -d --name my-app-entregas -p 8080:8080 api-entregas-image
```

Verifique se a API está no ar: http://localhost:8080/entregas/health

Documentação (Swagger): http://localhost:8080/swagger-ui/index.html

### 2. Rodar os testes

Na raiz deste projeto:

```bash
mvn clean test
```

Ou, pelo IntelliJ, clique no ▶️ ao lado de um cenário no arquivo `.feature`.

## 👩‍💻 Autora

**Évelyn Rodrigues**
[GitHub](https://github.com/a-rodriguesdev) · 