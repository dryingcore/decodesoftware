# 🧪 Teste Técnico – Boas Práticas e Arquitetura (TypeScript + Bun)

## 🎯 Objetivo

Este desafio avalia sua habilidade em projetar sistemas com **boas práticas**, **estrutura limpa** e **domínio técnico em TypeScript moderno**. A ênfase está na **organização do código**, **clareza**, **aplicação de princípios de arquitetura escalável** e uso de ferramentas contemporâneas como o **[Bun](https://bun.sh/)**.

---

## 📚 Contexto

Você foi contratado para construir uma API REST para gerenciamento de tarefas de uma equipe de desenvolvimento. O sistema deve permitir:

- Criar, listar, editar e deletar tarefas.
- Associar tarefas a usuários.
- Marcar tarefas como concluídas.
- Listar tarefas por usuário e status.

---

## ✅ Funcionalidades Requisitadas

- [ ] Criar usuário
- [ ] Criar tarefa
- [ ] Editar usuário
- [ ] Edita tarefa
- [ ] Atualizar status da tarefa
- [ ] Listar tarefas com filtros (por usuário e status)
- [ ] Deletar tarefa

---

## 🧱 Requisitos Técnicos

- **Linguagem:** TypeScript
- **Runtime:** [Bun](https://bun.sh/) — arquivos `.ts` são executados diretamente
- **Framework HTTP:** [Fastify](https://fastify.dev/)
- **Banco de dados:** MySQL, PostgreSQL ou MongoDB (à sua escolha)
- **Estilo de código:** Prettier + ESLint
- **Arquitetura:** Domain-Driven Design + Clean Architecture
- **Testes:** Opcionais, mas recomendados (`bun test` ou similar)

---

## 🧠 Requisitos de Qualidade

- ✅ Estrutura de pastas clara e organizada.
- ✅ Separação correta por camadas: `domain`, `application`, `infrastructure`, `interfaces`.
- ✅ Uso de princípios **SOLID** e boas práticas de projeto.
- ✅ Validação rigorosa dos dados de entrada.
- ✅ Tratamento adequado de erros e exceções.
- ✅ Código legível, com boa nomenclatura e responsabilidades bem definidas.
- ✅ Instruções claras de instalação e execução no `README.md`.

---

## 🚀 Por que usar Bun?

O [Bun](https://bun.sh/) é um runtime moderno e performático para JavaScript/TypeScript.

### ✅ Vantagens práticas:

- Execução direta de arquivos `.ts`, sem necessidade de `tsc` ou `ts-node`.
- Instalação de dependências ultrarrápida com `bun install`.
- Ambiente de testes embutido com `bun test`.
- Menor tempo de boot e build.
- Redução de complexidade no setup do projeto.

---

## 🔧 Pré-requisitos

Antes de começar, você deve ter instalado:

- [Bun](https://bun.sh/docs/installation)
- [Docker](https://docs.docker.com/get-docker/)
- [Docker Compose](https://docs.docker.com/compose/)

---

## 🐳 Execução com Docker

Tanto a API quanto o banco de dados devem rodar em containers via **Docker Compose**, em rede interna isolada.

### ✅ Requisitos da aplicação:

- A aplicação deve estar acessível em `http://localhost:3333`.
- A rede Docker deve ser nomeada (ex.: `internal_net`).
- Variáveis de ambiente devem ser carregadas via arquivo `.env`.

### ▶️ Passos para rodar o projeto:

```bash
# 1. Instale as dependências
bun install

# 2. Suba os containers (API + banco)
docker-compose up -d --build
```

---

## 🗂 Estrutura Esperada

```
.
├── docker-compose.yml
├── Dockerfile
├── .env
├── tsconfig.json
└── src/
    ├── domain/            # Entidades e contratos da regra de negócio
    ├── application/       # Casos de uso
    ├── infrastructure/    # Implementações concretas (ex.: banco)
    ├── interfaces/        # Entradas e saídas (ex.: rotas HTTP)
    ├── shared/            # Helpers, utilitários, configs
    └── index.ts            # Ponto de entrada da aplicação
```

---

## 🧪 Testes

Embora opcionais, testes são fortemente recomendados.

- Priorize a cobertura de **casos de uso** na camada `application/`.
- Utilize `bun test`, `vitest` ou similar.
- Organize os arquivos de teste em `src/tests` ou estrutura equivalente.

---

## 📝 Entrega

- Crie um repositório público no GitHub ou GitLab.
- Suba o código com histórico de commits.
- Garanta que `docker-compose up -d --build` funcione sem erros.
- Confirme que `http://localhost:3333` responde corretamente.
- Certifique-se de que o `README.md` esteja completo e funcional.
- Envie o link do repositório para avaliação.

---

## 📊 Critérios de Avaliação

| Critério                           | Peso |
| ---------------------------------- | ---- |
| Arquitetura e separação de camadas | 30%  |
| Clareza e organização do código    | 25%  |
| Aplicação de boas práticas (SOLID) | 20%  |
| Dockerização funcional             | 15%  |
| Testes e validações (se houver)    | 10%  |

---

## 💡 Dicas

- Evite lógica de negócio nas rotas HTTP.
- Separe responsabilidades claramente (ex.: controladores vs. use-cases).
- Valide todos os dados de entrada.
- Use injeção de dependências onde fizer sentido.
- Evite ORMs pesados se isso comprometer a clareza (query builders simples são aceitos).
- Priorize legibilidade, coesão e previsibilidade do sistema.

---

Boa sorte! 🚀
