# JurisPro - Sistema de Gestão Jurídica

Sistema completo de gestão para escritórios de advocacia, migrado de localStorage para **SQL Server 2022**.

## Estrutura do Projeto

```
JurisPro/
├── database/
│   └── create_database.sql    # Script de criação das tabelas
├── backend/                   # API Node.js/Express
│   ├── src/
│   │   ├── config/           # Configuração do banco
│   │   └── routes/           # Rotas da API
│   └── package.json
└── src/                       # Frontend React/TypeScript
    ├── api/                  # Cliente da API
    ├── components/           # Componentes reutilizáveis
    ├── pages/                # Páginas do sistema
    ├── store/                # Estado global (Zustand)
    ├── theme/                # Tema Material UI
    └── types/                # Tipos TypeScript
```

## Pré-requisitos

- **SQL Server 2022** (ou SQL Server Express)
- **Node.js 18+**
- **npm** ou **yarn**

## Instalação

### 1. Configurar o Banco de Dados

1. Abra o SQL Server Management Studio (SSMS)
2. Conecte-se ao servidor
3. Abra o arquivo `database/create_database.sql`
4. Execute o script completo

Isso criará:
- Banco de dados `JurisPro`
- Todas as tabelas necessárias
- Índices para performance
- View para dashboard
- Dados de exemplo

### 2. Configurar o Backend

```bash
cd backend

# Copiar arquivo de configuração
cp .env.example .env

# Editar o .env com suas credenciais
# DB_SERVER=localhost
# DB_PORT=1433
# DB_NAME=JurisPro
# DB_USER=sa
# DB_PASSWORD=sua_senha

# Instalar dependências
npm install

# Iniciar o servidor
npm run dev
```

### 3. Configurar o Frontend

```bash
# Na raiz do projeto
npm install

# Iniciar o servidor de desenvolvimento
npm run dev
```

O frontend estará disponível em `http://localhost:5173`

## Credenciais de Acesso

| Email | Senha | Papel |
|-------|-------|-------|
| admin@escritorio.com | admin123 | Administrador |
| ana.mendes@escritorio.com | adv123 | Advogado |
| felipe.santos@escritorio.com | adv123 | Advogado |
| beatriz.costa@escritorio.com | adv123 | Advogado |

## Funcionalidades

### Dashboard
- Visão geral do escritório
- Total de processos, clientes, prazos
- Próximos prazos
- Resumo financeiro do mês

### Gestão de Clientes
- Cadastro de pessoas físicas e jurídicas
- Busca e filtros
- Gerenciamento completo (CRUD)

### Gestão de Advogados
- Cadastro com OAB e especialização
- Status ativo/inativo
- Gerenciamento completo (CRUD)

### Processos
- Cadastro de processos com tribunal e área
- Status (ativo, encerrado, suspenso)
- Vinculação com cliente e advogado responsável
- Valor da causa

### Prazos
- Controle de prazos processuais
- Status de conclusão
- Alertas visuais para atrasos

### Tarefas
- Gerenciamento de tarefas
- Prioridade (baixa, média, alta)
- Status (pendente, em andamento, concluído)
- Atribuição a advogados

### Financeiro
- Controle de receitas e despesas
- Categorização
- Status de pagamento
- Resumo financeiro

## Tecnologias

### Backend
- Node.js
- Express
- MSSQL (SQL Server driver)
- UUID

### Frontend
- React 18
- TypeScript
- Material UI
- Zustand (state management)
- React Router
- Axios
- date-fns
- Recharts

## API Endpoints

### Autenticação
- `POST /api/auth/login` - Login
- `POST /api/auth/logout` - Logout
- `GET /api/auth/me` - Usuário atual

### Recursos
- `/api/users` - Usuários
- `/api/lawyers` - Advogados
- `/api/clients` - Clientes
- `/api/processes` - Processos
- `/api/deadlines` - Prazos
- `/api/tasks` - Tarefas
- `/api/financials` - Movimentações financeiras
- `/api/publications` - Publicações
- `/api/dashboard` - Estatísticas

## Build para Produção

```bash
# Backend
cd backend
npm run build

# Frontend
npm run build
```

## Licença

Este projeto é para uso interno.
