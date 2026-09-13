# CUBRID Lab

**Open-source client ecosystem for CUBRID** — mature Python packages published
on PyPI, with Rust, Go, and TypeScript clients in active development.

CUBRID is an Apache-2.0 licensed open-source RDBMS used across a large
share of Korean public-sector systems (industry surveys place it around
10% of public-sector DBMS instances). Yet for years its client tooling
lagged: the official Python driver's last release dates back to 2014.
CUBRID Lab rebuilds that tooling as a modern, tested, documented ecosystem.

## Documentation hub — start with the Python stack

| Documentation | Contents |
|---|---|
| [**pycubrid** — DB-API 2.0 driver](https://cubrid-lab.github.io/pycubrid/) | Connections, type mapping, wire protocol, API reference |
| [**sqlalchemy-cubrid** — SQLAlchemy 2.0 dialect](https://cubrid-lab.github.io/sqlalchemy-cubrid/) | Reflection, MERGE, ENUM, Alembic migrations |
| [**cubrid-cookbook-python** — examples & templates](https://cubrid-lab.github.io/cubrid-cookbook-python/) | 75 runnable examples, 7 production templates |
| [**cubrid-mcp-server** — AI agent access](https://cubrid-lab.github.io/cubrid-mcp-server/) | 12 MCP tools, safety whitelist, domain knowledge packs |

## The Python ecosystem — stable and on PyPI

| Package | What it is | Docs | Install |
|---|---|---|---|
| [pycubrid](https://github.com/cubrid-lab/pycubrid) | Pure-Python DB-API 2.0 driver (no C extensions, zero dependencies) | [docs](https://cubrid-lab.github.io/pycubrid/) | `pip install pycubrid` |
| [sqlalchemy-cubrid](https://github.com/cubrid-lab/sqlalchemy-cubrid) | SQLAlchemy 2.0 dialect — reflection, MERGE, native ENUM, Alembic | [docs](https://cubrid-lab.github.io/sqlalchemy-cubrid/) | `pip install sqlalchemy-cubrid` |
| [cubrid-cookbook-python](https://github.com/cubrid-lab/cubrid-cookbook-python) | 75 runnable examples + 7 production templates, verified nightly on live servers | [docs](https://cubrid-lab.github.io/cubrid-cookbook-python/) | `git clone` |
| [cubrid-mcp-server](https://github.com/cubrid-lab/cubrid-mcp-server) | The first publicly available CUBRID MCP server — read-only safety whitelist, domain knowledge packs | [docs](https://cubrid-lab.github.io/cubrid-mcp-server/) | `uvx cubrid-mcp-server` |

## Why you can trust it

Every change passes an automated quality gate before merge:

- **2,200 tests** across the ecosystem, including the official SQLAlchemy test suite
- **CI on live databases**: Python 3.10–3.14 × CUBRID 10.2/11.0/11.2/11.4 — 20 combinations
- **95% coverage floor** (CI-enforced), `mypy --strict` with 0 errors
- **450 merged PRs** and **35 PyPI releases** shipped through this process
- **MIT licensed**, SPDX SBOM attached to every GitHub Release

## Get started in 30 seconds

```bash
pip install pycubrid
```

```python
import pycubrid

conn = pycubrid.connect(
    host="localhost", port=33000, user="dba", password="", database="testdb"
)
```

More paths — SQLAlchemy, cookbook examples, MCP — on the
[Get Started](get-started.md) page.

## Ecosystem map

| Language | Packages | Status |
|---|---|---|
| Python | pycubrid, sqlalchemy-cubrid, cookbook, MCP server | ![stable](https://img.shields.io/badge/status-stable-brightgreen) |
| Rust | cubrid-rs (protocol, client, tokio, pool), sea-orm-cubrid | ![in progress](https://img.shields.io/badge/status-in%20progress-orange) |
| Go | cubrid-go (database/sql), gorm-cubrid | ![in progress](https://img.shields.io/badge/status-in%20progress-orange) |
| TypeScript | cubrid-client, drizzle-cubrid | ![in progress](https://img.shields.io/badge/status-in%20progress-orange) |

See [Packages](packages.md) for the full catalog and [Roadmap](roadmap.md)
for the maturity matrix.

## Next steps

→ [Documentation](documentation.md) · [Get Started](get-started.md) · [Roadmap](roadmap.md)
