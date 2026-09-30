# Security Policy

## Reporting a vulnerability

**Do not open a public issue, pull request, or discussion for a vulnerability
report.** There are two private channels, and either one reaches us:

1. **GitHub's private reporting** — enabled on every public repository. Use
   *Security* → *Report a vulnerability* on the affected repository. This is the
   fastest route: the report arrives as a private advisory draft with a
   conversation thread attached.
2. **Email [team@adea.dev](mailto:team@adea.dev)** — put `SECURITY` in the
   subject line and name the affected repository.

Prefer the first if the repository is public. Use email for a cross-cutting
issue that spans repositories, or if private reporting is not available to you.

The two private repositories in this organization do not expose private
reporting, which is expected: access to them is already restricted. Report
against the public component, or use email.

## What to include

- The repository and, if relevant, the deployment profile (**Cloud**, **Hosted**, or **Local**).
- Version, commit SHA, or release tag.
- What an attacker gains, and what access they need to start.
- Steps to reproduce, or a proof of concept.
- The impact you believe it has, and how you would prioritise it.

Credentials, tokens, database URLs, and customer data are all out of scope for a
report — please do not send them. Describe them instead. Note that
[secret scanning and push protection](https://docs.github.com/en/code-security/secret-scanning)
are enabled on our repositories, so an accidentally committed credential is
likely already revoked on our side.

## What to expect

- An acknowledgement within **3 business days**.
- An assessment with a severity and a decision within **14 days**.
- A fix, or a mitigation and a published advisory, on a timeline we agree with
  you. We will not publish anything that names you without your say-so.
- Credit in the advisory unless you would rather we did not.

We will coordinate disclosure with you rather than announcing a fix on a date we
pick unilaterally. If a report is not a vulnerability, we will say so plainly and
tell you what we think it is instead.

## Scope

In scope: every repository in [github.com/adea-ai](https://github.com/adea-ai),
including private repositories you have legitimate access to.

Especially interested in:

- **Cortana authorization.** Cortana is designed so that source authorization,
  ingestion, model use, and memory writes are separate explicit decisions. A way
  to reach any of them without the decision is a serious finding.
- **Control Plane credential handling.** The credential vault, RuntimeNode key
  registration, and the HPKE v1 remote-control envelope.
- **Adea entitlement gates.** The remote mount for the private Agent Sim engine
  is entitlement-gated; anything that reaches it without an entitlement is a
  serious finding.
- **Secrets in CI.** Workflow injection, unpinned third-party actions, and any
  path by which a pull request can read a repository secret.
