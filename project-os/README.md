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
2. Run `/onboard` automatically, right there in the install conversation — pulling your project, client, stakeholders, and timeline from the Palette MCP or dropped docs where it can, and asking you for the rest in one short round — then **replace the sample with your real project** and regenerate the dashboard.

You never have to trigger onboarding yourself. If it doesn't finish in one go (you close the session, or you'd rather fetch the SOW first), the next agent to open the folder sees the unchecked boxes in `SETUP.md` and offers to pick up where it left off — or you can say **"set me up"** (or run `/onboard`) to resume it on demand. Onboarding is safe to re-run: it detects what's already real and only fills the gaps.

Palette Desktop creates a checkpoint right before install so you can revert.

## After install

Open `overview.html` for the live dashboard. Then, in your agent, these commands are available:

```text
/onboard        resume or re-run setup (also triggered by saying "set me up")
/new-decision   log a decision, numbered + indexed — e.g. /new-decision "Use Postgres over Mongo"
/new-meeting    scaffold meeting notes, stamped + indexed — e.g. /new-meeting "Weekly client sync"
/finish-session wrap up a session: recap, follow-ups, a memory line
/workspace-heal weekly audit: links, indexes, dashboard drift
```

These are agent commands, not shell commands — type them to your coding agent, or just describe what you want in plain language. Everything else is plain markdown you can read, edit, and version-control.
