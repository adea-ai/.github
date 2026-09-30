# Security Policy

## Reporting a vulnerability

**Email [team@adea.dev](mailto:team@adea.dev). Do not open a public issue, pull
request, or discussion for a vulnerability report.**

Private vulnerability reporting is not currently enabled on our repositories, so
there is no "Report a vulnerability" button on the Security tab. Email is the
only private channel we offer. If you would rather use GitHub's own channel, ask
us and we will enable private vulnerability reporting on the affected repository
first.

Please put `SECURITY` in the subject line.

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
