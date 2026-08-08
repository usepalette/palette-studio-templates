---
type: command
description: Scaffold a decisions/NNNN-slug.md from the template, auto-numbered, and index it
argument-hint: "<short decision title>"
---

# New Decision

Scaffold `decisions/NNNN-slug.md` from `decisions/TEMPLATE.md` and add it to the decisions index — so a decision is correctly numbered, stamped, and registered, instead of hand-copying (which drifts: skipped numbers, unstamped frontmatter, a file that never makes it into the index).

## Trigger

`/new-decision Use Postgres over Mongo`, or bare `/new-decision` (then ask for the title).

## Inputs

1. **Decision title** (required) — a short summary of the call being made. Slug it kebab-case (`Use Postgres over Mongo` → `use-postgres-over-mongo`).
2. Anything you already know — the context, the options, who decided. Don't fabricate; leave the template's prompts where you don't know.

## Process

1. **Find the next number.** List `decisions/NNNN-*.md`, take the highest `NNNN`, add one, and zero-pad to 4 digits (`0007`). If none exist yet, start at `0001`.
2. **Claim the number, don't overwrite it.** Create `decisions/<NNNN>-<slug>.md` from `decisions/TEMPLATE.md` **only if no file with that `NNNN` already exists** — decision records are immutable, so never write over one. If the number is taken (another agent or teammate claimed it between your listing and your write), re-run step 1 and retry with the new highest + 1. Repeat until the create succeeds; if it keeps colliding, stop and tell the user rather than guessing.
3. **Stamp it.** Fill the title heading and frontmatter: `type: decision`, the decision number, `date` = today (`YYYY-MM-DD`), `status` (e.g. `proposed`), `last_updated` = today, and `last_updated_by` = **the human you're doing this for**, not you the agent (ask if you don't know who to credit). These files are a record of who decided what — an agent name in that field makes the record useless.
4. **Add to the index.** Append a row to the table in `decisions/README.md`: `| [<NNNN>](<NNNN>-<slug>.md) | <title> | <date> | <status> |` (match the index's actual columns — the number is the link).
5. **Update the dashboard.** The project tracks recent decisions in `context/project.md` frontmatter (`recentDecisions`) — add this decision there (newest first), then regenerate the `overview.html` `data-snapshot` so the dashboard reflects it (see `AGENTS.md` → "The dashboard").
6. **No fabrication.** Where a section has no real info, leave the template's placeholder.
7. **Confirm.** Print the path created, the index row added, and the dashboard update.

## Notes

- Assumes `decisions/TEMPLATE.md` exists — if it doesn't, stop and flag it rather than inventing a structure.
- Keep the decision record tight — context, options considered, the call, and why. Detail and discussion live in `meetings/` or linked docs.
