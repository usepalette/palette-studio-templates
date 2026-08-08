---
type: command
description: Scaffold a meetings/YYYY-MM-DD-slug.md from the template, stamped and indexed
argument-hint: "<meeting title>"
---

# New Meeting

Scaffold `meetings/YYYY-MM-DD-slug.md` from `meetings/TEMPLATE.md`, stamp today's date, and add it to the meetings index — so meeting notes are correctly dated, stamped, and registered, instead of hand-copying (which drifts: wrong date, unstamped frontmatter, notes that never make it into the index).

## Trigger

`/new-meeting Weekly client sync`, or bare `/new-meeting` (then ask for the title).

## Inputs

1. **Meeting title** (required) — what the meeting is. Slug it kebab-case (`Weekly client sync` → `weekly-client-sync`).
2. Anything you already know — attendees, agenda, the date if it isn't today. Don't fabricate.

## Process

1. **Copy the template.** Create `meetings/<YYYY-MM-DD>-<slug>.md` from `meetings/TEMPLATE.md`, using today's date (or a date the user gives). If a file for that date + slug already exists, stop and offer to open it.
2. **Stamp it.** Fill the title heading and frontmatter: `type: meeting`, `date` = the meeting date, attendees if known, `last_updated` = today, and `last_updated_by` = **the human you're doing this for**, not you the agent (ask if you don't know who to credit). These notes are a record of who was in the room — an agent name in that field makes the record useless.
3. **Add to the index.** Add it to the listing in `meetings/README.md`: `| [<YYYY-MM-DD> — <title>](<YYYY-MM-DD>-<slug>.md) | <attendees> |` (match the index's actual columns).
4. **Update the dashboard.** The project tracks recent meetings in `context/project.md` frontmatter (`recentMeetings`) — add this meeting there (newest first), then regenerate the `overview.html` `data-snapshot` so the dashboard reflects it.
5. **No fabrication.** Leave the template's placeholders where you have no real info.
6. **Confirm.** Print the path created, the index row added, and the dashboard update.

## Notes

- Assumes `meetings/TEMPLATE.md` exists — if it doesn't, stop and flag it rather than inventing a structure.
- After the meeting, log any decisions with `/new-decision` and sweep follow-ups with `/finish-session`.
