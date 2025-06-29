
# 📘 API de Gerenciamento de Produtos

---

## 🧾 Descrição Geral

Esta API fornece operações básicas de **CRUD** (Criar, Ler, Atualizar, Deletar) para o gerenciamento de produtos em uma aplicação. Ideal para sistemas de controle de estoque, marketplaces e catálogos.

---

## 🚀 Funcionalidades

| Função             | Descrição                                | Método | Endpoint              |
|--------------------|--------------------------------------------|--------|------------------------|
| Listar Produtos    | Retorna todos os produtos                 | GET    | `/produtos`           |
| Consultar Produto  | Retorna um produto pelo ID                | GET    | `/produtos/:id`       |
| Criar Produto      | Cadastra um novo produto                  | POST   | `/produtos`           |
| Atualizar Produto  | Atualiza um produto existente             | PUT    | `/produtos/:id`       |
| Deletar Produto    | Remove um produto pelo ID                 | DELETE | `/produtos/:id`       |

---

## 🧱 Tecnologias Utilizadas

- **Node.js** – Ambiente de execução JavaScript no servidor
- **Express.js** – Framework para aplicações web
- **express-validator** – Validação de dados de entrada
- **CORS** – Permite requisições de diferentes origens
- **Insomnia** – Ferramenta para testar APIs

---

## 🗃️ Modelo de Produto

```json
{
  "id": 1,
  "nome": "Teclado Gamer",
  "preco": 199.90
}
```

---

## 📤 Requisições e Respostas

### 🔍 GET `/produtos`

Retorna todos os produtos.

**Resposta 200:**
```json
[
  { "id": 1, "nome": "Camiseta", "preco": 49.90 },
  { "id": 2, "nome": "Tênis", "preco": 199.90 }
]
```

---

### 🔍 GET `/produtos/:id`

Consulta um produto por ID.

**Resposta 200:**
```json
{ "id": 1, "nome": "Camiseta", "preco": 49.90 }
```

**Resposta 404:**
```json
{ "mensagem": "Produto não encontrado" }
```

---

### 📝 POST `/produtos`

Cria um novo produto.

**Body (JSON):**
```json
{
  "nome": "Mouse Sem Fio",
  "preco": 89.90
}
```

**Resposta 201:**
```json
{
  "id": 3,
  "nome": "Mouse Sem Fio",
  "preco": 89.90
}
```

**Resposta 400 (validação):**
```json
{
  "erros": [
    { "msg": "O nome é obrigatório", "param": "nome" },
    { "msg": "O preço deve ser um número maior que zero", "param": "preco" }
  ]
}
```

---

### ✏️ PUT `/produtos/:id`

Atualiza um produto.

**Body (JSON):**
```json
{
  "nome": "Tênis Esportivo",
  "preco": 220.00
}
```

**Resposta 200:**
```json
{
  "id": 2,
  "nome": "Tênis Esportivo",
  "preco": 220.00
}
```

**Resposta 404:**
```json
{ "mensagem": "Produto não encontrado" }
```

---

### ❌ DELETE `/produtos/:id`

Remove um produto.

**Resposta 200:**
```json
{ "mensagem": "Produto removido com sucesso" }
```

**Resposta 404:**
```json
{ "mensagem": "Produto não encontrado" }
```

---

## ✅ Validações

| Campo   | Tipo   | Regra                                 |
|---------|--------|----------------------------------------|
| `nome`  | string | Obrigatório, não pode ser vazio       |
| `preco` | float  | Obrigatório, maior que zero           |

---

## 🧪 Testes com Insomnia

1. Instale: [https://insomnia.rest/download](https://insomnia.rest/download)
2. Crie um novo Workspace: `API Produtos`
3. Adicione requisições com os exemplos desta documentação
4. Use a URL base: `http://localhost:3000`

---

## 🧭 Como Executar Localmente

1. Clone ou baixe o projeto
2. Instale as dependências:

```bash
npm install
```

3. Inicie o servidor:

```bash
npm run dev
```

4. Teste a API acessando:

```
http://localhost:3000/produtos
```

---

## 📌 Notas Finais

- Esta API **não possui autenticação** nesta versão.
- Em versões futuras, poderá incluir **JWT**, **MongoDB** ou **interface Swagger**.

---

## 📞 Contato

- **Email:** ellensimonini.adv@gmail.com  
- **GitHub:** [https://www.github.com/Ellen-simonini](https://www.github.com/Ellen-simonini)

---
