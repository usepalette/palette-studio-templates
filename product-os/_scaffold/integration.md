# Product OS - install guide

You just installed Product OS into the user's workspace: one folder of markdown for user feedback,
painpoints, feature requests, discovery, strategy, specs, competitors, and team input, readable by
the team and every AI agent.

It ships as a **blank template**. The folders, commands, conventions, dashboard, and
`[bracket placeholders]` are in place. There is no sample company or customer data.

## What to do

1. Briefly tell the user what Product OS is. Keep it to one or two sentences. Do not read
   `AGENTS.md` or the README aloud.

2. Run `/onboard`. The full flow lives in `.agents/commands/onboard.md`, with a Claude adapter at
   `.claude/commands/onboard.md`. Prefer a live context connector and documents in `_inbox/` before
   asking questions. Keep questions to one short round. Never invent product facts, users, team
   members, priorities, or integrations. A solo user and `not used` systems are valid. Separate
   the workspace owner from the current human used for `last_updated_by`. Propose, confirm, then
   write.

3. After setup, summarize:
   - What was filled in: product overview, working shape, feedback path, optional live systems,
     and current product direction.
   - What remains intentionally `unknown` or `not used` in living content.
   - The first useful commands: `/feedback`, `/synthesize-feedback`, `/spec`, and `/review`.
   - The maintenance habit: `/finish-session` after meaningful work and `/workspace-heal` weekly.

## Notes

- `AGENTS.md` is the source of truth for agent behavior. `CLAUDE.md`, `GEMINI.md`, and
  `.vibe/AGENTS.md` only point to it.
- When the team uses an issue tracker, it remains the source of truth for initiatives, projects,
  and tasks. Product OS holds durable evidence, reasoning, and paste-ready drafts, not a second
  roadmap. If the team does not use a tracker, setup records `not used`.
- Source code and secrets do not belong here. Bulk or restricted raw exports should stay in their
  controlled source; use `_inbox/` only for temporary material the workspace audience may access.
