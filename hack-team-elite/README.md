# SAHARA

SAHARA is a FastAPI application with a Jinja2 landing page, static CSS, and
SQLAlchemy configuration for PostgreSQL. The landing page does not make
medical claims or provide diagnosis.

## Requirements

- Python 3.14
- PostgreSQL (needed when you start using database features)

## Set up and run (Windows Command Prompt)

Run these commands from the repository root. Create the virtual environment
only once:

```bat
cd /d C:\Users\mypc\Desktop\Sahara\hack-team-elite
py -3.14 -m venv .venv
.venv\Scripts\python.exe -m pip install -r backend\requirements.txt
.venv\Scripts\python.exe -m uvicorn app.main:app --app-dir backend --reload
```

If `.venv` already exists, skip the `py -3.14 -m venv .venv` command.

Open `http://127.0.0.1:8000/` for the landing page,
`http://127.0.0.1:8000/health` for the health check, or
`http://127.0.0.1:8000/docs` for the interactive API documentation.

## PostgreSQL configuration

The home page and health check run without a database connection. Before using
database features, set `DATABASE_URL` in Command Prompt to your PostgreSQL
connection URL:

```bat
set DATABASE_URL=postgresql+psycopg://YOUR_USER:YOUR_PASSWORD@localhost:5432/YOUR_DATABASE
```

Replace the example values with your local PostgreSQL credentials and database.
Do not commit passwords or other secrets to Git.
