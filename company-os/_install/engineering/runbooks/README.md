---
type: index
owner: [Owner]
status: draft
last_updated: YYYY-MM-DD
last_updated_by: [Owner]
edit_policy: team
---

# Runbooks

"It's on fire, do this." Operational how-tos for the moments when something breaks or a risky operation has to happen — deploy, rollback, a database migration, a service restart. Written so someone who *isn't* the expert can follow them under pressure.

## When to add one

Any time you do an operation that's risky, rare, or that only one person knows how to do — write it down before you forget. If you had to figure it out at 2am, the next person shouldn't have to.

## How

1. Copy `_template.md` to `<name>.md` (e.g. `deploy.md`, `rollback.md`, `db-migration.md`).
2. Write the steps so they're followable cold — exact commands, not "you know the drill."
3. Keep it current — a stale runbook is worse than none.

## Index

| Runbook | For |
|---|---|
| _[deploy.md]_ | _[shipping to production]_ |
