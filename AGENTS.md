# AGENTS.md

## Shared issue, PR, and commit standard

See the [cubrid-lab organization standard](https://github.com/cubrid-lab/.github/blob/main/docs/ISSUE_PR_COMMIT_STANDARD.md). Issue titles use only a type prefix (`feat:`, `bug:`, `docs:`, etc.), not a required module scope. Describe the human-readable goal or observed defect, relevant evidence and verifiable acceptance criteria. Triage determines validity, duplication, scope, priority and size; PR and commit titles retain the existing Conventional Commits requirements and CI. Avoid personal comments, opaque internal IDs and agent narration.


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
