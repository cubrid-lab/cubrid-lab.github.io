# Contributing

**Issue title policy:** use type-only `feat:`, `bug:`, etc. with observable acceptance criteria. PR and commit messages follow local Conventional Commits rules. Separate issue triage from PR CI; see [organization standard](https://github.com/cubrid-lab/.github/blob/main/docs/ISSUE_PR_COMMIT_STANDARD.md).

Use a focused pull request with a clear purpose, changed files, validation
evidence and any required documentation updates. Human contributors and
all AI-assisted implementations follow the same review criteria.

Required GitHub CI checks on the final head are authoritative.
Local validation is encouraged but does not create a separate merge
requirement. Oracle, Copilot and agent-review are optional advisory
reviewers; their outputs are not approval or evidence of passing tests.
The responsible maintainer examines correctness, security, affected
published assets and CI status before merging. Verify affected navigation and links before merging; report which build and
published-site checks have actually run.
Do not weaken existing workflow, release, credential or publishing
security requirements.

## Issue and agent work

For this site, file one repository-local issue per independently reviewable
navigation, content or publishing change. Before implementation, check the
current site, existing open issues/PRs and actual owner. New issues enter
`status: needs triage`; maintainers check scope, duplication, type and
relative urgency against the local backlog, then verify exactly one
`priority: critical/high/medium/low` and one `size: XS/S/M/L/XL` before
clearing the label. This is a maintainer decision, not an AI severity score.

Human contributors may propose and work on unclaimed issues without a
specific coding agent or prior approval. Autonomous agents operated by
maintainers need explicit authorization and a verified implementer assignment
before accepting internally reserved work. Keep human-written and
AI-assisted PRs to the same evidence and review standard.

For content and navigation updates, check links/anchors and run the existing
strict MkDocs build locally when practical:

```bash
python -m pip install mkdocs-material pymdown-extensions
mkdocs build --strict
```

The current `.github/workflows/docs.yml` builds and deploys on a **push to
main**, not as a required PR test; do not claim the deployed site was verified
before that event. Publishing permissions, existing Pages configuration and
maintainer review remain authoritative. No live CUBRID test is implied.
