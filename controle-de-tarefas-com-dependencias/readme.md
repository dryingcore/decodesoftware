# 🧪 Desafio Técnico – Controle de Tarefas com Dependências

## 🎯 Objetivo

Construa uma pequena API (REST ou CLI) para gerenciar tarefas com dependências entre si.  
Cada tarefa só pode ser concluída se **todas as suas tarefas dependentes estiverem concluídas**.

---

## 📋 Requisitos obrigatórios

1. **Criar tarefa**

   - id, nome, status (`pendente | concluída`), e uma lista de dependências (ids de outras tarefas)

2. **Listar tarefas**

   - Exibir todas as tarefas com suas dependências e status atual

3. **Concluir tarefa**

   - Só pode ser marcada como concluída se **todas as tarefas dependentes também estiverem concluídas**
   - Caso contrário, deve retornar um erro claro

4. **Excluir tarefa**
   - Só pode ser excluída se **nenhuma outra tarefa depender dela**

---

## 📦 Exemplo de fluxo

```bash
# Criação
POST /tarefas
{
  "id": "A",
  "nome": "Instalar dependências",
  "dependencias": []
}

POST /tarefas
{
  "id": "B",
  "nome": "Compilar código",
  "dependencias": ["A"]
}

# Tentar concluir tarefa B (erro: depende de A)
PATCH /tarefas/B/concluir

# Concluir A
PATCH /tarefas/A/concluir

# Concluir B (agora pode)
PATCH /tarefas/B/concluir
