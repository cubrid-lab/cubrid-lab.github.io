# Contributing

**Issue title policy:** use type-only `feat:`, `bug:`, etc. with observable acceptance criteria. PR and commit messages follow local Conventional Commits rules. Separate issue triage from PR CI; see [AGENTS.md](AGENTS.md).

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


## Issue handoff and development progress

Use the issue and PR's actual state as evidence. Classification, authorization,
implementation, review and completion are **different decisions**:

1. **Intake / triage:** A newly filed issue starts with `status: needs triage`.
   Check evidence or reproduction, duplicate open/closed issues and overlapping
   PRs, repository scope, type, priority, size, dependencies, and verifiable
   acceptance criteria. A maintainer removes the intake label only after
   confirming the saved GitHub metadata. Do not infer priority, size, or triage
   completion automatically from the title or an AI suggestion.
2. **Ready:** Triage completion alone does not authorize development. Record
   the Ready decision in the issue only when the intended outcome and non-goals are bounded, blockers
   have been resolved, and any repository-specific product, architecture,
   safety or compatibility decisions have been accepted. Unresolved research
   remains investigation; blocked work records its dependency and next action.
3. **In Progress:** Before maintainer-directed or autonomous implementation,
   identify the actual implementer in the GitHub Assignee field, check whether
   another open PR already owns the change, and link the implementation PR to
   its issue. Human-led outside contributors may propose a change on an
   unclaimed issue without prior assignment or an AI-tool-specific approval;
   coordinate with existing assignees and follow the local contribution rules.
4. **In Review:** A PR is in review only when its scoped change and verification
   evidence are available. Check the required CI on the final PR head, test
   coverage appropriate to the risk, unresolved review findings and any
   repository-specific independent review or live-system validation. A bot
   review or passing CI cannot replace an outstanding product/safety decision.
5. **Done:** Record the actual disposition: a merged and validated change,
   a completed investigation with evidence, or an explained duplicate/not-
   planned closure. Use an issue-closing PR keyword only if merging actually
   satisfies its acceptance criteria. A merged PR is not proof that any
   deferred integration, fault, security or release verification has passed.

**Tracking without boards:** GitHub Issues and pull requests are the only
workflow tracker. The sole lifecycle label is `status: needs triage` for
unreviewed intake. Once triage is completed, remove that label after checking
the actual saved issue metadata; do not create `status: ready`, `status: in
progress`, or other duplicate workflow labels. Record the **Ready** decision,
remaining dependencies, and next action in the issue. For **In Progress**,
identify the actual implementer using Assignees and add a concise start/handoff
comment; link the working PR when it exists. **In Review** is visible from the
linked open, non-draft PR and its actual review/check status. A **Blocked**
issue records the blocker, responsible party, and unblock condition in a
comment. **Done** is the issue's Closed state with the recorded validated
outcome or explained disposition, not merely the existence of a merged PR.
Do not configure or depend on GitHub Projects/boards. Priority measures impact,
and size estimates effort; neither represents work-in-progress.
This guidance introduces no new automated merge gate and does not supersede
this repository's design, testing, security, or release requirements.
