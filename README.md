# Simple LMS — Django & Docker Foundation

A containerized Learning Management System (LMS) foundation built with **Django**, **PostgreSQL**, and **Docker Compose**. This project focuses on establishing a structured development environment for a Django web application with a PostgreSQL database running in separate Docker containers.

The project was developed as part of the **Server-Side Programming** course to gain practical experience in containerized web application development, database integration, and Django project configuration.

---

## 🚀 Overview

**Simple LMS** is a foundational Django project designed to demonstrate how a web application and its database can be configured and managed using Docker.

The application separates the Django web service and PostgreSQL database into independent containers, providing a consistent and reproducible development environment.

### Key Technologies

- **Django** — Python web framework
- **PostgreSQL** — Relational database management system
- **Docker** — Application containerization
- **Docker Compose** — Multi-container application orchestration
- **Python** — Primary programming language

---

## 🏗️ Architecture

The project consists of two main services:

```text
┌─────────────────────────┐
│      Django Web App     │
│       Python / Django   │
│         Port 8001       │
└────────────┬────────────┘
             │
             │ Database Connection
             ▼
┌─────────────────────────┐
│      PostgreSQL DB      │
│         Port 5432       │
└─────────────────────────┘
```

### Services

| Service | Technology | Description |
|---|---|---|
| `web` | Django | Runs the Django web application |
| `db` | PostgreSQL | Provides persistent relational database storage |

---

## 📁 Project Structure

```text
Simple-LMS/
│
├── docker-compose.yml
├── Dockerfile
├── .env.example
├── requirements.txt
├── manage.py
│
├── config/
│   ├── __init__.py
│   ├── settings.py
│   ├── urls.py
│   ├── asgi.py
│   └── wsgi.py
│
└── README.md
```

---

## ⚙️ Requirements

Before running the project, make sure the following tools are installed:

- Docker Desktop
- Git
- A web browser

The project does not require a local PostgreSQL installation because the database runs inside a Docker container.

---

## 🔧 Environment Configuration

Create a `.env` file based on the provided `.env.example`:

```env
DB_NAME=lmsdb
DB_USER=postgres
DB_PASSWORD=password123
DB_HOST=db
DB_PORT=5432
```

### Environment Variables

| Variable | Description |
|---|---|
| `DB_NAME` | PostgreSQL database name |
| `DB_USER` | PostgreSQL username |
| `DB_PASSWORD` | PostgreSQL password |
| `DB_HOST` | PostgreSQL Docker service name |
| `DB_PORT` | PostgreSQL database port |

> **Note:** The `.env` file should not be committed to GitHub when it contains sensitive credentials. Use `.env.example` as a template for other development environments.

---

## ▶️ Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/JonathanDir/Docker-Django.git
cd Docker-Django
```

### 2. Configure Environment Variables

Create a `.env` file:

```bash
cp .env.example .env
```

On Windows PowerShell, you can use:

```powershell
Copy-Item .env.example .env
```

Adjust the database configuration if necessary.

---

### 3. Build and Start the Containers

```bash
docker compose up -d --build
```

This command builds the Django application image and starts both the Django and PostgreSQL containers.

---

### 4. Run Database Migrations

```bash
docker compose exec web python manage.py migrate
```

This initializes the required Django database tables.

---

### 5. Create a Django Superuser

```bash
docker compose exec web python manage.py createsuperuser
```

Follow the prompts to create the administrator account.

---

### 6. Access the Application

Open your browser and visit:

```text
http://localhost:8001
```

The Django application should now be accessible locally.

---

## 📸 Screenshots

### Django Application

Add a screenshot of the running Django application here.

Example:

```text
screenshots/
└── django-home.png
```

You can display it in this README using:

```markdown
![Django Application](screenshots/django-home.png)
```

---

## 🐳 Docker Commands

### Start Containers

```bash
docker compose up -d
```

### Rebuild Containers

```bash
docker compose up -d --build
```

### Stop Containers

```bash
docker compose down
```

### View Running Containers

```bash
docker compose ps
```

### View Application Logs

```bash
docker compose logs web
```

### Access the Django Container

```bash
docker compose exec web bash
```

---

## 🗄️ Database

This project uses **PostgreSQL** as the database engine.

The PostgreSQL service is managed through Docker Compose and is accessible by the Django application using the Docker service name:

```text
db
```

The default PostgreSQL port inside the container is:

```text
5432
```

---

## 🎯 Learning Objectives

This project was developed to practice:

- Django project initialization and configuration
- PostgreSQL database integration
- Docker containerization
- Docker Compose service orchestration
- Environment variable configuration
- Django database migrations
- Django administrative user management
- Basic container-based development workflow

---

## 🔮 Future Development

The project can be extended into a complete Learning Management System with features such as:

- User authentication and authorization
- Student and instructor management
- Course management
- Learning materials
- Assignment and submission management
- Course enrollment
- Student progress tracking
- Dashboard and reporting
- REST API integration

These features are not part of the current foundation and are listed as potential future improvements.

---

## 👨‍💻 Author

**Jonathan Naufal Farrel**

Informatics Engineering Student  
Universitas Dian Nuswantoro (UDINUS)

**Course:** Server-Side Programming

---

## 📄 License

This project was created for educational and academic purposes.
