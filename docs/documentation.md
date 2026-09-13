# Documentation

Each package ships its own documentation site, versioned and deployed from
its repository. This page is the hub — start with the stable Python stack.

## Python — stable

<div class="grid cards" markdown>

-   :material-database:{ .lg .middle } **pycubrid**

    ---

    Connection strings, type mapping, CAS wire protocol reference,
    complete API reference.

    [:octicons-arrow-right-24: cubrid-lab.github.io/pycubrid](https://cubrid-lab.github.io/pycubrid/)

-   :material-layers-triple:{ .lg .middle } **sqlalchemy-cubrid**

    ---

    Dialect setup, schema reflection, MERGE/ENUM behavior,
    Alembic migrations.

    [:octicons-arrow-right-24: cubrid-lab.github.io/sqlalchemy-cubrid](https://cubrid-lab.github.io/sqlalchemy-cubrid/)

-   :material-book-open-variant:{ .lg .middle } **cubrid-cookbook-python**

    ---

    75 runnable examples, 7 production templates, nightly
    golden-test pipeline.

    [:octicons-arrow-right-24: cubrid-lab.github.io/cubrid-cookbook-python](https://cubrid-lab.github.io/cubrid-cookbook-python/)

-   :material-robot:{ .lg .middle } **cubrid-mcp-server**

    ---

    12 MCP tools, read-only safety whitelist, domain knowledge packs,
    expert prompts.

    [:octicons-arrow-right-24: cubrid-lab.github.io/cubrid-mcp-server](https://cubrid-lab.github.io/cubrid-mcp-server/)

</div>

## Rust / Go / TypeScript — in progress

Documentation sites for these stacks are not yet published. Track progress
in the package catalog:

- [Rust packages](packages.md#rust-in-progress) — cubrid-rs workspace, sea-orm-cubrid
- [Go packages](packages.md#go-in-progress) — cubrid-go, gorm-cubrid
- [TypeScript packages](packages.md#typescript-in-progress) — cubrid-client, drizzle-cubrid

## Documentation conventions

- Every repository deploys its docs with the same MkDocs Material pipeline
  (`mkdocs build --strict` → GitHub Pages).
- Docs are bilingual where it matters most: English canonical content with
  Korean translations maintained in-repo.
- API references are generated from type-annotated sources — if the docs and
  the code disagree, the code wins; please open an issue.
