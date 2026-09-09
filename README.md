# Lucas Saldanha Werneck

**AI automation engineer & prompt engineer.** I build the systems, and I run the companies that depend on them.

Rio de Janeiro · UTC−3 · [LinkedIn](https://www.linkedin.com/in/lucassaldanhawerneck/) · lucas@2olhares.com

Most of my repositories are private because they run real businesses — a cinema-equipment rental company, a certified lens-service lab, and a solar / EV-charger installer that I own. Below is what is in them. Every URL listed is live.

---

## Voice & LLM agents

| Project | What it is | Stack |
|---|---|---|
| **LuxVolt voice receptionist** — [voice.luxvolt.com.br](https://voice.luxvolt.com.br) | Retell AI phone agent for a solar / EV-charger installer. Identifies the caller from caller ID, qualifies the job, books a site visit on the company's real calendar (self-hosted Cal.com), opens support tickets, transfers emergencies to a human. Every tool call is journaled before the agent speaks; bookings are idempotent under retries; webhooks are signature-verified; the public dashboard masks PII. Agent and LLM provisioned from versioned code through the Retell API. | Retell AI · Node 24 · Hono · `node:sqlite` · Cal.com · Docker · Traefik |
| **Smart Cart** | Multi-channel ordering agent: voice or text in, real items in a real supermarket cart out. Whisper STT → Claude structured outputs → live catalogue resolution with brand and price preferences. | Bun · Hono · Turso · grammY · Claude API |
| **Zona Sul MCP server** | Model Context Protocol server exposing a private VTEX GraphQL API as typed agent tools. Replaced brittle browser automation with direct authenticated calls. | TypeScript · MCP SDK · GraphQL |
| **LensTechs knowledge agent** — [lenstech-discord.2olhares.com](https://lenstech-discord.2olhares.com) | RAG over a technical Discord. Incremental export → SQLite FTS5 → grounded answers with channel, author, date and permalink. Instructed to never answer from memory. | Python · SQLite FTS5 · Docker |
| **BenchBigBrother** | Multi-camera capture and review for lens disassembly, with LLM-vision part identification. Motion-triggered ring buffer, hardware HEVC encode. | Node · ffmpeg / VAAPI · Anthropic SDK |
| **Agent tooling** | 12 custom Claude Code skills and a policy hook that enforces an escalation ladder for web access: deny the third identical retry, block automated-browser fingerprints on protected sites, force the next tier instead of looping. | Node · hooks |

## Workflow automation & integrations

| Project | What it is | Stack |
|---|---|---|
| **Booqable ↔ ContaAzul sync engine** — [automacoes.2olhares.com](https://automacoes.2olhares.com) | Replaced four production Make.com scenarios (cutover 2026-08-03, zero data loss). Idempotent decision engine over an append-only journal, daily invariant checker that emails finance when the books disagree, typed alerts with de-duplication, write guards for missing tax IDs. | Node · Hono · BullMQ + Redis · Postgres / Drizzle · Docker |
| **calsinc** — [calsinc.app](https://calsinc.app) | Calendar sync and booking bridge across Google Calendar accounts. | Node · Google Calendar API · Docker |
| **Autopost** — autopost.luxvolt.com.br | Scheduled social publishing pipeline for the energy business. | Node · Docker |
| **Make.com / Zapier / n8n** | Years of production scenarios before the custom engine: webhooks, HTTP modules, Google Apps Script bridges, sheet-to-CRM flows. The blueprints are archived alongside the engine that replaced them. | — |

## Products in production

| Project | What it is | Stack |
|---|---|---|
| **ImportRadar** — [importradar.shop](https://importradar.shop) | Import-viability SaaS: scrapes marketplace and supplier pricing, computes landed cost, margin and ROI, flags products needing ANATEL certification. Payments, email, SSL, backups, health monitoring — all mine. | Python / Flask · Playwright · SQLite · Mercado Pago · Traefik · Cloudflare R2 |
| **EletricParts** — [parts.luxvolt.com.br](https://parts.luxvolt.com.br) | Headless e-commerce storefront for EV-charging parts. | Medusa · Next.js · Postgres · Redis |
| **Tupã** — [tupa.vc](https://tupa.vc) | EV-charger station aggregator with an extraction pipeline and public API. | Node · Redis · Postgres · Docker |
| **LensSys** — lenssys.2olhares.com | Multi-tenant service management for cinema equipment repair. Replaces RepairShopr. | Next.js · Supabase |
| **LensReport** — lensreport.2olhares.com | Optical test reports for cinema lenses. | Next.js |
| **Collimator VCurve** — [collimator-releases](https://github.com/lucas-saldanha-werneck/collimator-releases) | V-curve FFD metrology app for lens collimation (public releases only). | — |
| **Zeiss service manuals** | Two-stage authoring pipeline: training audio → transcript-faithful narrative → professional service manual, cross-referenced against OEM sources. | Whisper · LLM pipeline |

## Infrastructure

25+ services on a self-managed VPS: Docker Compose, Traefik v2 with automatic Let's Encrypt (DNS-01 via Cloudflare), off-site backups, self-hosted health monitoring, and a dead-man's-switch pattern for silent-failure detection.

---

### Background

Undergraduate research in cosmology (co-author on two dark-energy papers, [arXiv:astro-ph/0501643](https://arxiv.org/abs/astro-ph/0501643)). Seventeen years running production companies. Apple Certified Trainer. I have spent more of my life explaining technical systems to non-technical people than writing code — which turns out to be most of the job.
