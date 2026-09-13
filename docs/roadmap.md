# Roadmap

## Maturity matrix

| Package | Language | Status | Notes |
|---|---|---|---|
| pycubrid | Python | **Stable** | On PyPI; 16 releases; Python 3.10–3.14 × CUBRID 10.2–11.4 |
| sqlalchemy-cubrid | Python | **Stable** | On PyPI; 19 releases; official SQLAlchemy test suite integrated |
| cubrid-mcp-server | Python | **Stable** | On PyPI; read-only whitelist; domain knowledge packs |
| cubrid-cookbook-python | Python | **Stable** | 75 examples; nightly golden runs on live servers |
| cubrid-rs | Rust | In progress | Workspace: protocol, sync client, tokio, pool |
| sea-orm-cubrid | Rust | In progress | SeaORM dialect |
| cubrid-go | Go | In progress | `database/sql` driver |
| gorm-cubrid | Go | In progress | GORM dialect |
| cubrid-client | TypeScript | In progress | Node.js client |
| drizzle-cubrid | TypeScript | In progress | Drizzle ORM dialect |

Stable means: published to a package registry, documented, CI-gated on live
databases, and covered by the release process (changelog, SBOM, semantic
versioning). In-progress repositories follow the same playbook but have not
reached that bar yet — they are not advertised as production-ready.

## Direction

1. **Deepen Python** — performance work on the driver hot path, broader
   SQLAlchemy/Alembic coverage, more cookbook golden tests.
2. **Replicate the playbook** — the process validated on Python
   (protocol-level tests, live-DB CI matrix, translation governance,
   registry publishing) is being applied to Rust, Go, and TypeScript.
3. **AI-ready tooling** — expand MCP server capabilities and domain
   knowledge packs as the ecosystem grows.

## Performance focus

Current verified optimizations (documented, reproducible via
[cubrid-benchmark](https://github.com/cubrid-lab/cubrid-benchmark)):

| Optimization | Result |
|---|---|
| Native ping (CHECK_CAS) | +280% throughput |
| SQLAlchemy `pool_pre_ping` | +588% throughput |
| Bulk insert (1,000 rows) | 12.3% faster |
| Query select-all | 19.9% faster |

Further driver-level optimization is tracked per-repository in the
[CUBRID Ecosystem Roadmap project board](https://github.com/orgs/cubrid-lab/projects/2).
