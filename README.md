# Contacts API with JWT Auth

A REST API for managing personal contacts, built with FastAPI, async SQLAlchemy, and PostgreSQL. Features JWT-based authentication, email verification, and avatar uploads.

## Features

- CRUD operations for contacts (create, read, update, delete, search, list upcoming birthdays)
- User registration and login with JWT access tokens
- Email verification via a confirmation link
- Avatar upload and storage via Cloudinary (falls back to Gravatar)
- Per-route request rate limiting
- Database migrations with Alembic
- Async PostgreSQL access via SQLAlchemy + asyncpg

## Stack

- Python 3.11, FastAPI
- SQLAlchemy (async), PostgreSQL, Alembic
- Cloudinary, libgravatar
- JWT (python-jose), Passlib/bcrypt (password hashing)
- Docker / Docker Compose

## Setup

1. Install dependencies:
   ```bash
   poetry install
   ```
2. Create a `.env` file with the required variables (database URL, JWT secret, mail server credentials, Cloudinary credentials — see `conf/config.py`).
3. Apply database migrations:
   ```bash
   poetry run alembic upgrade head
   ```

## Usage

Run the API locally:

```bash
poetry run uvicorn main:app --host 127.0.0.1 --port 8000 --reload
```

Or with Docker Compose:

```bash
docker compose up --build
```

Interactive API docs are available at `/docs` once the server is running.
