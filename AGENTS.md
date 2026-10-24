# AGENTS.md

## Scope

This repository maintains CUBRID Lab documentation and website content. Preserve existing
repository-specific build, publishing, security and licensing rules.

## Unified PR Review Workflow

Apply the same review and merge process regardless of whether the change
is human-authored or developed with OpenCode, Codex, Claude Code,
ChatGPT, Copilot or another agent.

1. Keep the change focused; add relevant validation and affected docs.
2. Trust required repository GitHub CI checks at the final PR head as the
   official automated verification. Local runs are encouraged, not an
   additional mandatory merge gate.
3. Review correctness, scope, security, maintainability and publication
   effects. Optional Oracle, Copilot or agent-review output is advisory,
   never required because of which coding tool was used.
4. Resolve or disposition findings. The responsible maintainer checks
   required CI, remaining risks and affected publishing paths and
   decides whether to merge.

Verify affected navigation, links, build/deploy output, and published-site safety before merging.
High-risk workflow permissions, secrets and publishing changes need
independent maintainer scrutiny; existing GitHub branch protections
remain unchanged.

## Issue triage lifecycle

New issues in this repository begin with `status: needs triage`. Any issue
forms include the label; the `issues: opened` workflow covers external
submissions. GitHub Actions using `GITHUB_TOKEN` must attach it when creating
issues because their own events may not trigger this workflow.

1. Confirm the problem and evidence, investigate unknowns, detect duplicate
   issues and overlapping open PRs, and check local ownership, issue type,
   scope/non-goals, dependencies and testable acceptance.
2. Compare **all currently open issues in this repository** (including API
   pagination) before deciding relative priority, considering user impact,
   existing work and blockers rather than issue age.
3. Assign one `priority: critical/high/medium/low` and one of the original
   `size: XS/S/M/L/XL`; split oversized implementation work where useful,
   retaining ownership and any parent completion contract.
4. Re-fetch the saved GitHub labels and validate issue type, priority, size,
   scope and duplicate disposition. Remove `status: needs triage` only when
   the maintainer has completed that check. Otherwise retain it.

This process never guesses issue urgency or creates another PR gate. Existing
quality, security and release expectations still apply.
