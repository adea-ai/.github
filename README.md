# .github

This repository is [ADEA](https://github.com/adea-ai)'s org-level configuration.
It is not a product. Nothing here is built, released, or consumed at runtime.

## What lives here

| File                                                 | Purpose                                                                                                                                               |
| ---------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| [`profile/README.md`](profile/README.md)             | Renders on the organization's [Overview tab](https://github.com/adea-ai). This is the only file in the repository that appears in public-facing docs. |
| [`CONTRIBUTING.md`](CONTRIBUTING.md)                 | Org-wide contribution defaults. Repositories with their own `CONTRIBUTING.md` keep it.                                                                |
| [`CODE_OF_CONDUCT.md`](CODE_OF_CONDUCT.md)           | [Contributor Covenant 2.1](https://www.contributor-covenant.org/version/2/1/code_of_conduct/), enforced across every repository.                      |
| [`SECURITY.md`](SECURITY.md)                         | How to report a vulnerability. Applies org-wide.                                                                                                      |
| [`.github/ISSUE_TEMPLATE/`](.github/ISSUE_TEMPLATE/) | Issue forms inherited by repositories that do not define their own.                                                                                   |

## How the profile README is wired

GitHub renders `profile/README.md` from this repository on the organization
Overview tab. Two rules follow from that and are easy to get wrong:

- The path is `profile/README.md`, **not** `README.md` at the root. A root
  `README.md` renders only when someone browses the repository itself.
- The repository must be public and named exactly `.github`. There is no other
  name that works.

Members of the organization see a _member_ view of the profile. A separate
private `.github-private` repository with `profile/README.md` supplies that
view. We do not have one, so members and non-members currently see the same
public content.

## Precedence

GitHub merges these files by a fixed rule: **the most specific repository wins.**
A `.github` file in a repository overrides the one here, which means a
repository can deliberately opt out of anything in this table without anyone
editing this repository.

Repositories can provide their own agent instructions, contribution guides and
templates. Some repositories, including `plugins`, already define issue forms,
so they use those forms rather than the defaults here. Check the destination
repository before assuming inheritance. GitHub documents this behavior in
[Creating a default community health file](https://docs.github.com/en/communities/setting-up-your-project-for-healthy-contributions/creating-a-default-community-health-file).

## Locations GitHub requires

These are not interchangeable, and GitHub does not say so when you get one wrong
— the file is simply ignored.

| File type                                                                      | Required location in this repository                                                                                         |
| ------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------- |
| Org profile                                                                    | `profile/README.md` — the Overview tab reads nothing else                                                                    |
| Issue templates and their `config.yml`                                         | `.github/ISSUE_TEMPLATE/`                                                                                                    |
| Pull request template                                                          | `pull_request_template.md` at root, in `.github/` or `docs/`; multiple templates use a `PULL_REQUEST_TEMPLATE/` subdirectory |
| Community Markdown defaults (CODE_OF_CONDUCT, CONTRIBUTING, SECURITY, SUPPORT) | `.github/`, root, then `docs/`, in that order of precedence                                                                  |
| FUNDING.yml                                                                    | `.github/FUNDING.yml`                                                                                                        |

See GitHub’s [pull request template locations](https://docs.github.com/en/communities/using-templates-to-encourage-useful-issues-and-pull-requests/creating-a-pull-request-template-for-your-repository)
for the single- and multiple-template layouts.

A label referenced by an issue template must also exist here, in the default
repository, as well as in every repository that uses the template. `bug` and
`enhancement` are both present.

## Editing this repository

See [AGENTS.md](AGENTS.md) for the topic-branch and draft-PR workflow. Push work
in progress to the same draft during the task and before handoff. Personal review
of the exact head gates readiness; mark reviewed drafts ready to trigger CI.
Applicable passing checks and protections gate merge. This repository has no build step.

The default branch is `main`. Pinned repositories are configured outside the
repository, on the organization profile page.
