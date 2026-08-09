---
type: index
owner: "[Owner]"
status: draft
last_updated: YYYY-MM-DD
last_updated_by: "[Owner]"
edit_policy: everyone
---

# GTM OS

**Your go-to-market as a file system** — one folder of markdown for your commercial knowledge, active work, and team processes, that your team *and* every AI agent work from.

Instead of brand voice, positioning, playbooks, and account context scattered across Docs, Notion, and people's heads, it lives in one readable structure agents load before they act — so you stop re-explaining your GTM every session.

> Works with any coding agent — Claude Code, Cursor, Codex, Gemini CLI, and more. Works *best* in [Palette Desktop](https://palette.team), where your team shares one workspace and it stays in sync with your live tools.

---

## Quick start

1. **Open this folder** in [Palette Desktop](https://palette.team) (best) — or any coding agent.
2. **Say "set me up"** (or run `/onboard`). The agent notices the OS is still a blank template and walks you through it — you won't fill files by hand.
3. **Give it something to work from** (least effort first): connect the Palette connector, drop existing docs (a deck, a positioning doc), paste from another AI, or just answer a few questions.
4. **Start working.** Say what you're doing ("draft a launch post", "prep me for the Acme call") and the agent pulls the right context.

---

## The structure

```
gtm-os/
│
├── foundations/          # What you know — brand, market, strategy, product marketing
│   ├── brand/            #   voice, messaging, positioning
│   ├── market/           #   ICP, competitive intel
│   ├── strategy/         #   GTM strategy
│   └── product-marketing/#   product narrative, sales story
├── work/                 # What you're doing — campaigns, projects, research, content
├── accounts/             # Customer accounts (/new-account)
├── playbooks/            # How you think — philosophy + approach per domain (sales, content, launch)
├── templates/            # Fill-in formats to produce content — the launch kit, paired with playbooks
├── team/                 # Who you are — context + writing voice per person (/new-person)
├── log/                  # Fuller session recaps (the richer memory superset)
│
├── AGENTS.md             # How agents behave here — the source of truth
├── CLAUDE.md · GEMINI.md # thin pointers so each agent auto-loads AGENTS.md (Mistral: .vibe/AGENTS.md)
├── README.md             # this map → becomes your living index after setup
├── SETUP.md              # onboarding checklist (delete when done)
├── lessons.md · log.md   # memory: what to do differently · what happened
├── .agents/              # canonical commands + skills (every agent reads these)
├── .claude/              # thin adapters so Claude registers the commands
└── .vibe/                # thin pointer so Mistral (Vibe) auto-loads AGENTS.md
```

Every folder has a `README.md` (its front door). The memory (`lessons.md`, `log.md`) lives once, at the root.

---

## Commands

Scaffold with commands so everything stays correctly stamped and indexed.

| Command | What it does |
|---|---|
| `/onboard` | Set the OS up for your company (connector / docs / Q&A). Runs on first open. |
| `/new-account` | Scaffold a customer folder and add it to the status board. |
| `/new-person` | Scaffold a teammate's `team/` folder (profile + voice). |
| `/review` | Review your work against brand, hygiene, and completeness before sharing. |
| `/finish-session` | Wrap up: recap, follow-ups, a memory line. |
| `/workspace-heal` | Audit for broken links, stale indexes, and unfinished setup. |

Plus a `prefill-context` skill with copy-paste prompts for pulling context out of other AIs and tools.

## Works with any agent, great with Palette Desktop

`AGENTS.md` is the shared source of truth; `CLAUDE.md` / `GEMINI.md` / `.vibe/AGENTS.md` are thin pointers so Claude, Gemini, Codex, and Mistral all load the same rules — no per-agent prompt drift. It's just files, so it runs anywhere — but [Palette Desktop](https://palette.team) is built for exactly this.

*Built by [Palette](https://palette.team). Copy it, rename it, make it yours.*

---

## After setup: what this file becomes

Everything above is the **template landing page**. During `/onboard`, **replace this whole landing page with the short router below** — swap the minimal frontmatter for the index block, and fill in the body. From then on the `README.md` is your GTM OS's living front door.

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

# [Company] GTM OS

**[One line: what your company does.]**

The shared, AI-readable home for how [Company] goes to market.
New here? This page is your map. Agents: read `AGENTS.md` first, then the folder you're working in.

## Where things live

| Folder | What lives here |
|---|---|
| `foundations/` | Brand, market, strategy, product marketing |
| `work/` | Campaigns, projects, research, content |
| `accounts/` | Customer accounts |
| `playbooks/` | How the team thinks about each domain |
| `team/` | Per-person focus + writing voice |
| `log/` | Session recaps |

## Owners

| Area | Owner |
|---|---|
| Brand & content | [Owner] |
| Market & strategy | [Owner] |
| Accounts | [Owner] |
```
