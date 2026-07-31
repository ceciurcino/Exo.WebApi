# 🚀 Exo.WebApi

> **Exo.WebApi** é uma API RESTful desenvolvida em **C# / .NET** como parte da atividade de consolidação do curso de **Desenvolvimento Full Stack**. O projeto consiste no gerenciamento e controle de projetos/usuários, implementando rotas CRUD completas, persistência de dados e autenticação segura baseada em **JWT (JSON Web Token)**.

---

## 📌 Sumário
- [Recursos e Funcionalidades](#-recursos-e-funcionalidades)
- [🛠️ Tecnologias Utilizadas](#️-tecnologias-utilizadas)
- [📁 Estrutura do Projeto](#-estrutura-do-projeto)
- [⚙️ Pré-requisitos](#️-pré-requisitos)
- [🚀 Como Executar o Projeto](#-como-executar-o-projeto)
- [📍 Endpoints da API](#-endpoints-da-api)
- [🔐 Autenticação JWT](#-autenticação-jwt)
- [👩‍💻 Autora](#-autora)

---

## 💻 Recursos e Funcionalidades

- 🔄 **CRUD de Projetos**: Criação, listagem, atualização e remoção de registros de projetos.
- 👤 **CRUD / Gestão de Usuários**: Cadastro e gerenciamento de permissões de acesso.
- 🔒 **Autenticação & Autorização (JWT)**: Login com geração de Token Bearer para proteção de rotas restritas.
- 🗄️ **Mapeamento Objeto-Relacional (ORM)**: Utilização do **Entity Framework Core** para comunicação com o banco de dados SQL Server.
- 📖 **Documentação Interativa**: Interface **Swagger UI** para testar as requisições de forma simples e rápida.

---

## 🛠️ Tecnologias Utilizadas

- **Linguagem**: C#
- **Framework Principal**: .NET / ASP.NET Core Web API
- **ORM**: Entity Framework Core
- **Banco de Dados**: Microsoft SQL Server
- **Autenticação**: JSON Web Token (JWT) / System.IdentityModel.Tokens.Jwt
- **Documentação de API**: Swashbuckle / Swagger UI

---

## 📁 Estrutura do Projeto

```text
Exo.WebApi/
├── Contexts/          # Configuração do DbContext e conexão com o Banco de Dados
├── Controllers/       # Controladores da API (ProjetosController, UsuariosController, etc.)
├── Models/            # Classes de domínio e entidades
├── Repositories/      # Padrão Repository para regras de acesso a dados
├── Properties/        # Configurações de inicialização (launchSettings.json)
├── appsettings.json   # Configurações do ambiente e Connection Strings
└── Program.cs         # Ponto de entrada da aplicação e Injeção de Dependências

⚙️ Pré-requisitos
Antes de iniciar, certifique-se de ter instalado em sua máquina:

.NET SDK 6.0+

SQL Server ou SQL Server Express / LocalDB

Ferramenta para testes de API (opcional): Postman ou Insomnia (ou utilizar o próprio Swagger)

IDE de sua preferência: Visual Studio Code ou Visual Studio

Studio

## 🚀 Como Executar o Projeto

### 1. Clonar o repositório

```bash
git clone https://github.com/ceciurcino/Exo.WebApi.git
cd Exo.WebApi

2. Configurar a String de Conexão
Abra o arquivo appsettings.json e ajuste a chave ConnectionStrings para indicar o seu servidor local do SQL Server:
```json
"ConnectionStrings": {
  "ExoContext": "Server=localhost\\SQLEXPRESS;Database=ExoWebApi;Trusted_Connection=True;TrustServerCertificate=True;"
}
```

3. Aplicar as Migrations / Atualizar o Banco de Dados
```bash
dotnet ef database update
```

4. Executar a aplicação
```bash
dotnet run
```

A aplicação estará rodando no endereço padrão (ex: https://localhost:7--- ou http://localhost:5---).
Acesse a documentação do Swagger abrindo no seu navegador:

```plaintext
https://localhost:<PORTA>/swagger
```

---

### 📁 Projetos

| Método | Endpoint | Descrição | Requer Auth? |
| :--- | :--- | :--- | :--- |
| `GET` | `/api/projetos` | Lista todos os projetos cadastrados | ❌/✔️ |
| `GET` | `/api/projetos/{id}` | Busca um projeto por ID | ❌/✔️ |
| `POST` | `/api/projetos` | Cadastra um novo projeto | ✔️ Sim |
| `PUT` | `/api/projetos/{id}` | Atualiza os dados de um projeto | ✔️ Sim |
| `DELETE` | `/api/projetos/{id}` | Remove um projeto do sistema | ✔️ Sim |

---

### 👤 Usuários

| Método | Endpoint | Descrição | Requer Auth? |
| :--- | :--- | :--- | :--- |
| `GET` | `/api/usuarios` | Lista todos os usuários | ✔️ Sim |
| `POST` | `/api/usuarios` | Cadastra um novo usuário | ❌ Não |
| `PUT` | `/api/usuarios/{id}` | Atualiza informações do usuário | ✔️ Sim |
| `DELETE` | `/api/usuarios/{id}` | Remove um usuário | ✔️ Sim |

🔐 Autenticação JWT
Para testar endpoints protegidos no Swagger ou no Postman:

1. Faça uma requisição POST no endpoint /api/login enviando email e senha.

2. Copie o token retornado no corpo da resposta.

3. No Swagger, clique no botão Authorize no canto superior direito e cole o token no formato:
```plaintext
Bearer <SEU_TOKEN_AQUI>
```

4. Clique em Authorize e teste as rotas protegidas.

👩‍💻 Autora

Desenvolvido por Cecília Urcino

Estudante de Análise e Desenvolvimento de Sistemas | Desenvolvedora Full Stack / Front-end / QA
