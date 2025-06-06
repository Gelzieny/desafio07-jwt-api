<strong><h1 align="center">🔐 Desafio 07 - API de Pedidos com Autenticação JWT</h1></strong>

<p align="justify">

Este repositório contém a solução para o **Desafio 07** proposto pela [Rocketseat](https://rocketseat.com.br), referente ao módulo **Autenticação JWT e Segurança**. O objetivo é desenvolver uma API de pedidos protegida com autenticação via **JWT**, aplicando os conhecimentos de segurança, autorização e estruturação de APIs RESTful.
</p>

> 🔗 Link do desafio original: [Notion - Desafio 07](https://efficient-sloth-d85.notion.site/Desafio-07-36707f75b62640d8a2cf1c515a665531)  
> 🔗 Repositório do projeto: [GitHub - Gelzieny/desafio07-jwt-api](https://github.com/Gelzieny/desafio07-jwt-api.git)



## 📌 Objetivo

Criar uma **API de pedidos** com as seguintes características:

- Autenticação de usuários via **JWT**
- Apenas usuários autenticados podem acessar seus próprios pedidos
- **CRUD de pedidos** limitado ao usuário autenticado
- Utilização de boas práticas como **MVC**, **validação**, **criptografia de senha** e **segurança na API**

---

## 🔐 Sobre o JWT

Ao fazer login com sucesso, o usuário receberá um **token JWT** contendo:

- `id`: Identificador único do usuário
- `username`: Nome do usuário
- `token`: JWT assinado

Este token deve ser enviado nas requisições subsequentes via `Authorization Header`



## 📁 Estrutura esperada da API

### Usuários

- `POST /register`: Criação de conta com `username` e `senha`
- `POST /login`: Retorna um token JWT válido

### Pedidos

- `GET /orders`: Lista todos os pedidos do usuário autenticado
- `POST /orders`: Cria um novo pedido com descrição
- (opcional) `DELETE /orders/:id`: Remove um pedido do usuário

---

## 🧱 Modelo do Banco de Dados

**Tabela: users**

```bash
| Campo     | Tipo     |
|-----------|----------|
| id        | integer (PK) |
| username  | text     |
| password  | text (criptografada) |

**Tabela: orders**

| Campo       | Tipo     |
|-------------|----------|
| id          | integer (PK) |
| user_id     | integer (FK) |
| description | text     |
| created_at  | datetime |
```

---

## 🛠 Tecnologias utilizadas

- **Python 3.x**
- **Flask** (ou FastAPI/Django REST, conforme sua escolha)
- **JWT (PyJWT)**
- **SQLite** como banco de dados
- **SQLAlchemy** (opcional)
- **bcrypt** para hash de senhas
- **unittest** ou **pytest** para testes

---

## ▶️ Criar ambiente virtual

```bash
  #Clonar o repositório
  git clone https://github.com/seu-usuario/desafio07-jwt-api.git

  cd desafio07-jwt-api
  
  #  Windows (CMD ou PowerShell)
  python -m venv venv && venv\Scripts\activate && pip install -r requirements.txt


  # macOS / Linux (bash/zsh)
  python3 -m venv venv && source venv/bin/activate && pip install -r requirements.txt
```

---

## ✅ Funcionalidades implementadas
  - Registro de usuários com senha criptografada
  - Login com geração de token JWT
  - Proteção de rotas com autenticação
  - Pedidos visíveis apenas para o dono
  - Banco de dados SQLite com tabelas relacionadas
  - Testes automatizados (em progresso)

---

## 🧪 Testes

```bash
  pytest
```

## 💡 Aprendizados

  - Este desafio reforça conceitos fundamentais de segurança em APIs:
  - Autenticação e autorização com JWT
  - Proteção de rotas com decorators/middlewares
  - Boas práticas com senhas e tokens
  - Integração com banco de dados relacional
  - Organização do código usando MVC