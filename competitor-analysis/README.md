# Competitor Analysis

Track competitors with structure: a landscape doc, per-competitor profiles,
and skills that handle research and adding new entries.

## What you get

- **`landscape.md`** — the synthesis: tier table, threat assessment, your
  structural advantages, open research questions.
- **`competitors/`** — one profile per competitor, following a consistent
  template (positioning, pricing, strengths, weaknesses, threat level,
  sources).
- **`competitor-research` skill** — knows where profiles live, how to
  research a competitor, and how to format the output. Auto-invoked when
  you're working on competitor profiles.
- **`add-competitor` skill** — invokable as `/add-competitor` or just by
  asking "add Acme as a competitor."

## How install works

When you install this workflow, an agent will ask:

1. Where should the market folder live? (suggests `gtm/foundations/market/`,
   but defers if you already have a research or strategy folder.)
2. What's your product/company name? (pulled from the Palette MCP if
   available, otherwise asked.)
3. Which 2–5 competitors should we seed?
4. Should we research the seeded competitors now, or leave them as
   placeholders for later? (You can fill placeholders in any time with
   `/add-competitor <name>`.)

Then it writes everything into your project. Palette Desktop creates a checkpoint
right before the install so you can revert from the timeline if you want
to start over.

## After install

Run `/add-competitor` whenever you want to track another competitor — or
just say it in natural language. The skill handles the research, writes
the profile, and updates `landscape.md` so the synthesis stays in sync.
