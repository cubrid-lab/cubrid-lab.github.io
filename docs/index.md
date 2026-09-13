# CUBRID Lab

**Open-source client ecosystem for CUBRID** — mature Python packages published
on PyPI, with Rust, Go, and TypeScript clients in active development.

CUBRID is an Apache-2.0 licensed open-source RDBMS, widely adopted in the
Korean public sector. Yet for years its client tooling lagged: the official
Python driver's last release dates back to 2014. CUBRID Lab rebuilds that
tooling as a modern, tested, documented ecosystem.

## The Python ecosystem — stable and on PyPI

| Package | What it is | Install |
|---|---|---|
| [pycubrid](https://github.com/cubrid-lab/pycubrid) | Pure-Python DB-API 2.0 driver (no C extensions, zero dependencies) | `pip install pycubrid` |
| [sqlalchemy-cubrid](https://github.com/cubrid-lab/sqlalchemy-cubrid) | SQLAlchemy 2.0 dialect — reflection, MERGE, native ENUM, Alembic | `pip install sqlalchemy-cubrid` |
| [cubrid-cookbook-python](https://github.com/cubrid-lab/cubrid-cookbook-python) | 75 runnable examples + 7 production templates, verified nightly on live servers | `git clone` |
| [cubrid-mcp-server](https://github.com/cubrid-lab/cubrid-mcp-server) | The first publicly available CUBRID MCP server — read-only safety whitelist, domain knowledge packs | `uvx cubrid-mcp-server` |

## Why you can trust it

Every change passes an automated quality gate before merge:

- **2,200 tests** across the ecosystem, including the official SQLAlchemy test suite
- **CI on live databases**: Python 3.10–3.14 × CUBRID 10.2/11.0/11.2/11.4 — 20 combinations
- **95% coverage floor** (CI-enforced), `mypy --strict` with 0 errors
- **450 merged PRs** and **35 PyPI releases** shipped through this process
- **MIT licensed**, SPDX SBOM attached to every GitHub Release

## Ecosystem map

| Language | Packages | Status |
|---|---|---|
| Python | pycubrid, sqlalchemy-cubrid, cookbook, MCP server | ![stable](https://img.shields.io/badge/status-stable-brightgreen) |
| Rust | cubrid-rs (protocol, client, tokio, pool), sea-orm-cubrid | ![in progress](https://img.shields.io/badge/status-in%20progress-orange) |
| Go | cubrid-go (database/sql), gorm-cubrid | ![in progress](https://img.shields.io/badge/status-in%20progress-orange) |
| TypeScript | cubrid-client, drizzle-cubrid | ![in progress](https://img.shields.io/badge/status-in%20progress-orange) |

See [Packages](packages.md) for the full catalog and [Roadmap](roadmap.md)
for the maturity matrix.

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
