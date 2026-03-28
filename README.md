# 🚀 Dockerized FastAPI + PostgreSQL

A **production-ready** FastAPI application with PostgreSQL, fully containerized using Docker and Docker Compose.

## Features

- Modern Async **FastAPI** with auto-generated Swagger UI
- Optimized **multi-stage Dockerfile** (small & secure)
- Non-root user for security
- Multi-container setup (`app` + `postgres`)
- Persistent database with Docker volumes
- Health checks and restart policies
- Clean project structure with separation of concerns

## Quick Start

```bash
# 1. Clone & start
docker compose up --build -d

# 2. Check status
docker compose ps

# 3. View logs
docker compose logs app
Access the app:

Main: http://localhost:8000
Swagger Docs: http://localhost:8000/docs
Health: http://localhost:8000/health

Project Structure
textdocker-fastapi-postgres/
├── app/
│   ├── main.py                 # FastAPI app entrypoint
│   ├── core/config.py          # Settings with Pydantic
│   ├── db/database.py          # SQLAlchemy models & session
│   └── api/todos.py            # Todo CRUD routes
├── Dockerfile                  # Multi-stage production build
├── docker-compose.yml          # Multi-container orchestration
├── requirements.txt
├── .dockerignore
└── README.md
Tech Stack

Python 3.12 + FastAPI
SQLAlchemy + psycopg2-binary
PostgreSQL 16
Docker + Docker Compose
Uvicorn ASGI server

Production Practices Demonstrated

Multi-stage Docker builds (reduced image size)
Non-root container user
Proper Docker layer caching
.dockerignore for clean context
Healthchecks on services
depends_on with service_healthy
Environment variable management
Restart policies (unless-stopped)

Local Development
PowerShellpython -m venv .venv
.venv\Scripts\Activate.ps1
pip install -r requirements.txt
uvicorn app.main:app --reload --host 0.0.0.0 --port 8000
Made as a learning project to demonstrate DevOps + Backend skills.
