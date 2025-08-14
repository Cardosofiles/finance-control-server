# Finance Dashboard Server

Servidor backend para gerenciamento financeiro, fornecendo APIs RESTful para controle de transações, categorias, usuários e relatórios. Ideal para dashboards financeiros pessoais ou corporativos.

## ✨ Funcionalidades Principais

- Cadastro, autenticação e gerenciamento de usuários
- CRUD de transações financeiras (receitas e despesas)
- Gerenciamento de categorias de transações
- Relatórios financeiros (por período, categoria, etc.)
- Filtros e paginação de dados
- Middleware de autenticação JWT
- Logs e tratamento de erros

## 🛠️ Stack e Tecnologias

- **Node.js** (runtime)
- **Express** (framework web)
- **TypeScript** (tipagem estática)
- **Prisma ORM** (acesso a banco de dados)
- **PostgreSQL** (banco de dados relacional)
- **JWT** (autenticação)
- **dotenv** (variáveis de ambiente)
- **Jest** (testes automatizados)
- **ESLint/Prettier** (padronização de código)

## 📁 Estrutura de Pastas

```
finance-dashboard-server/
├── src/
│   ├── controllers/    # Lógica dos endpoints (ex: TransactionController)
│   ├── middlewares/    # Middlewares (ex: autenticação, erros)
│   ├── models/         # Modelos de dados (Prisma)
│   ├── routes/         # Definição das rotas da API
│   ├── services/       # Regras de negócio e integrações
│   ├── utils/          # Funções utilitárias
│   ├── config/         # Configurações (ex: banco, env)
│   └── app.ts          # Inicialização do Express
├── prisma/             # Schema e migrações do banco
├── tests/              # Testes automatizados
├── .env.example        # Exemplo de variáveis de ambiente
├── package.json
└── README.md
```

### Explicação das principais partes

- **controllers/**: Implementam a lógica dos endpoints da API.
- **middlewares/**: Funções intermediárias para autenticação, logs, erros, etc.
- **models/**: Definição dos modelos de dados via Prisma.
- **routes/**: Organização das rotas e endpoints.
- **services/**: Camada de negócio, separando lógica do controller.
- **prisma/**: Schema do banco e arquivos de migração.
- **tests/**: Testes unitários e de integração.

## 🚀 Instalação e Execução Local

### Pré-requisitos

- Node.js >= 18.x
- npm >= 9.x
- PostgreSQL >= 13

### Passos

1. **Clone o repositório**

   ```bash
   git clone https://github.com/seu-usuario/finance-dashboard-server.git
   cd finance-dashboard-server
   ```

2. **Instale as dependências**

   ```bash
   npm install
   ```

3. **Configure as variáveis de ambiente**

   - Copie o arquivo `.env.example` para `.env` e ajuste conforme seu ambiente:
     ```
     cp .env.example .env
     ```
   - Edite `.env` com as credenciais do banco e segredo JWT.

4. **Execute as migrações do banco**

   ```bash
   npx prisma migrate deploy
   ```

5. **Inicie o servidor**
   ```bash
   npm run dev
   ```
   O servidor estará disponível em `http://localhost:3000`.

## 🧪 Executando Testes

```bash
npm test
```

Os testes estão localizados na pasta `tests/` e cobrem controllers, services e integrações.

## 📚 Exemplos de Uso dos Endpoints

### Autenticação

```http
POST /api/auth/login
Content-Type: application/json

{
  "email": "user@email.com",
  "password": "senha123"
}
```

### Criar Transação

```http
POST /api/transactions
Authorization: Bearer <token>
Content-Type: application/json

{
  "amount": 100.50,
  "type": "income",
  "categoryId": 1,
  "description": "Salário",
  "date": "2024-06-01"
}
```

### Listar Transações

```http
GET /api/transactions?startDate=2024-06-01&endDate=2024-06-30
Authorization: Bearer <token>
```

## 💡 Boas Práticas e Recomendações

- Sempre utilize branches para novas features ou correções.
- Mantenha o padrão de código seguindo ESLint e Prettier.
- Adicione testes para novas funcionalidades.
- Documente endpoints e regras de negócio relevantes.
- Utilize variáveis de ambiente para dados sensíveis.
- Revise as PRs antes de mergear.

## 🤝 Contribuição

1. Fork este repositório
2. Crie sua branch (`git checkout -b feature/nome`)
3. Commit suas alterações (`git commit -m 'feat: nova feature'`)
4. Push para o branch (`git push origin feature/nome`)
5. Abra um Pull Request

---

Para dúvidas ou sugestões, abra uma issue ou entre em contato!

## 📫 Contato

<div align="center">

<a href="mailto:cardosofiles@outlook.com">
  <img src="https://img.shields.io/badge/Email-0078D4?style=for-the-badge&logo=microsoftoutlook&logoColor=white" alt="Email"/>
</a>
<a href="https://www.linkedin.com/in/joaobatista-dev/" target="_blank">
  <img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"/>
</a>
<a href="https://github.com/Cardosofiles" target="_blank">
  <img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub"/>
</a>
<a href="https://cardosofiles.dev/" target="_blank">
  <img src="https://img.shields.io/badge/Portfólio-222222?style=for-the-badge&logo=about.me&logoColor=white" alt="Portfólio"/>
</a>

</div>
