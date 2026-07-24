---
type: index
owner: [Owner]
status: draft
last_updated: YYYY-MM-DD
last_updated_by: [Owner]
edit_policy: team
---

# Decisions (ADRs)

Architecture Decision Records — the durable *why* behind significant technical choices. One file per decision, so the reasoning survives even when the people who made it move on.

## When to write one

Write an ADR for a choice that's **hard to reverse, affects multiple people/repos, or that someone will later ask "why did we do it this way?"** Not every choice needs one — routine calls don't.

## How

1. Copy `_template.md` to `YYYY-MM-DD-<short-title>.md`.
2. Fill it in. Keep it tight — context, the decision, the consequences.
3. Link it from `../architecture.md` if it shapes the system map, and link the issue/PR trail (don't copy it).
4. Add a row to the index below.

**Status lifecycle:** `proposed` → `accepted` → (later) `superseded by <newer ADR>`. Never delete a superseded ADR — mark it and link forward.

## Index

| # / Date | Decision | Status |
|---|---|---|
| _[YYYY-MM-DD]_ | _[the first decision]_ | _[accepted]_ |
