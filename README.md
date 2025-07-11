# NLW Agents

Backend API para o projeto NLW Agents, construído com Fastify, TypeScript e PostgreSQL.

## 🚀 Tecnologias

- **Runtime**: Node.js com TypeScript
- **Framework**: Fastify
- **Database**: PostgreSQL com pgvector
- **ORM**: Drizzle ORM
- **Validação**: Zod
- **Linter/Formatter**: Biome
- **Containerização**: Docker

## 📋 Pré-requisitos

- Node.js 18+
- Docker e Docker Compose
- Yarn (recomendado) ou npm

## ⚙️ Configuração

### 1. Clone o repositório
```bash
git clone <repository-url>
cd nlw-agents
```

### 2. Instale as dependências
```bash
yarn install
```

### 3. Configure as variáveis de ambiente
Crie um arquivo `.env` na raiz do projeto:
```env
PORT=3333
DATABASE_URL=postgres://postgres:postgres@localhost:5432/nlw_agents
```

### 4. Inicie o banco de dados
```bash
docker-compose up -d
```

### 5. Execute as migrações
```bash
yarn db:generate
yarn db:migrate
```

### 6. Execute o seed (opcional)
```bash
yarn db:seed
```

## 🏃‍♂️ Executando o projeto

### Desenvolvimento
```bash
yarn dev
```

### Produção
```bash
yarn start
```

O servidor estará disponível em `http://localhost:3333`

## 📊 Scripts disponíveis

- `yarn dev` - Executa em modo desenvolvimento com hot reload
- `yarn start` - Executa em modo produção
- `yarn db:generate` - Gera migrações do Drizzle
- `yarn db:migrate` - Executa migrações no banco
- `yarn db:studio` - Abre o Drizzle Studio
- `yarn db:seed` - Executa dados de exemplo

## 🏗️ Estrutura do projeto

```
src/
├── db/
│   ├── connection.ts
│   ├── migrations/
│   ├── schema/
│   └── seed.ts
├── http/
│   └── routes/
├── env.ts
└── server.ts
```

## 🔧 Padrões utilizados

- **Type Safety**: TypeScript + Zod para validação
- **Clean Architecture**: Separação de responsabilidades
- **Database First**: Drizzle ORM com migrações
- **RESTful APIs**: Fastify com validação automática
- **Environment Variables**: Validação com Zod

## 🐳 Docker

O projeto inclui configuração Docker para PostgreSQL com pgvector:

```bash
# Iniciar banco
docker-compose up -d

# Parar banco
docker-compose down
```

## 📝 Endpoints

- `GET /health` - Health check
- `GET /rooms` - Lista salas disponíveis

## 🔍 Drizzle Studio

Para visualizar e gerenciar o banco de dados:
```bash
yarn db:studio
```
