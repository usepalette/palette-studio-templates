---
type: command
description: Scaffold a teammate's team/<name>/ folder (profile + voice), stamped and ready
argument-hint: "<name> [role]"
---

# New Person

Scaffold a `team/<name>/` folder from `team/_template/` so a teammate's GTM profile and writing voice are correctly stamped and complete — instead of hand-copying (which drifts: missing files, unstamped frontmatter). The teammate companion to `/new-account`.

## Trigger

`/new-person Alex`, `/new-person Alex "Head of Sales"`, or bare `/new-person` (then ask for the name).

## Inputs

1. **Name** (required) — slug it kebab-case (`Alex Chen` → `alex-chen`).
2. Anything you already know — role, current focus, how they like to write. Don't fabricate.

## Process

1. **Check it doesn't exist.** If `team/<slug>/` already exists, stop and offer to open it.
2. **Copy the template.** Create `team/<slug>/` from `team/_template/` — `README.md` (profile) and `voice.md` (their writing voice). Keep both.
3. **Stamp it.** Fill the name, role, and any focus you were given into `README.md`; leave the rest as the template's prompts. Set `last_updated` / `last_updated_by`.
4. **No fabrication.** Leave placeholders where you have no real info — people refine their own profiles over time.
5. **Confirm.** Print the path created.

## Notes

- Assumes `team/_template/` exists — if it doesn't, stop and flag it rather than inventing a structure.
- `voice.md` is what `/review` and content work read to make writing sound like this person — worth filling in properly.
- Live context (what they're working on now) comes from the connector, not this folder — don't paste it in.
