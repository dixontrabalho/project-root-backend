## Backend API - Project Root
## 1. Descrição do Projeto

Este projeto consiste em uma API backend RESTful desenvolvida para gerenciamento de usuários, produtos e categorias. A aplicação fornece autenticação baseada em token (JWT), controle de acesso e operações completas de CRUD.

O sistema foi projetado com foco em escalabilidade, organização modular e boas práticas de desenvolvimento backend, utilizando arquitetura baseada em camadas (controllers, services, models, routes).

## 2. Tecnologias e Dependências
Stack Principal
Node.js (>= 18.x recomendado)
Express.js 5.x
PostgreSQL
Sequelize (ORM)
Bibliotecas e Ferramentas
bcryptjs – Hash de senhas
jsonwebtoken – Autenticação via JWT
dotenv – Gerenciamento de variáveis de ambiente
cors – Controle de acesso HTTP
swagger-jsdoc / swagger-ui-express – Documentação da API
Desenvolvimento e Testes
jest – Testes automatizados
supertest – Testes de integração HTTP
nodemon – Hot reload em desenvolvimento
sequelize-cli – Gerenciamento do banco

3. Instalação e Setup
Pré-requisitos
Node.js instalado
PostgreSQL em execução
Gerenciador de pacotes (npm ou yarn)
Passos
# Clone o repositório
git clone <https://github.com/dixontrabalho/project-root-backend>

# Acesse a pasta do projeto
cd project-root

# Instale as dependências
npm install
Variáveis de Ambiente

Crie um arquivo .env na raiz do projeto:

PORT=3000

DB_HOST=localhost
DB_USER=postgres
DB_PASSWORD=sua_senha
DB_NAME=nome_do_banco
DB_PORT=5432

JWT_SECRET=sua_chave_secreta
4. Como Usar
Rodar em ambiente de desenvolvimento
npm run dev
Rodar em produção
npm start

A API estará disponível em:
http://localhost:3000


## 5. Estrutura do Projeto

src/
├── app.js                 # Configuração do Express
├── server.js              # Inicialização do servidor
│
├── config/
│   └── database.js        # Configuração do banco
│
├── controllers/           # Lógica de entrada (HTTP)
│   ├── AuthController.js
│   ├── UserController.js
│   ├── ProductController.js
│   └── CategoryController.js
│
├── services/              # Regras de negócio
│   └── ProductService.js
│
├── models/                # Modelos do Sequelize
│   ├── User.js
│   ├── Product.js
│   ├── Category.js
│   ├── ProductImage.js
│   └── ProductOption.js
│
├── routes/                # Definição de rotas
│   ├── userRoutes.js
│   ├── productRoutes.js
│   └── categoryRoutes.js
│
├── middleware/
│   └── auth.js            # Middleware de autenticação
│
├── database/
│   └── index.js           # Inicialização ORM
│
tests/
├── user.test.js
├── product.test.js
└── category.test.js

## 6. Configuração
Banco de Dados

Configure o banco PostgreSQL conforme o .env.

Sequelize

Para rodar migrations e seeds (se aplicável):

npx sequelize-cli db:migrate
npx sequelize-cli db:seed:all
## 7. Testes
Executar testes
npm test
Tecnologias utilizadas
Jest
Supertest
Tipos de testes
Testes de integração de endpoints
Validação de regras de negócio

## 8. API / Endpoints
Autenticação
POST /auth/login
Request:
{
  "email": "user@email.com",
  "password": "123456"
}

Response:
{
  "token": "jwt_token"
}
Usuários
POST /users

Criação de usuário

GET /users

Listagem de usuários (requer autenticação)

Produtos
GET /products

Lista todos os produtos

POST /products

Cria um novo produto

GET /products/:id

Detalhes de um produto

Categorias
GET /categories

Lista categorias

POST /categories

Cria categoria

Autenticação

Rotas protegidas utilizam header:

Authorization: Bearer <token>
10. Licença

Este projeto está licenciado sob a licença ISC.

11. Autores / Contato

Autor:
Dixon Brito de Sá com a orientação di Nazaré Almeida!

Contato:

Email: dixon.trabalho@gmail.com
GitHub: https://github.com/dixontrabalho