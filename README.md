# 🍕 Sistema de Gestão de Pizzaria

Aplicação web full-stack para gerenciamento das operações de uma pizzaria, desenvolvida com **Node.js, Express e TypeScript**.

O sistema permite gerenciar produtos e clientes, realizar pedidos e acompanhar informações de vendas por meio de um painel administrativo. O backend é organizado em camadas seguindo o padrão **Model-Service-Controller**, com persistência de dados em **PostgreSQL**.

## 🖥️ Funcionalidades

### 🍕 Gestão de produtos

* Cadastro, consulta, edição e exclusão de produtos (**CRUD**);
* Organização do cardápio por categorias;
* Filtro dinâmico de produtos na interface.

### 👤 Gestão de clientes

* Cadastro de novos clientes;
* Consulta de clientes durante a finalização dos pedidos.

### 🛒 Pedidos

* Carrinho de compras com persistência utilizando `localStorage`;
* Associação de pedidos a clientes;
* Seleção de múltiplos produtos;
* Fluxo de checkout;
* Geração de comprovantes dos pedidos realizados.

### 📊 Painel administrativo

* Área dedicada ao acompanhamento das vendas;
* Processamento do histórico de pedidos;
* Relatórios semanais e mensais;
* Visualização do total de vendas por período.

## 🏗️ Arquitetura

O backend foi estruturado utilizando o padrão **Model-Service-Controller**, separando responsabilidades entre representação dos dados, regras de negócio, tratamento das requisições e definição das rotas.

```text
src/
├── controllers/    # Tratamento das requisições
├── database/       # Configuração da conexão com PostgreSQL
├── models/         # Interfaces e tipos da aplicação
├── routes/         # Definição das rotas
├── services/       # Regras de negócio
└── server.ts       # Inicialização do servidor

public/
├── index.html
├── admin.html
├── script.js
└── admin.js

comprovantes/
└── arquivos gerados pelos pedidos
```

O acesso ao PostgreSQL é centralizado por meio de um `Pool` de conexões, enquanto as configurações do ambiente são fornecidas por **variáveis de ambiente**, evitando manter credenciais diretamente no código-fonte.

## 🛠️ Tecnologias

### Backend

* Node.js
* Express
* TypeScript
* PostgreSQL

### Frontend

* HTML5
* CSS3
* JavaScript

### Infraestrutura e ferramentas

* Docker
* npm
* pgAdmin 4
* Git

## 🚀 Executando o projeto

### Pré-requisitos

Para executar a aplicação localmente, você precisará de:

* Node.js
* npm
* Docker
* PostgreSQL em container

## 1. Clone o repositório

```bash
git clone <URL-DO-REPOSITORIO>
cd <NOME-DO-REPOSITORIO>
```

## 2. Instale as dependências

```bash
npm install
```

## 3. Configure as variáveis de ambiente

Crie um arquivo `.env` na raiz do projeto utilizando `.env.example` como referência:

```env
DB_USER=seu_usuario
DB_HOST=localhost
DB_NAME=db_pizzaria
DB_PASSWORD=sua_senha
DB_PORT=5432
```

> O arquivo `.env` não deve ser versionado. Mantenha-o listado no `.gitignore`.

## 4. Inicie o PostgreSQL

Exemplo utilizando Docker:

```bash
docker run -d \
  --name sistema-pizzaria \
  -e POSTGRES_USER=seu_usuario \
  -e POSTGRES_PASSWORD=sua_senha \
  -e POSTGRES_DB=db_pizzaria \
  -p 5432:5432 \
  postgres:latest
```

Os valores utilizados na criação do container devem corresponder às configurações definidas no seu arquivo `.env`.

## 5. Execute a aplicação

Para iniciar em modo de desenvolvimento:

```bash
npm run dev
```

O servidor será iniciado em:

```text
http://localhost:3000
```

## 🔐 Configuração e segurança

As credenciais de acesso ao PostgreSQL são carregadas por meio de variáveis de ambiente.

O repositório disponibiliza apenas um arquivo `.env.example` com a estrutura necessária para configuração. O arquivo `.env` real é ignorado pelo Git para evitar o versionamento de credenciais locais.

Exemplo:

```env
DB_USER=
DB_HOST=localhost
DB_NAME=db_pizzaria
DB_PASSWORD=
DB_PORT=5432
```

## 🧠 Conceitos aplicados

Durante o desenvolvimento foram aplicados conceitos de:

* desenvolvimento web full-stack;
* APIs e requisições HTTP;
* arquitetura em camadas;
* operações CRUD;
* programação com TypeScript;
* modelagem e persistência de dados com PostgreSQL;
* gerenciamento de conexões com banco de dados;
* manipulação de estado no frontend com `localStorage`;
* conteinerização com Docker;
* separação entre configuração e código por meio de variáveis de ambiente;
* versionamento com Git.

## 📈 Possíveis evoluções

Algumas melhorias que podem ser incorporadas ao projeto:

* testes automatizados;
* autenticação e autorização do painel administrativo;
* validação mais robusta das entradas da API;
* tratamento centralizado de erros;
* migrações de banco de dados;
* utilização de Docker Compose para simplificar a configuração do ambiente;
* melhorias de responsividade e experiência do usuário.
---

Desenvolvido como projeto acadêmico durante a graduação em **Ciência da Computação**, com foco na aplicação prática de TypeScript e conceitos de desenvolvimento web full-stack.
