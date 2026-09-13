# CUBRID Lab — Organization Landing Site

[![Docs](https://img.shields.io/badge/site-cubrid--lab.github.io-FF6600)](https://cubrid-lab.github.io/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

This repository hosts the **cubrid-lab organization landing site** at
<https://cubrid-lab.github.io/> — an ecosystem portal for the open-source
CUBRID client libraries maintained by the [cubrid-lab](https://github.com/cubrid-lab)
organization.

## What lives here

| Path | Purpose |
|---|---|
| `docs/` | MkDocs Material source (Home, Packages, Get Started, Articles, Roadmap, Community, About) |
| `mkdocs.yml` | Site configuration and navigation |
| `.github/workflows/docs.yml` | GitHub Pages build & deploy (same pattern as all cubrid-lab repos) |

## Local development

```bash
pip install mkdocs-material pymdown-extensions
mkdocs serve
# open http://localhost:8000
```

Build check (CI-enforced):

```bash
mkdocs build --strict
```

## Content policy

- **English-first**: canonical content is English; Korean articles live under
  `docs/articles/.../ko.md` with an English summary companion (`index.md`).
- **No AI-authorship narrative**: public content describes the verification
  system (tests, CI gates), not who or what authored the code.
- **Metrics hygiene**: numbers are sourced from the verified metrics snapshot
  and re-measured at release milestones — no stale star/download badges.
- Claims are stated defensibly (e.g. "the first *publicly available* CUBRID
  MCP server", not "world's first").

## Contributing

See the [Community page](https://cubrid-lab.github.io/community/) for the
issue-first workflow, commit conventions, and translation governance used
across all cubrid-lab repositories.

## License

[MIT](LICENSE) — same as every cubrid-lab repository.
