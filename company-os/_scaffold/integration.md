# Company OS — install guide

You just installed Company OS into the user's workspace — a whole-company operating system: one
folder of markdown for how the company works and what's active, across six spaces (`accounts/`,
`gtm/`, `product/`, `engineering/`, `ops/`, `people/`), readable by the team and every AI agent.

It ships as a **blank template**: the folders, conventions, commands, and `[bracket placeholders]`
are in place, waiting to be filled with the user's real company. There is no sample data.

## What to do

1. Tell the user briefly what Company OS is — one or two sentences. Don't read `AGENTS.md` or the
   README to them.

2. Run the `/onboard` command. It's a conversational setup that captures the company basics,
   which of the six spaces to keep, the team, and the brand voice — then fills the templates and
   swaps the README landing page for the company's living index. The full flow is defined in
   `.claude/commands/onboard.md` (already placed) — follow it as written. Prefer pulling context
   from the Palette MCP or docs the user drops in `_inbox/` before asking questions; keep any
   questions to one short round, and never fabricate — propose, then confirm.

3. After `/onboard` finishes, give a quick summary:
   - What you filled in (company basics, kept/dropped spaces, owners) and who was added to `people/`.
   - The scaffolding commands they'll use next: `/new-account` (a customer), `/new-person` (a
     teammate), `/create-space` (a new area).
   - The weekly habit: `/finish-session` each session, `/workspace-heal` + `/reflect` to keep it clean.

## Notes

- `AGENTS.md` is the source of truth for how agents behave; each space has its own `README.md`
  (and sometimes an `AGENTS.md`) that layers on local rules.
- Projects and tasks are meant to live in the user's issue tracker (Linear, etc.), not as markdown
  here — the OS holds the durable context around that work.
- Source code and secrets never live in this workspace — it links out to the code host, CRM, and
  docs for the rest.
