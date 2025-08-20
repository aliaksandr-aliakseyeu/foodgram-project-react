# Foodgram — Recipe Sharing Platform (Legacy Learning Project, 2022)

> **Legacy notice:** This is a **learning project built in 2022**. It uses an older tech stack and is preserved for portfolio/history. Not actively maintained.

A simple platform where users publish recipes, subscribe to authors, add favorites, and download a consolidated shopping list for selected dishes.

- **Owner:** @aliaksandr-aliakseyeu  
- **Backend:** Django REST Framework  
- **Frontend:** React (SPA)

---

## Features
- User registration and authentication (JWT/token login)
- CRUD for recipes with ingredients and tags
- Follow authors, manage favorites
- Generate & download a shopping list for selected recipes
- API-first backend (DRF); separate React SPA frontend

---

## Tech Stack (legacy)
- **Python 3.7**, **Django 2.2.x**, **Django REST Framework 3.12.x**
- **PostgreSQL**, **Gunicorn**
- **Docker**, **Docker Compose**, **Nginx**
- Notes: versions reflect 2019–2021 era of the curriculum

---

## Environment variables (`.env`)

```dotenv
# Django
SECRET_KEY=replace_me
DEBUG=False
ALLOWED_HOSTS=localhost,127.0.0.1,web

# Database (PostgreSQL)
DB_ENGINE=django.db.backends.postgresql
DB_NAME=postgres
POSTGRES_USER=postgres
POSTGRES_PASSWORD=postgres
DB_HOST=db
DB_PORT=5432
```

> Provide `.env.example` in the repo and **do not** commit your real `.env`.

---

## Quick Start (Docker)

```bash
# 1) clone
git clone https://github.com/aliaksandr-aliakseyeu/foodgram-project-react.git
cd foodgram-project-react

# 2) environment
cp .env.example .env

# 3) build & run
docker compose up -d --build
# if your Docker uses v1 CLI, replace with: docker-compose up -d --build

# 4) init database
docker compose exec web python manage.py migrate
docker compose exec web python manage.py createsuperuser
docker compose exec web python manage.py collectstatic --no-input

# 5) optional: load fixtures (adjust file name if your repo uses a different one)
docker compose exec web python manage.py loaddata ingredients.json
# or: ingredient.json
```

---

## API Docs

- **ReDoc:** `http://localhost/api/docs/`
- Sample endpoints:
  - `POST /api/users/` — user registration  
  - `POST /api/auth/token/login/` — obtain token  
  - `GET /api/recipes/` — list recipes

---

## Author

**Aliaksandr Aliakseyeu**  
LinkedIn: https://www.linkedin.com/in/aliaksandr-alekseev  
GitHub: https://github.com/aliaksandr-aliakseyeu