# Agent instructions for Adea organization defaults

Organization profile and community defaults. Start with `README.md` and `CONTRIBUTING.md`; this repository has no application build or package manifest.

## Working drafts

For authorized repository work, proceed with ordinary edits, checks, commits and
draft pushes without repeated confirmation. Use the checked-in conventions for
routine choices; ask only when a consequential decision or authority is missing.

- Work on a topic branch from current `main`; target the same focused draft PR
  throughout the task. Check for an overlapping draft before creating one.
- Commit and push WIP during the task and before stopping or handing off.
  Incomplete work and failing checks do not block draft pushes; record the exact
  results and remaining work in the draft.
- Verify the remote head before and after pushing. If another contributor has
  advanced it, preserve their work; use a separate handoff branch when needed.
  Do not force-push over another contributor.
- Keep auto-merge off while pushing unreviewed work. Review and applicable
  passing checks gate readiness and merge, rather than WIP publication.

## Validation

Review Markdown and issue forms, verify local links, and run `git diff --check`.
