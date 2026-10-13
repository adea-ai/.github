# Agent instructions: organization defaults

This repository contains the public organization profile and community defaults.
It has no application runtime, package manifest, build system or CI workflow.

## Navigation

- [README.md](README.md): GitHub locations and inheritance behavior.
- [profile/README.md](profile/README.md): organization Overview content; the root
  README describes this repository instead.
- [CONTRIBUTING.md](CONTRIBUTING.md), [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md) and
  [SECURITY.md](SECURITY.md): existing organization defaults.
- [.github/ISSUE_TEMPLATE](.github/ISSUE_TEMPLATE): inherited issue forms.

Repository-specific community files take precedence over these defaults.
Changes here can affect repositories that inherit them; check intended links,
labels and wording in the affected forms or profile.

## Working drafts

For authorized repository work, proceed with ordinary edits, checks, commits and
draft pushes without repeated confirmation. Use checked-in conventions for
routine choices; ask only when a consequential decision or authority is missing.

- Branch from current `main`. Reuse a suitable focused draft PR, or open one;
  keep working on that branch throughout the task.
- Commit and push WIP during work and before stopping or handing off. Incomplete
  work and failing checks do not block draft pushes; record results and gaps.
- Verify the remote head before and after pushing. Preserve another contributor's
  changes; use a separate handoff branch when needed instead of force-pushing.
- Keep auto-merge off while pushing unreviewed work. Review and applicable passing
  checks gate readiness and merge, rather than WIP publication.

## Managed-core applicability

This repository has no `.github/code-foundry.yml` or Code Foundry managed core.
The official sync command requires that configuration; the repository-specific
guidance here does not introduce Code Foundry onboarding.

## Validation

Review Markdown and issue-form YAML, verify local links and referenced labels,
and run `git diff --check`. There is no repository build/test command to run;
the product-toolchain examples in the organization contribution guide do not
apply to this documentation-only checkout. Use existing tooling when checking
Markdown or YAML rather than adding a package manifest for this task.

## Handoff

Report changed files, exact check commands/results, skipped checks and remaining
work, plus the branch, PR link and verified remote SHA. Distinguish draft WIP
from reviewed work ready for the next gate.
