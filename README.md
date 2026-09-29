# 💰 Finance API

API REST desenvolvida em Node.js com TypeScript para o desafio back-end da Kinvo. O objetivo é gerenciar transações financeiras (receitas e despesas), autenticar utilizadores e exibir o saldo, utilizando boas práticas de arquitetura limpa e código escalável.

---
## 📚 Funcionalidades

- ✅ Cadastro e login de utilizadores
- ✅ Criação de transações (receitas e despesas)
- ✅ Actualização e exclusão de transações
- ✅ Listagem com filtros por data e paginação
- ✅ Exibição do saldo total

---

## 🛠️ Tecnologias utilizadas

![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=node.js&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![Express.js](https://img.shields.io/badge/Express.js-000000?style=for-the-badge&logo=express&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)
![Prisma](https://img.shields.io/badge/Prisma-2D3748?style=for-the-badge&logo=prisma&logoColor=white)
![JWT](https://img.shields.io/badge/JWT-000000?style=for-the-badge&logo=jsonwebtokens&logoColor=white)

---

## 🚀 Como executar o projecto

### Pré-requisitos
- Node.js (v18+)
- PostgreSQL
- npm ou yarn

### Instalação

```bash
# Clone o repositório
git clone https://github.com/alfredobaptista/finance-backend.git
cd finance-backend

# Instale as dependências
yarn install

# Crie um arquivo .env com as variáveis:
DATABASE_URL="postgresql://User:senha@localhost:5432/kinvo"
JWT_SECRET="sua_chave_secreta"

# Execute as migrations
npx prisma migrate dev

# Inicie o servidor para acesso via web/API
yarn dev

# Ou use a interface de linha de comando (CLI)
yarn cli
```

---

## 📮 Rotas principais

| Método | Rota                             | Descrição                     |
|--------|-----------------------------------|--------------------------------|
| POST   | `/auth/register`                  | Cadastro de utilizador         |
| POST   | `/auth/login`                     | Login e geração de token JWT   |
| POST   | `/transactions`                   | Criar transação                |
| PUT    | `/transactions/:id`               | Actualizar transação           |
| DELETE | `/transactions/:id`               | Excluir transação              |
| GET    | `/transactions?limit=10&skip=0`   | Listar transações com filtros  |
| GET    | `/transactions/amount`            | Exibir saldo total             |

⚠️ Todas as rotas de transações exigem autenticação via **token JWT**.

---

## 📌 Observações
- O projeto ainda **não possui testes automatizados** nem **Docker**.
- A arquitetura foi pensada para **facilitar a escalabilidade e manutenção**.
- Futuras melhorias incluem **testes**, **cache**, **segurança avançada** e **deploy**.

---

## 🧠 Sobre o desafio

Este projeto foi desenvolvido como parte do **Desafio Back-end da Kinvo**.
O foco está em aplicar **boas práticas de desenvolvimento**, **arquitetura limpa (hexagonal)** e **organização de código**.

---

## 🗄️ Duplo suporte a banco de dados

O sistema foi pensado para operar com **dois bancos de dados distintos**, mas **apenas um deles será usado por vez**:

- 🔹 **Banco em memória:**
  - Usado principalmente para testes e desenvolvimento local.
  - Facilita a agilidade sem dependências externas.

- 🔹 **PostgreSQL:**
  - Banco relacional utilizado para ambientes de produção.
  - Prisma proporciona uma camada robusta, com tipagem, consultas complexas e migrações controladas.

---

## 🏗️ Arquitectura limpa (Hexagonal)

- O sistema segue o princípio da **arquitetura limpa (ou hexagonal)**, que separa claramente:
  - **Domínio/negócio** (regras e lógica),
  - **Portas** (interfaces abstratas),
  - **Adaptadores** (implementações concretas, como bancos de dados).

- Graças a essa abordagem, a escolha do banco de dados é **abstrata e intercambiável**.
- Isso permite alternar entre o banco em memória e o PostgreSQL sem impactar a lógica central do sistema.

---

## 📌 Decisões técnicas

- Prisma escolhido pela tipagem forte e integração com TypeScript
- JWT com algoritmo HS256 para performance
- Arquitetura hexagonal para facilitar testes e troca de tecnologias
- Separação de responsabilidades para escalabilidade e manutenção

---

## 👨‍💻 Autor

**Alfredo Fernando Baptista**

- GitHub: [@alfredobaptista](https://github.com/alfredobaptista)
- LinkedIn: [linkedin.com/in/alfredobaptista](https://www.linkedin.com/in/alfredobaptista/)
