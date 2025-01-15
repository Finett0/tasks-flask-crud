# Documentação da aplicação CRUD em Flask

Esta documentação descreve os endpoints e funcionalidades da API CRUD implementada em Flask. A API permite criar, visualizar, atualizar e excluir tarefas.

---

## Estrutura do Projeto

- **Flask**: Framework utilizado para criar a aplicação.
- **Model**: A classe `Task` representa a estrutura de uma tarefa.
- **Dados Temporários**: As tarefas são armazenadas em uma lista `tasks`, e o controle de IDs é gerenciado pela variável global `task_id_control`.

---

## Endpoints

### 1. Criar Tarefa
**Endpoint:** `/tasks`  
**Método HTTP:** `POST`  
**Descrição:** Cria uma nova tarefa.  
**Corpo da Requisição (JSON):**  
```json
{
  "title": "Título da Tarefa",
  "description": "Descrição da Tarefa"
}

````
### Retorno em JSON
```json

{
  "message": "Nova Tarefa Criada com sucesso"
}
```
---

### 2. Listar Todas as Tarefas
**Endpoint:** `/tasks`
<br>
**Método HTTP:** `GET`
<br>
**Descrição:** Retorna uma lista com todas as tarefas.
<br>
**Exemplo de Resposta (JSON):**
```json
{
  "tasks": [
    {
      "id": 1,
      "title": "Título da Tarefa",
      "description": "Descrição da Tarefa",
      "completed": false
    },
    {
      "id": 2,
      "title": "Outra Tarefa",
      "description": "Outra Descrição",
      "completed": true
    }
  ],
  "total_tasks": 2
}
```
---

### 3. Consultar uma Tarefa pelo ID
**Endpoint:** `/tasks/<int:id>`
<br>
**Método HTTP:** `GET`
<br>
**Descrição:** Retorna os detalhes de uma tarefa específica pelo ID.
```json
{
  "id": 1,
  "title": "Título da Tarefa",
  "description": "Descrição da Tarefa",
  "completed": false
}
```
---
### 4. Atualizar uma Tarefa
**Endpoint:** `/tasks/<int:id>`
<br>
Método HTTP: `PUT`
<br>
**Descrição:** Atualiza os detalhes de uma tarefa existente pelo ID.
<br>
Corpo da Requisição (JSON):
```json
{
  "title": "Novo Título",
  "description": "Nova Descrição",
  "completed": true
}
```
Retorno de Sucesso em JSON:
```json
{
  "message": "Tarefa Atualizada com sucesso"
}
```
Retorno de Erro em JSON:
```json
{
  "message": "Não Foi possível encontrar a atividade"
}
```
---

### 5. Excluir uma Tarefa
**Endpoint:** `/tasks/<int:id>`
<br>
**Método HTTP:** `DELETE`
<br>
**Descrição:** Remove uma tarefa específica pelo ID.
<br>

Retorno de Sucesso em JSON:
```json
{
  "message": "Tarefa Deletada com sucesso"
}
```
Retorno de Erro em JSON:
```json
{
  "message": "Não Foi possível encontrar a atividade"
}
```





