# Contributing to ADEA

Thanks for helping. This file is the org-wide default: it describes what is true
of every public repository, and what to do when the repository you are working in
disagrees.

**A repository's own `CONTRIBUTING.md` wins**, including a guide under `.github/`
or `docs/`. Read that guide and the repository's `AGENTS.md` for its actual
commands and workflow. Everything here is the floor, not the ceiling.

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

Use the versions and package manager checked into the repository you are changing.
Repositories have different stacks and pins; `.github` itself has no application
toolchain or build command. Common places to find the declarations are:

| Tool        | Repository declarations                                        |
| ----------- | -------------------------------------------------------------- |
| Bun         | `packageManager`, `.bun-version`, or `.mise.toml` when present |
| Node.js     | `engines`, `.node-version`, or `.mise.toml` when present       |
| Rust        | `rust-toolchain.toml` when present                             |
| Other tools | The repository's own configuration and setup guide             |

Read the repository's setup instructions before installing dependencies.
Use `mise install` where the repository configures mise; use its existing package
manager and lockfile for dependencies. Run the check scripts that actually exist
in its manifest or documented native tooling. `bun run verify` is available only
where the repository defines `verify`; other repositories use separate format,
lint, typecheck, test and build commands. For this `.github` checkout, use the
[documentation checks in AGENTS.md](AGENTS.md#validation).

## Pull requests

- Default branch is `main` on every repository. Branch from it, target it.
- Fill in the repository's pull request template when one is provided — it asks
  for the thing reviewers otherwise have to ask for.
- Run the applicable checks documented by that repository and report their
  results. A skipped check is not a passing check.
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
