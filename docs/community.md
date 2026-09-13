# Community

## How we work

Every cubrid-lab repository follows the same development cycle:

1. **Issue first** — every non-trivial change starts with an issue that
   describes the problem and the proposed solution.
2. **Pull request** — implementation lands as a PR referencing the issue.
   PRs are reviewed by a maintainer; nothing is auto-merged.
3. **CI gates** — lint, type checks, tests (including live-database
   matrices), coverage floors, and documentation-sync checks must pass
   before merge.
4. **Human releases** — version bumps and registry publications are
   performed by maintainers from a single-source changelog.

## Conventions

- **Language**: issues, PRs, and canonical documentation are written in
  English. Korean translations are maintained alongside (`README.ko.md`
  pattern) with CI-enforced synchronization.
- **Commits**: [Conventional Commits](https://www.conventionalcommits.org/)
  (`feat:`, `fix:`, `docs:`, `chore:`, `ci:`, `test:`, `refactor:`).
- **Licensing**: the stable Python packages are MIT licensed with
  `THIRD_PARTY_LICENSES.md`, NOTICE, and SPDX SBOMs attached to releases.

## Ways to contribute

- **Report bugs** — open an issue with a reproduction case; the cookbook's
  runnable examples are a good starting point for isolating behavior.
- **Add a cookbook example** — a new example that passes the golden-test
  pipeline benefits every user of the stack.
- **Improve translations** — Korean docs are first-class; sync gaps are
  detected by CI and filed as issues.
- **Benchmark** — reproducible numbers from
  [cubrid-benchmark](https://github.com/cubrid-lab/cubrid-benchmark) drive
  the optimization roadmap.

## Code of conduct

Be respectful and constructive. Maintainers enforce the standard GitHub
community guidelines; sustained hostility or harassment results in removal
from the organization.
