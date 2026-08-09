---
type: index
owner: "[Owner]"
status: draft
last_updated: YYYY-MM-DD
last_updated_by: "[Owner]"
edit_policy: everyone
---

# Project OS Template

**One project as a file system — one folder your whole team, your client, *and* every AI agent work from.**

<!-- Hero image: add a screenshot of overview.html at assets/hero.png, then
     uncomment the block below. Kept commented so the README never shows a
     broken-image icon before the asset exists.
<p align="center">
  <img src="assets/hero.png" alt="Project OS Template — one project as a file system" width="820">
</p>
-->

Project context lives everywhere and nowhere: the brief in an email, decisions in a Slack thread, the timeline in someone's head. Docs go stale, links rot, and every AI assistant you use starts from zero — you re-explain the client, the scope, and who's who, every single session.

This template fixes that with something boringly simple: **a folder of markdown, in a structure people and agents both understand.** Open it, tell an agent about your project once, and it becomes the shared brain — the place your team looks things up and your AI teammates read before they act. A generated dashboard (`overview.html`) gives you the status at a glance.

> Works with any coding agent — Claude Code, Cursor, Codex, Gemini CLI, and more. Works *best* in [Palette Desktop](https://palette.team), where your team shares one workspace and it stays in sync with your live tools.

> 🧪 **This copy ships pre-filled with a sample project** (*Acme Co. — Customer Portal Rebuild*) so you can see the dashboard and structure working immediately — open [`overview.html`](overview.html). Say **"set me up"** (or run `/onboard`) and an agent replaces the sample with your real project.

---

## Why it works

- **One source of truth.** Each thing lives in one place, and everything links instead of duplicating.
- **Readable by humans and AI.** The same file orients a new joiner and briefs an agent — no separate "AI prompts" to maintain.
- **A dashboard for free.** `overview.html` renders the timeline, goals, stakeholders, and milestones straight from your markdown — no separate status deck.
- **It compounds.** Every session can leave the OS a little smarter (a lesson learned, a decision logged), so it gets more useful as the project runs.
- **Opinionated, but yours.** A strong default structure you can bend — keep the folders that fit, drop the ones you don't need.

---

## Quick start

1. **Copy this folder** into your workspace (Google Drive, a repo, wherever your team keeps files) and rename it for your project.
2. **Open it** in [Palette Desktop](https://palette.team) (best) — or any coding agent (Claude Code, Cursor, Codex, Gemini CLI, …).
3. **Say "set me up"** (or run `/onboard`). The agent notices the OS is still a sample and walks you through it — you won't fill files by hand.
4. **Give it something to work from** (least effort first):
   - **Connect a tool** (Palette / an MCP connector) → it pulls the project, people, and status automatically.
   - **Drop docs in [`_inbox/`](_inbox/)** — the brief, an SOW, kickoff notes — and it files them into the right places.
   - **Paste from another AI** — the agent hands you a prompt to run in Claude/ChatGPT, you paste the answer back.
   - **Or just answer a few questions.**
5. **Open [`overview.html`](overview.html)** for the live dashboard, and start working. Setup progress is tracked in [`SETUP.md`](SETUP.md).

---

## The structure

```
project-os/
│
├── context/            # The what & why — project.md (dashboard meta), brief, goals, stakeholders, glossary
├── meetings/           # One file per meeting (/new-meeting)
├── decisions/          # Why we chose what we chose — ADR-style (/new-decision)
├── research/           # User research, interviews, synthesis
├── design/             # Design rationale + links to Figma / prototypes
├── team/               # How the team works — cadence, comms, onboarding
├── deliverables/       # Milestones and what has shipped
├── admin/              # Scope, timeline, contracts, billing
│
├── overview.html       # Generated status dashboard (reads the markdown frontmatter)
├── AGENTS.md           # How agents behave here — the source of truth
├── CLAUDE.md · GEMINI.md   # thin pointers so each agent auto-loads AGENTS.md (Mistral: .vibe/AGENTS.md)
├── README.md           # this landing page → becomes your project's index after setup
├── SETUP.md            # onboarding checklist (delete when done)
├── lessons.md · log.md # memory: what to do differently · what happened
├── _inbox/             # drop existing docs here to prefill the OS
├── assets/             # logo, images, the README hero
├── .agents/            # canonical commands + skills (every agent reads these)
├── .claude/            # thin adapters so Claude registers the commands
└── .vibe/              # thin pointer so Mistral (Vibe) auto-loads AGENTS.md
```

Every folder has a `README.md` (its front door). The project's memory (`lessons.md`, `log.md`) lives once, at the root, and the dashboard's project metadata lives in `context/project.md`.

---

## Commands

Scaffold with commands so everything stays correctly stamped and indexed — never hand-copy.

| Command | What it does |
|---|---|
| `/onboard` | Set the OS up for your project (connector / docs / Q&A). Runs on first open. |
| `/new-decision` | Log a decision — auto-numbered, stamped, and added to the index. |
| `/new-meeting` | Scaffold meeting notes — dated, stamped, and indexed. |
| `/finish-session` | Wrap up: recap, follow-ups, a memory line. |
| `/workspace-heal` | Audit for broken links, stale indexes, dashboard drift, and unfinished setup. |

Plus a `prefill-context` skill with copy-paste prompts for pulling context out of other AIs and tools.

## Works with any agent, great with Palette Desktop

`AGENTS.md` is the shared source of truth; `CLAUDE.md` / `GEMINI.md` (and `.vibe/AGENTS.md` for Mistral) are thin pointers so Claude, Gemini, Codex, and Mistral all load the same rules — no per-agent prompt drift. It's just files, so it runs anywhere — but [Palette Desktop](https://palette.team) is built for exactly this: your team shares one workspace, every session is a safe sandboxed copy, and a connector keeps the context current.

*Built by [Palette](https://palette.team). Copy it, rename it, make it yours.*

---

## After setup: what this file becomes

Everything above is the **template landing page** — the pitch a newcomer reads when they first copy the folder. It isn't meant to live forever.

During `/onboard`, **replace this whole landing page with the short router below** — swap the minimal frontmatter for the index block, and fill in the body. From then on the `README.md` is your project's living front door: the map agents read at the start of every session. (The dashboard's project data lives in `context/project.md`, not here — `/onboard` fills that in and removes its `sample: true` flag.)

<!-- ONBOARD: replace the entire landing page above with this block, filled in. -->

```markdown
---
type: index
owner: "[Owner]"
status: active
last_updated: YYYY-MM-DD
last_updated_by: "[Owner]"
edit_policy: everyone
---

# [Project] OS

**[One line: what this project delivers, for [Client].]**

The shared, AI-readable home for this engagement. Open `overview.html` for the live status.
New here? This page is your map — skim it, then browse the folders. Agents: read `AGENTS.md` first, then the folder you're working in.

## Where things live

| Folder | What lives here |
|---|---|
| `context/` | Project meta, brief, goals, stakeholders, glossary |
| `meetings/` | One file per meeting |
| `decisions/` | Why we chose what we chose |
| `research/` | User research, interviews, synthesis |
| `design/` | Design rationale + links |
| `team/` | How the team works — cadence, comms, onboarding |
| `deliverables/` | Milestones and shipped work |
| `admin/` | Scope, timeline, contracts |

## The team

- **Our lead:** [Owner]  ·  **Client lead:** [Name]
- Full roster in `context/stakeholders.md`; dashboard metadata in `context/project.md`.
```
