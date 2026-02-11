# 📝 FastAPI To-Do List API

![FastAPI To-Do List Hero Image](/hero_image.png)


[🇧🇷 Português](#português) | [🇺🇸 English](#english)

---

## 🇧🇷 Português

### 📖 Sobre o Projeto

Uma **API RESTful completa** desenvolvida com FastAPI para gerenciamento de tarefas (To-Do List). Este projeto foi criado como resposta ao **#DesafioDaSemana**, implementando todas as operações CRUD (Create, Read, Update, Delete) de forma profissional e eficiente.

A API oferece funcionalidades avançadas como filtragem por status e prioridade, paginação, estatísticas de tarefas e documentação interativa automática.

### ✨ Funcionalidades

- ✅ **Criar tarefas** com título, descrição, status e prioridade
- 📋 **Listar todas as tarefas** com filtros opcionais
- 🔍 **Buscar tarefa específica** por ID
- ✏️ **Atualizar tarefas** (parcial ou completa)
- 🗑️ **Deletar tarefas**
- 📊 **Estatísticas** (total, concluídas, pendentes, taxa de conclusão)
- 🎯 **Sistema de prioridades** (baixa, média, alta)
- 🔄 **Paginação** para grandes volumes de dados
- 📚 **Documentação interativa** automática (Swagger UI e ReDoc)
- 🌐 **CORS habilitado** para integração com frontends

### 🛠️ Tecnologias Utilizadas

- **FastAPI**: Framework web moderno e de alta performance
- **Pydantic**: Validação de dados e serialização
- **Uvicorn**: Servidor ASGI de alta performance
- **Python 3.11+**: Linguagem de programação

### 📋 Pré-requisitos

- Python 3.11 ou superior
- pip (gerenciador de pacotes Python)

### 🚀 Como Executar

#### 1. Clone o repositório

```bash
git clone https://github.com/gabriellafis/fastapi-todo-api.git
cd fastapi-todo-api
```

#### 2. Crie um ambiente virtual (recomendado)

```bash
python -m venv venv
source venv/bin/activate  # Linux/Mac
# ou
venv\Scripts\activate  # Windows
```

#### 3. Instale as dependências

```bash
pip install -r requirements.txt
```

#### 4. Execute a aplicação

```bash
uvicorn main:app --reload
```

A API estará disponível em: **http://localhost:8000**

### 📚 Documentação da API

Após iniciar o servidor, acesse:

- **Swagger UI (interativa)**: http://localhost:8000/docs
- **ReDoc (alternativa)**: http://localhost:8000/redoc

### 🔌 Endpoints Disponíveis

#### Tarefas

| Método | Endpoint | Descrição |
|--------|----------|-----------|
| `GET` | `/` | Página inicial da API |
| `POST` | `/tasks` | Criar nova tarefa |
| `GET` | `/tasks` | Listar todas as tarefas |
| `GET` | `/tasks/{task_id}` | Buscar tarefa específica |
| `PUT` | `/tasks/{task_id}` | Atualizar tarefa |
| `DELETE` | `/tasks/{task_id}` | Deletar tarefa |
| `GET` | `/tasks/stats/summary` | Obter estatísticas |

### 💡 Exemplos de Uso

#### Criar uma tarefa

```bash
curl -X POST "http://localhost:8000/tasks" \
  -H "Content-Type: application/json" \
  -d '{
    "title": "Estudar FastAPI",
    "description": "Completar tutorial oficial",
    "priority": "high",
    "completed": false
  }'
```

#### Listar todas as tarefas

```bash
curl -X GET "http://localhost:8000/tasks"
```

#### Listar tarefas pendentes de alta prioridade

```bash
curl -X GET "http://localhost:8000/tasks?completed=false&priority=high"
```

#### Atualizar uma tarefa

```bash
curl -X PUT "http://localhost:8000/tasks/{task_id}" \
  -H "Content-Type: application/json" \
  -d '{
    "completed": true
  }'
```

#### Deletar uma tarefa

```bash
curl -X DELETE "http://localhost:8000/tasks/{task_id}"
```

#### Obter estatísticas

```bash
curl -X GET "http://localhost:8000/tasks/stats/summary"
```

### 📊 Estrutura do Projeto

```
fastapi-todo-api/
├── main.py              # Aplicação principal
├── requirements.txt     # Dependências do projeto
├── .gitignore          # Arquivos ignorados pelo Git
└── README.md           # Documentação
```

### 🎯 Modelo de Dados

#### Task (Tarefa)

```json
{
  "id": "uuid-string",
  "title": "Título da tarefa",
  "description": "Descrição opcional",
  "completed": false,
  "priority": "medium",
  "created_at": "2025-10-01T10:00:00",
  "updated_at": "2025-10-01T10:00:00"
}
```

**Campos:**
- `id` (string): Identificador único (UUID)
- `title` (string): Título da tarefa (obrigatório, 1-200 caracteres)
- `description` (string): Descrição detalhada (opcional, até 1000 caracteres)
- `completed` (boolean): Status de conclusão (padrão: false)
- `priority` (string): Prioridade - "low", "medium" ou "high" (padrão: "medium")
- `created_at` (datetime): Data/hora de criação
- `updated_at` (datetime): Data/hora da última atualização

### 🔮 Melhorias Futuras

- [ ] Persistência em banco de dados (PostgreSQL/MongoDB)
- [ ] Autenticação e autorização (JWT)
- [ ] Testes automatizados (pytest)
- [ ] Sistema de tags para categorização
- [ ] Datas de vencimento e lembretes
- [ ] Dockerização da aplicação
- [ ] Deploy em produção (Heroku/Railway/Render)

### 📝 Licença

Este projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

### 👤 Autor

**Gabriel Demetrios Lafis**

- GitHub: [@gabriellafis](https://github.com/gabriellafis)

### 🤝 Contribuições

Contribuições, issues e feature requests são bem-vindos!

---

## 🇺🇸 English

### 📖 About The Project

A **complete RESTful API** developed with FastAPI for task management (To-Do List). This project was created as a response to the **#WeeklyChallenge**, implementing all CRUD operations (Create, Read, Update, Delete) in a professional and efficient manner.

The API offers advanced features such as filtering by status and priority, pagination, task statistics, and automatic interactive documentation.

### ✨ Features

- ✅ **Create tasks** with title, description, status, and priority
- 📋 **List all tasks** with optional filters
- 🔍 **Search specific task** by ID
- ✏️ **Update tasks** (partial or complete)
- 🗑️ **Delete tasks**
- 📊 **Statistics** (total, completed, pending, completion rate)
- 🎯 **Priority system** (low, medium, high)
- 🔄 **Pagination** for large data volumes
- 📚 **Automatic interactive documentation** (Swagger UI and ReDoc)
- 🌐 **CORS enabled** for frontend integration

### 🛠️ Technologies Used

- **FastAPI**: Modern, high-performance web framework
- **Pydantic**: Data validation and serialization
- **Uvicorn**: High-performance ASGI server
- **Python 3.11+**: Programming language

### 📋 Prerequisites

- Python 3.11 or higher
- pip (Python package manager)

### 🚀 How to Run

#### 1. Clone the repository

```bash
git clone https://github.com/gabriellafis/fastapi-todo-api.git
cd fastapi-todo-api
```

#### 2. Create a virtual environment (recommended)

```bash
python -m venv venv
source venv/bin/activate  # Linux/Mac
# or
venv\Scripts\activate  # Windows
```

#### 3. Install dependencies

```bash
pip install -r requirements.txt
```

#### 4. Run the application

```bash
uvicorn main:app --reload
```

The API will be available at: **http://localhost:8000**

### 📚 API Documentation

After starting the server, access:

- **Swagger UI (interactive)**: http://localhost:8000/docs
- **ReDoc (alternative)**: http://localhost:8000/redoc

### 🔌 Available Endpoints

#### Tasks

| Method | Endpoint | Description |
|--------|----------|-------------|
| `GET` | `/` | API home page |
| `POST` | `/tasks` | Create new task |
| `GET` | `/tasks` | List all tasks |
| `GET` | `/tasks/{task_id}` | Get specific task |
| `PUT` | `/tasks/{task_id}` | Update task |
| `DELETE` | `/tasks/{task_id}` | Delete task |
| `GET` | `/tasks/stats/summary` | Get statistics |

### 💡 Usage Examples

#### Create a task

```bash
curl -X POST "http://localhost:8000/tasks" \
  -H "Content-Type: application/json" \
  -d '{
    "title": "Study FastAPI",
    "description": "Complete official tutorial",
    "priority": "high",
    "completed": false
  }'
```

#### List all tasks

```bash
curl -X GET "http://localhost:8000/tasks"
```

#### List pending high-priority tasks

```bash
curl -X GET "http://localhost:8000/tasks?completed=false&priority=high"
```

#### Update a task

```bash
curl -X PUT "http://localhost:8000/tasks/{task_id}" \
  -H "Content-Type: application/json" \
  -d '{
    "completed": true
  }'
```

#### Delete a task

```bash
curl -X DELETE "http://localhost:8000/tasks/{task_id}"
```

#### Get statistics

```bash
curl -X GET "http://localhost:8000/tasks/stats/summary"
```

### 📊 Project Structure

```
fastapi-todo-api/
├── main.py              # Main application
├── requirements.txt     # Project dependencies
├── .gitignore          # Files ignored by Git
└── README.md           # Documentation
```

### 🎯 Data Model

#### Task

```json
{
  "id": "uuid-string",
  "title": "Task title",
  "description": "Optional description",
  "completed": false,
  "priority": "medium",
  "created_at": "2025-10-01T10:00:00",
  "updated_at": "2025-10-01T10:00:00"
}
```

**Campos:**
- `id` (string): Identificador único (UUID)
- `title` (string): Título da tarefa (obrigatório, 1-200 caracteres)
- `description` (string): Descrição detalhada (opcional, até 1000 caracteres)
- `completed` (boolean): Status de conclusão (padrão: false)
- `priority` (string): Prioridade - "low", "medium" ou "high" (padrão: "medium")
- `created_at` (datetime): Data/hora de criação
- `updated_at` (datetime): Data/hora da última atualização

### 🔮 Melhorias Futuras

- [ ] Database persistence (PostgreSQL/MongoDB)
- [ ] Authentication and authorization (JWT)
- [ ] Automated tests (pytest)
- [ ] Tag system for categorization
- [ ] Due dates and reminders
- [ ] Docker containerization
- [ ] Production deployment (Heroku/Railway/Render)

### 📝 Licença

This project is under the MIT license. See the [LICENSE](LICENSE) file for more details.

### 👤 Autor

**Gabriel Demetrios Lafis**

- GitHub: [@gabriellafis](https://github.com/gabriellafis)

### 🤝 Contribuições

Contribuições, issues, and feature requests are welcome!

---

⭐ **If you liked this project, give it a star!** ⭐

