# Lucas Saldanha Werneck

**AI automation engineer & prompt engineer.** I build the systems, and I run the companies that depend on them.

Rio de Janeiro · UTC−3 · [LinkedIn](https://www.linkedin.com/in/lucassaldanhawerneck/) · lucas@2olhares.com

Most of my repositories are private because they run real businesses — a cinema-equipment rental company, a certified lens-service lab, and a solar / EV-charger installer that I own. Below is what is in them. Every URL listed is live.

---

## Open source: AI tools for Claude Code

**[lucas-tools](https://github.com/lucas-saldanha-werneck/lucas-tools)** — the 26 AI tools I use every day with Claude Code: skills, hooks, mods (side panes and notes inside Claude Code) and commands, in one catalog. MIT, one repo each. To install, run this in Claude Code:

```
/plugin marketplace add lucas-saldanha-werneck/lucas-tools
```

- **Claude checks its own work:** [give-up-guard](https://github.com/lucas-saldanha-werneck/give-up-guard) sends it back when it stops with "didn't check"; [side-notes](https://github.com/lucas-saldanha-werneck/side-notes) shows the one thing you may have missed; [self-improve](https://github.com/lucas-saldanha-werneck/self-improve) turns repeated corrections into fixes; [wait-loop-guard](https://github.com/lucas-saldanha-werneck/wait-loop-guard) blocks wait loops with no deadline; [polish](https://github.com/lucas-saldanha-werneck/polish) is a simplicity review; [plugin-dev-guard](https://github.com/lucas-saldanha-werneck/plugin-dev-guard) keeps edits in the source repo.
- **Sessions that survive:** [save-clear](https://github.com/lucas-saldanha-werneck/save-clear) clears its own context and resumes from a summary; [session-keeper](https://github.com/lucas-saldanha-werneck/session-keeper), [remote-sessions](https://github.com/lucas-saldanha-werneck/remote-sessions), [session-archive](https://github.com/lucas-saldanha-werneck/session-archive), [rc-auto](https://github.com/lucas-saldanha-werneck/rc-auto).
- **Side panes:** [assumptions-pane](https://github.com/lucas-saldanha-werneck/assumptions-pane), [idea-shelf](https://github.com/lucas-saldanha-werneck/idea-shelf), [plan-checklist](https://github.com/lucas-saldanha-werneck/plan-checklist) and [clean-view](https://github.com/lucas-saldanha-werneck/clean-view), stacked in one [side-stack](https://github.com/lucas-saldanha-werneck/side-stack).
- **Web, secrets and the Mac:** [web-unlock](https://github.com/lucas-saldanha-werneck/web-unlock), [web-unlock-guard](https://github.com/lucas-saldanha-werneck/web-unlock-guard), [op-secrets](https://github.com/lucas-saldanha-werneck/op-secrets), [handoff-terminal](https://github.com/lucas-saldanha-werneck/handoff-terminal), [mac-remote](https://github.com/lucas-saldanha-werneck/mac-remote), [launchd-agenda](https://github.com/lucas-saldanha-werneck/launchd-agenda).
- **More:** [llm-council](https://github.com/lucas-saldanha-werneck/llm-council) asks several LLMs and lets them rank each other; [api-credit](https://github.com/lucas-saldanha-werneck/api-credit); command-line tools [stable-sync](https://github.com/lucas-saldanha-werneck/stable-sync) and [meeting-copilot](https://github.com/lucas-saldanha-werneck/meeting-copilot).

---

## Voice & LLM agents

| Project | What it is | Stack |
|---|---|---|
| **LuxVolt voice receptionist** — [voice.luxvolt.com.br](https://voice.luxvolt.com.br) | Retell AI phone agent for a solar / EV-charger installer. Identifies the caller from caller ID, qualifies the job, books a site visit on the company's real calendar (self-hosted Cal.com), opens support tickets, transfers emergencies to a human. Every tool call is journaled before the agent speaks; bookings are idempotent under retries; webhooks are signature-verified; the public dashboard masks PII. Agent and LLM provisioned from versioned code through the Retell API. | Retell AI · Node 24 · Hono · `node:sqlite` · Cal.com · Docker · Traefik |
| **Smart Cart** | Multi-channel ordering agent: voice or text in, real items in a real supermarket cart out. Whisper STT → Claude structured outputs → live catalogue resolution with brand and price preferences. | Bun · Hono · Turso · grammY · Claude API |
| **Zona Sul MCP server** | Model Context Protocol server exposing a private VTEX GraphQL API as typed agent tools. Replaced brittle browser automation with direct authenticated calls. | TypeScript · MCP SDK · GraphQL |
| **LensTechs knowledge agent** — [lenstech-discord.2olhares.com](https://lenstech-discord.2olhares.com) | RAG over a technical Discord. Incremental export → SQLite FTS5 → grounded answers with channel, author, date and permalink. Instructed to never answer from memory. | Python · SQLite FTS5 · Docker |
| **BenchBigBrother** | Multi-camera capture and review for lens disassembly, with LLM-vision part identification. Motion-triggered ring buffer, hardware HEVC encode. | Node · ffmpeg / VAAPI · Anthropic SDK |

## Workflow automation & integrations

| Project | What it is | Stack |
|---|---|---|
| **Booqable ↔ ContaAzul sync engine** — [automacoes.2olhares.com](https://automacoes.2olhares.com) | Replaced four production Make.com scenarios (cutover 2026-08-03, zero data loss). Idempotent decision engine over an append-only journal, daily invariant checker that emails finance when the books disagree, typed alerts with de-duplication, write guards for missing tax IDs. | Node · Hono · BullMQ + Redis · Postgres / Drizzle · Docker |
| **calsinc** — [calsinc.app](https://calsinc.app) | Calendar sync and booking bridge across Google Calendar accounts. | Node · Google Calendar API · Docker |
| **AutoPost** — [autopost.luxvolt.com.br](https://autopost.luxvolt.com.br) | SaaS for a franchise network: connects the franchisor's marketing hub (Sults) to each franchisee's Instagram and publishes automatically through the official Graph API. Free trial, no card. Automation as a product, not a scenario. | Node · Instagram Graph API · Docker |
| **Make.com / Zapier / n8n** | Years of production scenarios before the custom engine: webhooks, HTTP modules, Google Apps Script bridges, sheet-to-CRM flows. The blueprints are archived alongside the engine that replaced them. | — |

## Products in production

| Project | What it is | Stack |
|---|---|---|
| **ImportRadar** — [importradar.shop](https://importradar.shop) | Import-viability SaaS: scrapes marketplace and supplier pricing, computes landed cost, margin and ROI, flags products needing ANATEL certification. Payments, email, SSL, backups, health monitoring — all mine. | Python / Flask · Playwright · SQLite · Mercado Pago · Traefik · Cloudflare R2 |
| **LensReport** — [lensreport.2olhares.com](https://lensreport.2olhares.com) | SaaS: turns a cinema-lens inspection — instrument readings, cross-check, diagnosis — into a branded PDF report in the client's language. Free trial. | Next.js |
| **Leasing simulator** — [leaseing.luxvolt.com.br](https://leaseing.luxvolt.com.br) | Financial model for photovoltaic leasing in condominiums (Rio tariff structure, Lei 14.300 "Fio B"), as an interactive simulator. | Vanilla JS |
| **EletricParts** — parts.luxvolt.com.br | Headless e-commerce storefront for EV-charging parts. | Medusa · Next.js · Postgres · Redis |
| **Tupã** — [tupa.vc](https://tupa.vc) | EV-charger station aggregator (Voltbras, Tupimob, movE…) with an extraction pipeline and public API. App in review. | Node · Redis · Postgres · Docker |
| **LensSys** — lenssys.2olhares.com | Multi-tenant service management for cinema equipment repair. Replaces RepairShopr. | Next.js · Supabase |
| **Collimator VCurve** — [colimador-releases](https://github.com/lucas-saldanha-werneck/colimador-releases) | V-curve FFD metrology app for lens collimation (public releases only). | — |
| **Zeiss service manuals** | Two-stage authoring pipeline: training audio → transcript-faithful narrative → professional service manual, cross-referenced against OEM sources. | Whisper · LLM pipeline |

## Infrastructure

25+ services on a self-managed VPS: Docker Compose, Traefik v2 with automatic Let's Encrypt (DNS-01 via Cloudflare), off-site backups, self-hosted health monitoring, and a dead-man's-switch pattern for silent-failure detection.

---

### Background

Undergraduate research in cosmology (co-author on two dark-energy papers, [arXiv:astro-ph/0501643](https://arxiv.org/abs/astro-ph/0501643)). Seventeen years running production companies. Apple Certified Trainer. I have spent more of my life explaining technical systems to non-technical people than writing code — which turns out to be most of the job.
