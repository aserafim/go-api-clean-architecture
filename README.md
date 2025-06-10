---

```markdown
# 🧩 Go API – Clean Architecture

Este projeto é uma aplicação de estudo desenvolvida em Go como parte da formação FullCycle. A API implementa operações completas de CRUD para **produtos** e manipulação de **usuários**, utilizando uma arquitetura modular baseada em princípios de Clean Architecture, com testes unitários e documentação Swagger.

Repositório: [github.com/seu-usuario/go-api-clean-architecture](https://github.com/seu-usuario/go-api-clean-architecture)

---

## ⚙️ Tecnologias Utilizadas

- [Golang](https://golang.org/)
- [Chi](https://github.com/go-chi/chi) – HTTP router leve e idiomático
- [Swaggo](https://github.com/swaggo/swag) – Geração de documentação Swagger
- [SQLite](https://www.sqlite.org/index.html)
- [Godotenv](https://github.com/joho/godotenv) – Carregamento de variáveis de ambiente
- Testes com `testing` nativo do Go

---

## 📁 Estrutura do Projeto

```

.
├── cmd/server/              # Ponto de entrada da aplicação
│   ├── main.go              # Inicialização do servidor
│   ├── .env                 # Variáveis de ambiente
│   └── test.db              # Banco de dados SQLite
│
├── internal/
│   ├── entity/              # Entidades de domínio (User, Product)
│   ├── dto/                 # Objetos de transferência de dados
│   ├── database/            # Camada de acesso a dados (implementações e interfaces)
│   └── webserver/handlers/  # Handlers das rotas HTTP
│
├── docs/                    # Documentação Swagger gerada
├── pkg/                     # Pacotes utilitários (e.g. ID generator)
├── test/                    # Arquivos de teste HTTP para o Insomnia/Postman
└── go.mod / go.sum          # Gerenciamento de dependências

````

---

## 🚀 Como Rodar o Projeto

### Pré-requisitos

- Go 1.18 ou superior
- (Opcional) [Air](https://github.com/cosmtrek/air) para hot reload

### Passos

```bash
# Clone o repositório
git clone https://github.com/seu-usuario/go-api-clean-architecture.git
cd go-api-clean-architecture

# Instale as dependências
go mod tidy

# Execute o servidor
go run cmd/server/main.go
````

A API será exposta em `http://localhost:8080`.

---

## 📖 Documentação Swagger

Acesse a documentação interativa da API:

```
http://localhost:8080/docs/index.html
```

Para gerar novamente os arquivos:

```bash
swag init -g cmd/server/main.go -o docs
```

---

## 📌 Endpoints da API

### 📂 Users

| Método | Rota               | Descrição                    |
| ------ | ------------------ | ---------------------------- |
| POST   | `/users/get_token` | Autenticar e gerar token JWT |
| POST   | `/users`           | Criar um novo usuário        |

### 📦 Products

| Método | Rota             | Descrição                   |
| ------ | ---------------- | --------------------------- |
| GET    | `/products`      | Listar todos os produtos    |
| GET    | `/products/{id}` | Buscar produto por ID       |
| POST   | `/products`      | Criar um novo produto       |
| PUT    | `/products/{id}` | Atualizar produto existente |
| DELETE | `/products/{id}` | Deletar produto por ID      |

---

## 🛠️ Funcionalidades

* Clean Architecture (camadas bem definidas)
* Geração automática de UUID
* Documentação Swagger
* Camada de banco de dados separada por interfaces
* Middleware JWT para autenticação de rotas (em rotas protegidas)
* Testes unitários

---

## 🧪 Testes

Execute os testes com:

```bash
go test ./...
```

Testes implementados para camada de entidades e repositórios.

---
