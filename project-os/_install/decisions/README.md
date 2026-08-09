---
type: index
owner: "[Owner]"
status: active
last_updated: YYYY-MM-DD
last_updated_by: "[Owner]"
edit_policy: everyone
---

# decisions/

Lightweight log of project decisions — what we chose, and why.

## Why this folder exists

Decisions get made in meetings, chat, and hallways. Six weeks later, no one remembers *why*. This folder is the durable record.

## When to log a decision

Log it here if it answers "**why did we do it that way?**" — for example:

- A trade-off between two real options
- A scope or priority change
- A technical or design direction with consequences
- A change of mind from an earlier decision

Don't bother logging trivial choices.

## Convention

- **Filename:** `NNNN-short-title.md`, padded to 4 digits, e.g. `0007-use-postgres-for-events.md`.
- **Template:** copy [`TEMPLATE.md`](./TEMPLATE.md) — or run `/new-decision`, which numbers, stamps, and indexes it for you.
- **Don't delete or rewrite old decisions.** A decision record is immutable history. If a decision is superseded, add a new file and mark the old one as superseded — never edit the original away.
- **The one exception:** decision files flagged `sample: true` in their frontmatter are shipped template examples, not history. Those may be deleted during initial onboarding. Anything without that flag stays.

## Index

| # | Decision | Date | Status |
| - | -------- | ---- | ------ |
| [0001](0001-rebuild-not-refit.md) | Rebuild the portal, don't refit the legacy one | 2026-06-10 | accepted |

_(The 0001 entry is sample data — replace it with your real decisions.)_

---
_Edit this README to match how your team uses this folder._
