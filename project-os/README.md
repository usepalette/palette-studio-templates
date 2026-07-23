# Project OS

One project as a file system — the context, decisions, meetings, research, design, and deliverables for a single engagement, in one folder your whole team, your client, *and* every AI agent work from. Plain markdown, plus a live status **dashboard** generated straight from your files.

Built for teams running one project or client engagement with AI agents — agencies, consultancies, and internal project teams.

## What you get

- **A status dashboard for free** — `overview.html` renders a timeline, goals, stakeholders, milestones, and recent activity from your markdown frontmatter. No separate status deck to maintain.
- **The project's folders** — `context/` (brief, goals, stakeholders, glossary), `meetings/`, `decisions/` (ADR-style), `research/`, `design/`, `team/` (how the team works), `deliverables/`, and `admin/` (scope, timeline). Each with a README front door.
- **Commands** — `/onboard` to set it up, `/new-decision` and `/new-meeting` to scaffold entries (numbered, stamped, indexed), and `/finish-session` and `/workspace-heal` to keep it healthy.
- **Multi-agent by design** — `AGENTS.md` is the shared source of truth; `CLAUDE.md` / `GEMINI.md` / `.vibe/AGENTS.md` are thin pointers so Claude, Gemini, Codex, and Mistral all follow the same rules.
- **A memory that compounds** — root `lessons.md` (what to do differently) and `log.md` (what happened) so context doesn't evaporate between sessions.

## How install works

This template ships **pre-filled with a sample project** (*Acme Co. — Customer Portal Rebuild*) so the dashboard works the moment you open it — nothing looks empty. When you install, an agent will:

1. Place the workspace on disk (the folders, the dashboard, the commands).
2. Run `/onboard` — pulling your project, client, stakeholders, and timeline from the Palette MCP or dropped docs where it can, and asking you for the rest in one short round — then **replace the sample with your real project** and regenerate the dashboard.

Palette Desktop creates a checkpoint right before install so you can revert.

## After install

```bash
# open overview.html for the live dashboard, then:
set me up                 # (or /onboard) replace the sample with your project
/new-decision "Use Postgres over Mongo"   # log a decision, numbered + indexed
/new-meeting "Weekly client sync"         # scaffold meeting notes
/finish-session           # wrap up: recap, follow-ups, a memory line
/workspace-heal           # weekly audit: links, indexes, dashboard drift
```

Open `overview.html` any time for the project status at a glance. Everything else is plain markdown you can read, edit, and version-control.
