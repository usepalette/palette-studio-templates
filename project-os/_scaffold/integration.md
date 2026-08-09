# Project OS — install guide

You just installed Project OS into the user's project — a single-project workspace: one
folder for the context, meetings, decisions, research, design, deliverables, and team of one
engagement, with a live status dashboard (`overview.html`) generated from the markdown.

It ships **pre-filled with a sample project** (*Acme Co. — Customer Portal Rebuild*) so the
dashboard works the moment they open it. Every sample file is flagged `sample: true`, and
`/onboard` replaces the sample with the user's real project.

## What to do

1. Tell the user briefly what Project OS is — one or two sentences. Point them at
   `overview.html` for the live dashboard (it currently shows the Acme sample, with a banner
   saying so). Don't read `AGENTS.md` or the README to them.

2. Run the `/onboard` command — do this now, as part of install; don't wait for the user to
   ask. It walks through the project basics (name, client, dates, leads), stakeholders, scope,
   and goals — then replaces the sample with real content, swaps the README landing page for
   the project index, and regenerates the dashboard. The full conversational flow is defined
   in the canonical `.agents/commands/onboard.md` (already placed; `.claude/commands/onboard.md`
   is a thin adapter pointing at it) — follow it as written. Prefer pulling context from the
   Palette MCP or docs the user drops in `_inbox/` before asking questions; keep any questions
   to one short round. If the user wants to stop partway, leave the open boxes in `SETUP.md` —
   that's the signal for the next session to resume, and `/onboard` is safe to re-run.

3. After `/onboard` finishes, give a quick summary:
   - What you filled in (project metadata in `context/project.md`, stakeholders, scope, goals).
   - That the Acme sample is cleared and the `sample: true` flags removed (the dashboard's
     sample banner is now gone).
   - What's intentionally still light — `meetings/`, `decisions/`, `research/` fill up as the
     project runs, via `/new-meeting` and `/new-decision`.
   - The upkeep habits: `/finish-session` after any meaningful work session (it captures the
     memory line, so skipping it loses that session's context), and `/workspace-heal` weekly to
     keep the structure clean.

## Notes

- `AGENTS.md` is the source of truth for how agents behave here; the README is the human front
  door and, after onboard, the project index. `context/project.md` holds the dashboard's data.
- If the project isn't technical, `/onboard` offers to trim folders that don't fit (e.g.
  `research/`, `design/`).
- Source code and secrets never live in this workspace — it holds the durable context and
  links out to the rest.
