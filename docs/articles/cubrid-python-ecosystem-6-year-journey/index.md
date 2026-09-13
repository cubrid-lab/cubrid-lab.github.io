# The CUBRID Python Ecosystem: A 6-Year Journey

*September 2026 · This is the English summary. [한국어 원문 (full Korean article)](ko.md)*

## The gap

CUBRID — an Apache-2.0 open-source RDBMS — runs a significant share of
South Korea's public-sector information systems. Yet its official Python
driver's final release dates to May 2014. For over a decade, teams
maintaining CUBRID-based systems were effectively locked out of the modern
Python data stack: no maintained driver, no ORM support, no runnable
reference examples.

## How it started

The project began at a 2020 Korean open-source contribution program, where
two of us met as mentor and mentee on a SQLAlchemy-related task and, along
the way, connected with SQLAlchemy's creator, Mike Bayer. Discovering the
state of CUBRID's Python tooling turned a program exercise into a six-year
commitment.

## What was built

Four packages, each step exposing the next gap:

1. **sqlalchemy-cubrid (2021–22)** — the original 2012 dialect was dead.
   Rebuilt from scratch for SQLAlchemy 2.0: schema reflection, `MERGE`,
   `ON DUPLICATE KEY UPDATE`, native `ENUM` (validated against CUBRID
   10.2–11.4), Alembic support, and the official SQLAlchemy test suite.
2. **pycubrid (2025)** — the dialect needed a driver, and the last official
   one was an abandoned C extension. Replaced with a pure-Python DB-API 2.0
   driver, implemented by reverse-engineering the undocumented CAS binary
   protocol through cross-analysis of the BSD-licensed node-cubrid and the
   official C driver sources — 18 packet types, 27 data types. One-line
   install, no compiler, zero dependencies.
3. **cubrid-cookbook-python (2026)** — 75 runnable examples and 7 production
   templates (FastAPI, Flask, Django, Streamlit, Celery, ETL, AI agent).
   More than an example gallery: 45 examples run nightly against live
   CUBRID 11.2 + 11.4 servers, so driver regressions surface in the
   cookbook first.
4. **cubrid-mcp-server (2026)** — the first publicly available CUBRID
   MCP server: 12 tools behind a read-only safety whitelist, with
   domain-knowledge packs that teach LLMs CUBRID SQL syntax.

## How quality is maintained

Every change passes an automated gate: `mypy --strict` at zero errors, a
CI-enforced 95% coverage floor, property-based testing, API-compatibility
baselines, nightly golden runs, and a live-database CI matrix of
Python 3.10–3.14 × CUBRID 10.2–11.4 (20 combinations). In total: **2,200
tests**, **450 merged PRs**, **35 PyPI releases**, all MIT-licensed with
SBOMs on every release.

## Growing OSS in a niche market

Niche databases don't get community tooling for free. The response: run
reproducible benchmarks yourself ([cubrid-benchmark](https://github.com/cubrid-lab/cubrid-benchmark)),
dogfood nightly on live servers, document bilingually (63 English pages,
34 Korean pages across four documentation sites), and make the stack
AI-ready.

## What's next

The playbook validated on Python is being applied to Rust, Go, and
TypeScript. The goal: a four-language open-source client ecosystem for
CUBRID.

## Links

- Organization: <https://github.com/cubrid-lab>
- Driver docs: <https://cubrid-lab.github.io/pycubrid/>
- PyPI: <https://pypi.org/project/pycubrid/> ·
  <https://pypi.org/project/cubrid-mcp-server/>
