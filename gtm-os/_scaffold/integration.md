# GTM OS — install guide

You just installed GTM OS into the user's workspace — a go-to-market operating system: one folder
of markdown for brand, market, strategy, playbooks, accounts, team, and active work, readable by
the team and every AI agent.

It ships as a **blank template**: the folders, conventions, commands, and `[bracket placeholders]`
are in place, waiting to be filled with the user's real company. There is no sample data.

## What to do

1. Tell the user briefly what GTM OS is — one or two sentences. Don't read `AGENTS.md` or the
   README to them.

2. Run the `/onboard` command. It's a conversational setup that captures company basics, product,
   market, brand voice, and the team — then fills the foundation files and swaps the README landing
   page for the company's living index. The full flow is defined in `.agents/commands/onboard.md`
   (already placed) — follow it as written. Prefer pulling context from the Palette MCP or docs the
   user drops in `_inbox/` before asking questions; keep questions to one short round; never
   fabricate — propose, then confirm.

3. After `/onboard` finishes, give a quick summary:
   - What you filled in (`foundations/`, brand voice) and who was added to `team/`.
   - The commands they'll use next: `/new-account` (a customer), `/new-person` (a teammate),
     `/review` (check work against brand + hygiene), `/finish-session` after any meaningful work
     session, and `/workspace-heal` weekly.

## Notes

- `AGENTS.md` is the source of truth for how agents behave; each folder has its own `README.md`.
- Source code and secrets never live in this workspace — the OS links out to the CRM, docs, and tools.
