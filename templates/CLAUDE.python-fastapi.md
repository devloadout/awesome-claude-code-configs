# CLAUDE.md — Python + FastAPI

<!--
  DROP-IN TEMPLATE — DevLoadout / Agentic Coding Starter Kit
  Copy to your repo root as `CLAUDE.md`. Edit the <<FILL IN>> lines. Delete this comment when done.
-->

## Project

<<FILL IN: one sentence on what this service does.>>

Stack: Python <<FILL IN: 3.12>>, FastAPI, Pydantic v2, SQLAlchemy 2.0 (async), Alembic.
Package/deps: <<FILL IN: uv | poetry | pip-tools>>.

## Architecture rules (follow exactly)

- **Layered**: `routers/` (HTTP only) → `services/` (business logic) → `repositories/` (DB).
  Routers must not touch the DB directly; services must not build HTTP responses.
- **Pydantic models for all I/O.** Separate `schemas/` (API contracts) from ORM models (`models/`).
  Never return ORM objects directly from an endpoint.
- **Async all the way down.** Use `async def` endpoints and the async SQLAlchemy session.
  Never call blocking I/O inside an async path — offload with `run_in_threadpool`.
- Dependencies via FastAPI `Depends()`, not module-level globals.

## Conventions

- Type-hint everything. Code must pass `mypy --strict`.
- Validate config with a Pydantic `Settings` class reading from env — no bare `os.getenv`.
- Raise `HTTPException` for client errors; let a global handler format unexpected errors.
- Migrations: never edit the DB by hand — always `alembic revision --autogenerate`.

## Commands

- Run: `<<FILL IN: uv run uvicorn app.main:app --reload>>`
- Typecheck: `mypy --strict .`
- Lint/format: `ruff check . && ruff format .`
- Test: `pytest -q`

**Run mypy, ruff, and pytest before reporting a task complete.**

## What NOT to do

- Don't use sync `requests`/`time.sleep` in async code — use `httpx.AsyncClient`/`asyncio.sleep`.
- Don't put secrets in code or commit `.env`.
- Don't catch bare `except:` — catch specific exceptions and handle them.
- Don't add a dependency before checking the stdlib or existing deps can do it.
