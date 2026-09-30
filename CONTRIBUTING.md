# Contributing to ADEA

Thanks for helping. This file is the org-wide default: it describes what is true
of every public repository, and what to do when the repository you are working in
disagrees.

**A repository's own `CONTRIBUTING.md` wins.** `ui` and `themes` have one and
it is the authority for that codebase. Everything here is the floor, not the
ceiling.

## Before you start

Every public repository ships an `AGENTS.md`, and in several of them it is the
real operating contract — it carries the reasoning that does not fit in a commit
message. Read the one in the repository you are about to change before you
change it.

Issues are welcome without a patch, and issues with a reproduction are worth more
than issues without one. If you are about to change a token set, a retrieval
ranking, or a protocol boundary, open an issue first. Those edits reach every
consumer, and agreeing on the shape before the code is cheaper than reverting it
after.

## The toolchain

All six public repositories pin the same versions and manage them with
[mise](https://mise.jdx.dev):

| Tool | Pinned in |
| --- | --- |
| Bun | `.bun-version`, `packageManager` |
| Node.js | `.node-version` |
| Rust | `rust-toolchain.toml` |
| Everything else | `.mise.toml` |

```sh
git clone https://github.com/adea-ai/<repo>.git
cd <repo>
mise install        # honours the pinned versions
bun install
bun run verify      # typecheck, lint, tests, build
```

Use the pinned versions. A reproducible baseline is worth more than the newest
patch release, and `verify` green on a mismatched toolchain proves less than it
appears to.

## Pull requests

- Default branch is `main` on every repository. Branch from it, target it.
- Every repository has a pull request template. Fill it in — it asks for the
  thing reviewers otherwise have to ask for.
- Run `bun run verify`. A skipped check is not a passing check.
- One concern per pull request. A refactor and a behaviour change in the same
  diff is two reviews wearing one hat.
- Say which repositories a change affects. A change to `ui` or `themes` lands
  in Adea and Cortana; a change to `control-plane` shapes what every consumer
  can depend on. The `cross-repo` label exists for exactly this.

## Reporting a security issue

Do not open a public issue. Follow [SECURITY.md](SECURITY.md).

## Code of Conduct

[CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md) applies in every ADEA space. It is
Contributor Covenant 2.1 and it is enforced.
