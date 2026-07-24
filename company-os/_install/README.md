---
type: index
status: draft
---

# Company OS Template

**Your company as a file system — one folder your whole team *and* every AI agent work from.**

<!-- Hero image: add a screenshot or GIF of the folder tree at assets/hero.png, then
     uncomment the block below. Kept commented so the README never shows a broken-image
     icon before the asset exists.
<p align="center">
  <img src="assets/hero.png" alt="Company OS Template — your company as a file system, read by people and AI agents" width="820">
</p>
-->

Company knowledge lives everywhere and nowhere: scattered across Docs, Notion, Slack threads, and people's heads. Docs go stale, links rot, and every AI assistant you use starts from zero — you re-explain who you are, what you sell, and how you work, every single session.

This template fixes that with something boringly simple: **a folder of markdown, in a structure people and agents both understand.** Open it, tell an agent about your company once, and it becomes the shared brain — the place your team looks things up and your AI teammates read before they act.

> Works with any coding agent — Claude Code, Cursor, Codex, Gemini CLI, and more. Works *best* in [Palette Desktop](https://palette.team), where your team shares one workspace and it stays in sync with your live tools.

---

## Why it works

Most of your company's knowledge is already text. The trick isn't making *more* docs — it's putting the text you have into a shape that's navigable by a person skimming and an agent reading top-to-bottom.

- **One source of truth.** Each thing lives in one place, and everything links instead of duplicating.
- **Readable by humans and AI.** The same file orients a new hire and briefs an agent — no separate "AI prompts" to maintain.
- **Modular.** Playbooks capture *how you think*, templates give the *format to fill*, commands *do the repetitive work* — and they compose. Producing a launch (or a new account) becomes pick-a-playbook → fill-a-template, not start-from-scratch.
- **It compounds.** Every session can leave the OS a little smarter (a lesson learned, a decision logged), so it gets more useful over time instead of rotting.
- **Opinionated, but yours.** A strong default structure you can bend — drop a space you don't need, add one you do.

---

## Quick start

1. **Copy this folder** into your workspace (Google Drive, a repo, wherever your team keeps files).
2. **Open it** in [Palette Desktop](https://palette.team) (best) — or any coding agent (Claude Code, Cursor, Codex, Gemini CLI, …).
3. **Say "set me up"** (or run `/onboard`). The agent notices the OS is still a blank template and walks you through it — you won't fill files by hand.
4. **Give it something to work from** (least effort first):
   - **Connect a tool** (Palette / an MCP connector) → it pulls your company, team, and work automatically.
   - **Drop docs in [`_inbox/`](_inbox/)** — a deck, an existing wiki export, an org chart — and it files them into the right places.
   - **Paste from another AI** — the agent hands you a prompt to run in Claude/ChatGPT, you paste the answer back.
   - **Or just answer a few questions.**
5. **Start working.** Say what you're doing; the agent pulls the right context. Setup progress is tracked in [`SETUP.md`](SETUP.md).

---

## The structure

Six **spaces** — top-level folders, each an area a team owns. Every folder is written to be scanned first, and carries the same simple furniture, so an agent can walk into any of them and know how to work there.

```
company-os/
│
├── accounts/                  # Customers — one folder per account
│   ├── status.md              #   live board: stage · health · next step
│   └── _template/             #   /new-account scaffolds a brief, health, meetings, requests
│
├── gtm/                       # Go-to-market
│   ├── foundations/           #   what you know — brand, market, strategy, product marketing
│   ├── playbooks/             #   how you think — sales, content, launches
│   ├── templates/             #   fill-in formats paired with playbooks (the launch kit)
│   ├── content/               #   the pieces — blog, email, social, changelog
│   ├── work/                  #   campaigns, projects, research (each with a _template)
│   └── team/                  #   per-person focus + writing voice
│
├── product/                   # Product
│   ├── user-feedback/         #   feedback, feature-requests, interviews, painpoints
│   ├── competitors/           #   what they ship (profile template in its README)
│   ├── specs/                 #   paste-ready spec drafts (_template)
│   ├── strategy/              #   product strategy theses
│   └── discovery/             #   open questions to explore
│
├── engineering/               # Engineering
│   ├── architecture.md        #   the cross-repo system map
│   ├── stack.md               #   what you run and why
│   ├── standards.md           #   PR, review, testing bar
│   ├── onboarding.md          #   day 1 for a new engineer
│   ├── glossary.md            #   internal terms and vendors
│   ├── decisions/             #   ADRs — why you chose X over Y
│   ├── runbooks/              #   "it's on fire, do this"
│   ├── postmortems/           #   blameless incident write-ups
│   └── security/              #   posture, policies, compliance
│
├── ops/                       # Operations (founders-only)
│   ├── finance/               #   budgets, forecast, cap table
│   ├── investors/             #   updates, rounds, data room
│   ├── admin/                 #   legal, agreements, office
│   └── hiring/                #   company-wide hiring
│
├── people/                    # How to work with each teammate (agents read this to adapt)
│   └── _template/             #   /new-person scaffolds each profile (README, lessons, log)
│
├── AGENTS.md                  # How agents behave here — the source of truth
├── CLAUDE.md · GEMINI.md      # thin pointers so each agent auto-loads AGENTS.md (Mistral: .vibe/AGENTS.md)
├── README.md                  # this map
├── SETUP.md                   # onboarding checklist (delete when done)
├── lessons.md · log.md        # memory: what to do differently · what happened
├── _inbox/                    # drop existing docs here to prefill the OS
├── assets/                    # logos, brand images, the README hero
├── .agents/                   # canonical commands + skills (every agent reads these)
├── .claude/                   # thin adapters so Claude registers the commands
└── .vibe/                     # thin pointer so Mistral (Vibe) auto-loads AGENTS.md
```

**Every space** has a `README.md` (its front door), a `lessons.md` (what to do differently), and a `log.md` (what happened). A space adds its own `AGENTS.md` only when it needs a distinct way of working (`gtm/`, `product/`, `ops/`, and `engineering/` do).

---

## Inside the template

Five ideas hold the whole thing together:

1. **Spaces** — top-level areas a team owns. Keep the six that fit, drop the rest, add your own with `/create-space`.
2. **The four files** — `README` (what's here + what to do), optional `AGENTS.md` (how to think here), `lessons.md` (corrections), `log.md` (history).
3. **Front matter on everything** — a little YAML (`type`, `owner`, dates, `edit_policy`) so files are queryable and safe to edit. Stamped on creation.
4. **Link, don't duplicate** — the OS holds the durable *why* and points to your live systems (code host, issue tracker, docs, CRM) for the rest.
5. **It improves itself** — every session can leave a line in `lessons.md` (what to do differently) or `log.md` (what happened). `/reflect` promotes the recurring lessons into the guides agents read every time — so the OS gets *sharper* with use instead of rotting.

Full conventions live in [`AGENTS.md`](AGENTS.md).

---

## Commands

Scaffold with commands so everything stays correctly stamped and registered — never hand-copy.

| Command | What it does |
|---|---|
| `/onboard` | Set the OS up for your company (connector / docs / Q&A). Runs on first open. |
| `/create-space` | Add a new top-level space, to convention, registered in the map. |
| `/new-account` | Scaffold a customer folder and add it to the status board. |
| `/new-person` | Scaffold a teammate's `people/` folder. |
| `/finish-session` | Wrap up: recap, follow-ups, a memory line. |
| `/reflect` | Tidy the memory files and promote recurring lessons into the guides. |
| `/workspace-heal` | Audit for broken links, stale listings, drift, unfinished setup. |

Plus a `prefill-context` skill with copy-paste prompts for pulling context out of other AIs and tools.

## How it stays clean

Left alone, any wiki rots. This one has habits built in: **scaffold with the commands**, **capture as you go** (`lessons.md` / `log.md`), and **sweep weekly** (`/workspace-heal` + `/reflect`). `AGENTS.md` → *Keeping the OS healthy* spells out the cadence, and a connector can run it on a schedule.

## Works with any agent

`AGENTS.md` is the shared source of truth; `CLAUDE.md` / `GEMINI.md` (and `.vibe/AGENTS.md` for Mistral) are thin pointers so Claude, Gemini, Codex, and Mistral all load the same rules. No per-agent prompt drift.

## Works great with Palette Desktop

It's just files, so it runs anywhere — but [Palette Desktop](https://palette.team) is built for exactly this and makes it sing:

- **You own your files.** It's your folder on your drive — no lock-in, readable with or without Palette.
- **Any agent, one context.** Point Claude, Gemini, or Codex at the same folder; they all read the same `AGENTS.md`.
- **Safe, parallel work.** Every session is a sandboxed copy, so teammates (and agents) can work at the same time without stepping on each other, then merge back.
- **Checkpoints.** Snapshot the whole workspace and roll back anytime.
- **Live context.** Connect your tools and the OS stays current — the connector fills and refreshes context instead of you re-explaining it.

---

## Make it yours

This ships opinionated but generic — every specific is a `[placeholder]` or an example (e.g. "your issue tracker (Linear, Notion, …)"), never an assumption about your stack, size, or motion. `/onboard` swaps the placeholders for your reality; `/create-space` grows it from there.

*Built by [Palette](https://palette.team). Copy it, rename it, make it yours.*

---

## After setup: what this file becomes

Everything above is the **template landing page** — the pitch a newcomer reads on GitHub or when they first copy the folder. It isn't meant to live forever.

During `/onboard` (or your first cleanup), **replace all of it with the short router below** and fill it in. From then on the root `README.md` is your OS's living index — the map agents read at the start of every session, and where `/create-space` registers new spaces. It's the same shape every space's own `README.md` uses: a front door, not a sales page.

<!-- ONBOARD: replace the entire landing page above with this block, filled in. This becomes the living root index. -->

```markdown
---
type: index
owner: [Owner]
status: active
last_updated: YYYY-MM-DD
last_updated_by: [Owner]
edit_policy: open
---

# [Company] OS

**[One line: what your company does.]**

The shared, AI-readable home for how [Company] works and what's active.
New here? This page is your map. Agents: read `AGENTS.md` first, then the space you're working in.

## Structure

| Space | What lives here |
|---|---|
| `accounts/` | Customers — one folder per account |
| `gtm/` | Go-to-market — brand, playbooks, campaigns, content |
| `product/` | Product — feedback, specs, strategy, discovery |
| `engineering/` | Architecture, decisions, standards, runbooks |
| `ops/` | Finance, investors, admin, hiring (founders-only) |
| `people/` | How to work with each teammate |

## Owners

| Space | Owner | Last reviewed |
|---|---|---|
| `accounts/` | [Owner] | YYYY-MM-DD |
| `gtm/` | [Owner] | YYYY-MM-DD |
| `product/` | [Owner] | YYYY-MM-DD |
| `engineering/` | [Owner] | YYYY-MM-DD |
| `ops/` | [Owner] | YYYY-MM-DD |
| `people/` | [Owner] | YYYY-MM-DD |
```
