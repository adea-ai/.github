<h1 align="center">ADEA</h1>

<p align="center">
  <strong>Spatial workspace for multiplayer AI agent management.</strong>
</p>

<p align="center">
  <a href="https://adea.dev">adea.dev</a> ·
  <a href="mailto:team@adea.dev">team@adea.dev</a>
</p>

<p align="center">
  <a href="https://github.com/adea-ai/cortana/releases"><img alt="Cortana release" src="https://img.shields.io/github/v/release/adea-ai/cortana?label=cortana&style=flat-square"></a>
  <a href="https://github.com/adea-ai/adea"><img alt="Adea stars" src="https://img.shields.io/github/stars/adea-ai/adea?style=flat-square&label=adea"></a>
  <img alt="License" src="https://img.shields.io/badge/license-Apache--2.0-blue?style=flat-square">
</p>

---

We build open-source infrastructure for running teams of AI agents as a managed
workforce. ADEA is the product: a browser-based workspace where agents are
supervised, assigned work, and coordinated. Everything underneath it is
open source and Apache-2.0.

## The stack

ADEA is three separable layers. Each is useful on its own, and each is designed
to be replaced or run alongside the others.

| Layer | Repository | What it is |
| --- | --- | --- |
| **Surface** | [`adea`](https://github.com/adea-ai/adea) | The Agentic Development Environment — a Turborepo/SolidJS web app with Home and Work workspaces, chat, tasks, and a plugin marketplace. |
| **Engine** | [`control-plane`](https://github.com/adea-ai/control-plane) | Execution, integration, and orchestration for portable agents. Modular monolith with three deployment profiles: **Cloud**, **Hosted**, and **Local**. |
| **Memory** | [`cortana`](https://github.com/adea-ai/cortana) | A local-first, agent-native second brain. Rust, with a Tauri 2 desktop app, an MCP stdio server, an HTTP API, and a CLI. |

The split matters: the Control Plane owns *execution*, Cortana owns *memory*,
and Adea is the surface you supervise both from. Cortana is explicitly not an
agent harness, and the Control Plane holds no personal data — so you can adopt
either one without adopting the rest.

## Supporting libraries

- **[`ui`](https://github.com/adea-ai/ui)** — the Adea design system: one themed
  Solid component library, token set, and window shell shared by Adea and Cortana.
- **[`themes`](https://github.com/adea-ai/themes)** — semantic OKLCH themes
  normalized from upstream palettes, with Base24, terminal, CSS, and syntax adapters.
- **[`plugins`](https://github.com/adea-ai/plugins)** — a curated collection of
  official harness plugins from the OpenAI, Cursor, and Claude Code registries.

## Principles

**Local-first and explicit.** A new Cortana install is query-only. Source
authorization, ingestion, model use, and memory writes are separate decisions a
person makes on purpose.

**Portable by construction.** The same application semantics deploy to managed
cloud, a VPS you control, or a laptop. Portability is a product requirement, not
a migration project.

**Bounded context.** Agents receive cited, token-budgeted context — not a data
dump. Every claim in a ContextBundle traces back to authorized evidence.

**Own your tools.** The engine, the memory layer, and the design system are all
open source under Apache-2.0. If ADEA stops being the right tool, you can keep
the parts that are.

## Getting involved

Every public repository is Apache-2.0 and accepts issues and pull requests. Good
starting points:

- Read the `docs/` directory in the repository you care about — the architecture
  and decision records are written for outside contributors.
- Try [`cortana`](https://github.com/adea-ai/cortana/blob/main/docs/getting-started.md)
  for the most self-contained path from clone to first cited answer.
- Report what breaks. Issues with reproductions are genuinely useful here.

For anything else, reach us at [team@adea.dev](mailto:team@adea.dev).

---

<p align="center">
  <sub>Maintained by the ADEA team · <a href="https://github.com/adea-ai">github.com/adea-ai</a></sub>
</p>
