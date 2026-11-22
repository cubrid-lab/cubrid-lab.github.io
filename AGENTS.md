# AGENTS.md

## Issue and PR guidance for the documentation site

See the [local contributor guide](CONTRIBUTING.md). Issue titles use only a type prefix (`feat:`, `bug:`, `docs:`, etc.), not a required module scope. Describe the human-readable goal or observed defect, relevant evidence and verifiable acceptance criteria. Triage determines validity, duplication, scope, priority and size; PR and commit titles retain the existing Conventional Commits requirements and CI. Avoid personal comments, opaque internal IDs and agent narration.


## Scope

This repository maintains CUBRID Lab documentation and website content. Preserve existing
repository-specific build, publishing, security and licensing rules.

## PR review outcomes (common decision rules)

Apply the same outcome rules to human-authored and AI-assisted PRs. Review the actual diff, linked issue, compatibility, tests, documentation, safety and risks on the **current head commit**.

- **`APPROVE`** when the reviewed code has no substantive blocking finding. An optional improvement may be suggested in the approval; do not leave a clean external PR at `COMMENT` solely because of non-blocking polish. Re-evaluate if the head changes.
- **`REQUEST_CHANGES`** for a concrete must-fix correctness, regression, test, compatibility, security, safety or policy finding. Point to the affected code and an observable failure/acceptance condition; re-review after a fix.
- **`COMMENT`** for a question, preliminary/undecided review, or a non-decisional note. For a PR authored by the same GitHub account, GitHub self-approval is unavailable: record review findings honestly instead of manufacturing an independent approval.
- **Approval is not CI or workflow authorization.** A code review may be approved before CI finishes, but `action_required`, pending, failed, stale, skipped required checks or a workflow awaiting an external-contributor run authorization are **not** passing CI. The workflow-run authorization is separate from a PR `APPROVE`.
- **Merge only after all applicable gates.** Check required statuses on the final head, unresolved threads, repository-specific integration/security/independent-review requirements, protected paths and the maintainer's explicit merge decision. AI/bot output is advisory, never human approval or executed-test evidence. An approval never waives a release/publishing gate, permits admin bypass of failing checks, or authorizes automatic merging of security/workflow changes.

This section standardizes review **outcomes**, not branch protection, required reviewer counts, contributor reservations, release cadence or project-specific safety gates.

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

## Human-readable communication (all agents)

For this site, use the human-readable communication rule below.
On this site it applies to page copy, page titles, link text, change notes
and agent-written PR descriptions and review replies: say what a visitor or
maintainer needs to know and why before any issue number or internal label.
This repository's publishing, URL, security and licensing rules keep
precedence; do not rename pages or change URLs only to improve wording. The
notes below are the local application of that rule.

Use this rule for text authored or edited by Codex, Claude Code, OpenCode,
ChatGPT, Copilot, or any other agent. It applies to issues, PRs, reviews,
comments, checklists, status updates, commit summaries, release notes,
documentation, presentations, and other maintainer-facing writing.

- Write for a reader unfamiliar with the underlying script, storyboard,
  automation run, or agent plan. Name the actual project, component,
  action, evidence, and location in ordinary, clear language.
- Never use unexplained internal identifiers as reader-facing labels or
  checklist instructions (for example, `H1, P1, C1, K1, F2` or `A1/B1/R1/R2`).
  Do not substitute `P1`/`P2` for repository priority labels.
- When an internal identifier is necessary for accurate cross-reference,
  **describe the subject first**, then add the identifier in context:
  `site overview (0:20; section 1)`. Use descriptive
  names and timestamps, section titles, or paths wherever practical.
- Use natural, actionable wording. Prefer `Listen to the full narration and
  verify the pronunciation of each project name` to `Maintainer full listen`.
  Avoid compressed task fragments, unexplained acronyms, and generated
  process/status jargon.
- Keep legitimate technical identifiers unchanged in code, tests, structured
  data, logs, specifications, and exact evidence references. Issue numbers,
  filenames, command names, APIs, error codes, and hashes are not prohibited.
  Do not break machine-readable references to improve prose.
- Before publishing, reread the text as a first-time maintainer. It should
  state what happened or needs to happen, why, and where without requiring a
  separate lookup table. Edit an existing editable comment to correct unclear
  wording rather than adding redundant follow-up comments.

This is a local writing convention, not a new CI check, reviewer approval,
or merge gate. Keep existing repository-specific technical and safety rules.

## Repository-specific issue and PR evidence

This repository owns **the CUBRID Lab organization's public landing site**. Issue and PR titles, bodies, ADR/design discussions and release or publication claims must start with **this repository's** affected files and observable behavior. Check site source, content inventory, accessibility, navigation and actual published deployment checks. Do not reuse the rationale, issue tracker, implementation plan, test command, supported version claim or release schedule of another CUBRID Lab repository.

Other repositories may be linked as content destinations, but their issues, ADRs and release status cannot be assumed as this website's own implementation evidence. When an external link represents a real integration, specification or independent comparison, explain why it is needed and distinguish external context from locally tested evidence. Before review, scan the issue/PR title and description, contributor/agent guidance, documentation and published notes for incorrect project names or cross-language tooling. Keep the existing local CI, security and maintainer approval rules unchanged; this is a manual writing check, not an additional CI gate.
