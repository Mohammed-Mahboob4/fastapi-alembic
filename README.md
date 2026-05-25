# FastAPI Alembic Project

## Setup

1. Clone the repo
2. Create a virtual environment and install dependencies:
```bash
pip install -r requirements.txt
```
3. Create a `.env` file in the root:
```
DATABASE_URL=postgresql://admin:password@localhost:5432/appdb
```
4. Start the database:
```bash
docker-compose up -d
```
5. Apply existing migrations:
```bash
alembic upgrade head
```

## Migration Rules

- Never generate a migration on a feature branch
- Always pull latest main and run `alembic upgrade head` before generating a new migration
- Always run `alembic heads` before generating a migration — it must show only one head
- Never edit a migration file that has already been applied anywhere
- Always commit migration files together with your model changes