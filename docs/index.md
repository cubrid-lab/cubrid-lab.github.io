<div class="cubrid-hero" markdown>

# :material-database-search: CUBRID Lab

<p class="cubrid-tagline" markdown>
**Open-source client ecosystem for CUBRID** — mature Python packages on PyPI,
with Rust, Go, and TypeScript clients in active development.
CUBRID runs a large share of Korean public-sector systems, yet its official
Python driver died in 2014. We rebuilt the entire stack.
</p>

<div class="cubrid-hero-actions" markdown>
[Explore the docs](documentation.md){ .cubrid-btn }
[Get started — 30 seconds](get-started.md){ .cubrid-btn .cubrid-secondary }
[GitHub org](https://github.com/cubrid-lab){ .cubrid-btn .cubrid-secondary }
</div>

</div>

## The Python ecosystem — stable and on PyPI

<div class="grid cards" markdown>

-   :material-database:{ .lg .middle } **pycubrid**

    ---

    Pure-Python DB-API 2.0 driver speaking the CAS wire protocol.
    No C extensions, no compiler, zero dependencies.

    [:octicons-arrow-right-24: Documentation](https://cubrid-lab.github.io/pycubrid/)
    · [:octicons-mark-github-16:](https://github.com/cubrid-lab/pycubrid)
    · `pip install pycubrid`

-   :material-layers-triple:{ .lg .middle } **sqlalchemy-cubrid**

    ---

    SQLAlchemy 2.0 dialect — schema reflection, `MERGE`, native `ENUM`,
    Alembic migrations. Official SA test suite integrated.

    [:octicons-arrow-right-24: Documentation](https://cubrid-lab.github.io/sqlalchemy-cubrid/)
    · [:octicons-mark-github-16:](https://github.com/cubrid-lab/sqlalchemy-cubrid)
    · `pip install sqlalchemy-cubrid`

-   :material-book-open-variant:{ .lg .middle } **cubrid-cookbook-python**

    ---

    75 runnable examples + 7 production templates (FastAPI, Django,
    Streamlit, Celery, AI agent). 45 examples verified nightly on live servers.

    [:octicons-arrow-right-24: Documentation](https://cubrid-lab.github.io/cubrid-cookbook-python/)
    · [:octicons-mark-github-16:](https://github.com/cubrid-lab/cubrid-cookbook-python)

-   :material-robot:{ .lg .middle } **cubrid-mcp-server**

    ---

    The first publicly available CUBRID MCP server. 12 tools behind a
    read-only safety whitelist, with LLM domain-knowledge packs.

    [:octicons-arrow-right-24: Documentation](https://cubrid-lab.github.io/cubrid-mcp-server/)
    · [:octicons-mark-github-16:](https://github.com/cubrid-lab/cubrid-mcp-server)
    · `uvx cubrid-mcp-server`

</div>

## Why you can trust it

<div class="cubrid-stats" markdown>

<div class="cubrid-stat" markdown>
**2,200**

<span>tests</span>
</div>

<div class="cubrid-stat" markdown>
**20**

<span>live CI combinations</span>
</div>

<div class="cubrid-stat" markdown>
**95%**

<span>coverage floor</span>
</div>

<div class="cubrid-stat" markdown>
**450**

<span>merged PRs</span>
</div>

<div class="cubrid-stat" markdown>
**35**

<span>PyPI releases</span>
</div>

<div class="cubrid-stat" markdown>
**MIT**

<span>licensed + SBOM</span>
</div>

</div>

Every change passes an automated quality gate before merge — `mypy --strict`
at zero errors, property-based testing, API-compatibility baselines, nightly
golden runs, and CI on live databases across
Python 3.10–3.14 × CUBRID 10.2–11.4.

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
