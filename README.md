# Finance Dashboard API

Esta é a API para o Finance Dashboard, um sistema para gerenciamento de KPIs, produtos e transações financeiras.

## 🚀 Tecnologias Utilizadas

- Node.js
- Express.js
- MongoDB + Mongoose
- dotenv
- CORS
- Helmet
- Morgan
- Nodemon (para desenvolvimento)

## 📌 Instalação

Clone este repositório e instale as dependências:

```sh
git clone https://github.com/Cardosofiles/finance-control-server
cd finance-dashboard-server
npm install
```

## ⚙️ Configuração do Ambiente

Crie um arquivo `.env` na raiz do projeto e adicione a variável de ambiente para conexão com o MongoDB:

```env
MONGO_URL=<sua-url-do-mongodb>
PORT=9000
```

## ▶️ Executando o Servidor

Para rodar o servidor em modo desenvolvimento:

```sh
npm run dev
```

O servidor estará disponível em `http://localhost:9000`.

## 📌 Estrutura do Projeto

```
finance-dashboard-server/
│── src/
│   ├── routes/
│   │   ├── kpi.js
│   │   ├── product.js
│   │   ├── transaction.js
│   ├── services/
│   │   ├── KPI.js
│   │   ├── Product.js
│   │   ├── Transaction.js
│   ├── index.js
│── package.json
│── .env.example
│── README.md
```

## 📌 Rotas da API

### 📊 KPI (Key Performance Indicators)

- `GET /kpi/kpis` → Retorna a lista de KPIs.

### 🛍️ Produtos

- `GET /product/products` → Retorna a lista de produtos.

### 💳 Transações

- `GET /transaction/transactions` → Retorna as transações mais recentes (limite de 50, ordenadas por data de criação descendente).

## 📌 Modelos de Dados (Mongoose)

### KPI

```js
{
  totalProfit: Number,
  totalRevenue: Number,
  totalExpenses: Number,
  expensesByCategory: Map,
  monthlyData: [
    {
      month: String,
      revenue: Number,
      expenses: Number,
      operationalExpenses: Number,
      nonOperationalExpenses: Number
    }
  ],
  dailyData: [
    {
      date: String,
      revenue: Number,
      expenses: Number
    }
  ]
}
```

### Produto

```js
{
  price: Number,
  expense: Number,
  transactions: [ObjectId]
}
```

### Transação

```js
{
  buyer: String,
  amount: Number,
  productIds: [ObjectId]
}
```

## 📌 Autor

Desenvolvido por João Batista 🚀
