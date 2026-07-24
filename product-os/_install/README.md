---
type: index
status: draft
---

# Product OS

**Your product work as a file system.**

User feedback, interview notes, product strategy, specs, and roadmap reasoning tend to scatter
across docs, issue trackers, meeting tools, and people's heads. Product OS gives that material a
clear shape so people and agents can follow the evidence before making decisions.

> Works with Claude, Gemini, Codex, Mistral, and other agents. It works best in
> [Palette Desktop](https://palette.team), where a team can share the same files, work safely in
> parallel sessions, and connect live context.

## Quick start

1. Open this folder in Palette Desktop or another agent.
2. Say **"set me up"**, or run `/onboard`.
3. Give the agent an existing product brief, research export, feedback folder, or connected context
   if you have one. If not, answer one short round of questions.
4. Capture the first real signal with `/feedback`, find repeated patterns with
   `/synthesize-feedback`, or draft a spec with `/spec`.

Setup progress lives in [`SETUP.md`](SETUP.md).

You do not need to memorize commands. Say what happened in normal language and the agent should
recognize and run the matching workflow.

Product OS is modular. It works for a solo builder or a team, with or without a formal issue
tracker, analytics system, CRM, or live connector. During setup, unused systems are recorded as
`not used`; they are never invented or required.

## The structure

```text
product-os/
├── user-feedback/       # Raw feedback, interviews, requests, painpoints, companies, recaps
│   └── index.html       # Generated feedback dashboard
├── strategy/            # Durable claims about how the product wins
├── discovery/           # Open questions and learning plans
├── specs/               # Paste-ready product briefs
├── competitors/         # Capability-focused competitor profiles
├── team/                # How to work with each product teammate
├── team-input/          # Current roadmap input and dated sync recaps
├── documentation/       # Product overview and shared terminology
├── log/sessions/        # Fuller session recaps
├── _inbox/              # Temporary setup and import material
│
├── AGENTS.md            # Shared rules for every agent
├── CLAUDE.md            # Thin pointer to AGENTS.md
├── GEMINI.md            # Thin pointer to AGENTS.md
├── SETUP.md             # First-run checklist
├── lessons.md           # What to do differently
├── log.md               # What happened
├── .agents/             # Canonical commands and skills
├── .claude/             # Thin Claude adapters
└── .vibe/AGENTS.md      # Thin Mistral adapter
```

When the team uses an issue tracker, it remains the source of truth for initiatives, projects, and
tasks. This folder holds the durable evidence and reasoning around that work, not a second backlog.

## Commands

| Command | What it does |
|---|---|
| `/onboard` | Set up the workspace from connected context, documents, or a short conversation |
| `/feedback` | Capture raw feedback and explicit feature requests |
| `/synthesize-feedback` | Find repeated patterns and create or update painpoints |
| `/feedback-sync` | Rebuild the feedback dashboard from markdown |
| `/share-feedback` | Draft a sourced feedback recap and optionally send it after approval |
| `/spec` | Draft and save a paste-ready product spec |
| `/new-person` | Optionally add a contributor using the team template |
| `/review` | Check evidence, traceability, hygiene, and completeness |
| `/finish-session` | Capture decisions, follow-ups, and durable learning |
| `/workspace-heal` | Audit links, indexes, adapters, frontmatter, and setup drift |

## How signal moves

```text
raw feedback ──┬──> explicit ask ──> feature request ──┐
               │                                       │
interviews ────┴──> repeated problem ──> painpoint ─────┼──> discovery or spec
                                                       │
team input + competitor evidence ──────────────────────┴──> strategy
```

Not every quote becomes a painpoint. Not every painpoint becomes a feature. Product OS keeps the
links visible so the team can judge the evidence instead of trusting a summary.

## Multi-agent by design

`AGENTS.md` is the shared source of truth. `CLAUDE.md`, `GEMINI.md`, and `.vibe/AGENTS.md` point to
it without copying the rules. Canonical commands and skills live under `.agents/`; `.claude/`
contains registration adapters only.

## After setup: what this file becomes

During `/onboard`, replace this landing page with the living index below and fill in the
placeholders.

<!-- ONBOARD: replace the entire landing page above with this block, filled in. -->

```markdown
---
type: index
owner: [Workspace steward]
status: active
last_updated: YYYY-MM-DD
last_updated_by: [Setup author]
edit_policy: team
---

# [Product, product area, platform, or portfolio] Product OS

**[One line: what the product does and who it is for.]**

The shared, AI-readable home for product evidence, reasoning, and durable product knowledge.
Agents: read `AGENTS.md`, `lessons.md`, and the relevant folder README before working.

## Where things live

| Folder | What lives here |
|---|---|
| `user-feedback/` | Raw feedback, interviews, requests, painpoints, companies, recaps |
| `strategy/` | Durable product strategy theses |
| `discovery/` | Open questions and learning plans |
| `specs/` | Paste-ready product briefs |
| `competitors/` | Capability-focused competitor profiles |
| `team/` | Teammate profiles and working preferences |
| `team-input/` | Roadmap input and dated sync recaps |
| `documentation/` | Product overview and terminology |
| `log/` | Fuller session recaps |

## Live systems

| System | Role | Link |
|---|---|---|
| Work tracker, if used | Initiatives, projects, and tasks | [Link, description, or not used] |
| Feedback sources | Where raw feedback arrives | [Link, description, or manual capture] |
| Product analytics, if used | Behavioral evidence | [Link, description, or not used] |
```
