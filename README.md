# dnd_manager — minimal users API

This minimal project exposes CRUD endpoints for `User` objects using Express and `pg`.

Database setup (Postgres):

1. Create a database (example):

```sql
CREATE DATABASE dnd_manager;
\c dnd_manager

CREATE TABLE users (
  id SERIAL PRIMARY KEY,
  name TEXT NOT NULL,
  email TEXT UNIQUE NOT NULL
);
```

2. Set `DATABASE_URL` if needed, e.g.: `postgresql://user:pass@localhost:5432/dnd_manager`.

Running:

```powershell
npm install
npm start
# server runs on http://localhost:3000
```

Endpoints:
- `GET /users` — list users
- `GET /users/:id` — read single user
- `PUT /users/:id` — update user (JSON body: `name`, `email`)
- `DELETE /users/:id` — delete user
