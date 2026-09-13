# Packages

All repositories live in the [cubrid-lab](https://github.com/cubrid-lab)
organization. Everything is MIT licensed.

## Python — stable, on PyPI

### pycubrid

Pure-Python DB-API 2.0 (PEP 249) driver speaking the CUBRID CAS wire protocol.
No C extensions, no C compiler, zero runtime dependencies.

- [Repository](https://github.com/cubrid-lab/pycubrid) ·
  [Documentation](https://cubrid-lab.github.io/pycubrid/) ·
  [PyPI](https://pypi.org/project/pycubrid/)
- Python 3.10–3.14, CUBRID 10.2–11.4
- TLS/SSL support, LOB handling, async variant included
- Notable optimizations: native ping (CHECK_CAS) **+280% throughput**,
  SQLAlchemy `pool_pre_ping` **+588% throughput**

### sqlalchemy-cubrid

SQLAlchemy 2.0 dialect, rebuilt from scratch on top of pycubrid.

- [Repository](https://github.com/cubrid-lab/sqlalchemy-cubrid) ·
  [Documentation](https://cubrid-lab.github.io/sqlalchemy-cubrid/) ·
  [PyPI](https://pypi.org/project/sqlalchemy-cubrid/)
- Schema reflection (tables, columns, PK/FK, indexes, views, comments)
- `MERGE`, `ON DUPLICATE KEY UPDATE`, `REPLACE`
- Native `ENUM` support (validated against CUBRID 10.2–11.4)
- Alembic migration support, official SQLAlchemy test suite integrated

### cubrid-cookbook-python

Runnable examples and production templates — and a dogfooding platform:
45 examples execute nightly against live CUBRID 11.2 + 11.4 servers, catching
driver regressions before users do.

- [Repository](https://github.com/cubrid-lab/cubrid-cookbook-python) ·
  [Documentation](https://cubrid-lab.github.io/cubrid-cookbook-python/)
- 75 examples across fundamentals → advanced topics
- 7 application templates: FastAPI, Flask, Django, Streamlit, Celery, ETL,
  AI agent

### cubrid-mcp-server

Model Context Protocol server for CUBRID — the first publicly available one.

- [Repository](https://github.com/cubrid-lab/cubrid-mcp-server) ·
  [Documentation](https://cubrid-lab.github.io/cubrid-mcp-server/) ·
  [PyPI](https://pypi.org/project/cubrid-mcp-server/)
- 12 tools (11 read + 1 opt-in write) behind a read-only safety whitelist
- Domain-knowledge packs that teach LLMs CUBRID SQL syntax
- Expert workflow prompts for common analysis tasks

## Rust — in progress

| Repository | Description |
|---|---|
| [cubrid-rs](https://github.com/cubrid-lab/cubrid-rs) | CAS protocol codec and clients — workspace with `cubrid-protocol`, `cubrid-client` (sync), `cubrid-tokio` (async), `cubrid-pool` (connection pool) |
| [sea-orm-cubrid](https://github.com/cubrid-lab/sea-orm-cubrid) | SeaORM dialect for CUBRID |

## Go — in progress

| Repository | Description |
|---|---|
| [cubrid-go](https://github.com/cubrid-lab/cubrid-go) | Pure-Go `database/sql` driver for CUBRID |
| [gorm-cubrid](https://github.com/cubrid-lab/gorm-cubrid) | GORM dialect for CUBRID |

## TypeScript — in progress

| Repository | Description |
|---|---|
| [cubrid-client](https://github.com/cubrid-lab/cubrid-client) | Modern TypeScript-first Node.js client for CUBRID |
| [drizzle-cubrid](https://github.com/cubrid-lab/drizzle-cubrid) | Drizzle ORM dialect for CUBRID |

## Tooling

| Repository | Description |
|---|---|
| [cubrid-benchmark](https://github.com/cubrid-lab/cubrid-benchmark) | Reproducible benchmark suite with automated comparison for the CUBRID ecosystem |
| [showcase](https://github.com/cubrid-lab/showcase) | Contest materials, press kit, and presentation assets |
