---
description: Scaffold a teammate's people/<name>/ folder from the template, stamped and ready
argument-hint: "<name> [email] [role]"
---

# New Person

Scaffold a `people/<name>/` folder from `people/_template/` so a teammate's profile is correctly stamped and complete — instead of hand-copying (which drifts: missing furniture, unstamped frontmatter, wrong `email:`). This is the person companion to `/create-space` and `/new-account`.

## Trigger

`/new-person Alex`, `/new-person Alex alex@acme.com "Head of Sales"`, or bare `/new-person` (then ask).

## Inputs

Parse from the argument; ask for what's missing. Don't fabricate — propose → confirm.

1. **Name** (required) — slug it kebab-case (`Alex Rivera` → `alex-rivera`, or just `alex` if unambiguous).
2. **Email** (required for identity matching) — how agents recognize this person at session start. Default to your company pattern (`name@<company-domain>`) and confirm.
3. **Role** (optional) — their title.
4. Optional: `slack`, `github`, `linkedin`.

## Process

1. **Check it doesn't exist.** If `people/<slug>/` already exists, stop and offer to open it.
2. **Copy the template.** Create `people/<slug>/` from `people/_template/` — `README.md` (profile), `lessons.md`, `log.md`. Keep all three (the furniture is the point).
3. **Stamp the README frontmatter** with real values: `owner` = the person's name, `email`, `role`, `status: active`, `last_updated` = today, `last_updated_by` = the person setting it up, `edit_policy: owner-only`. Fill the `# Name` heading. Leave the "How to work with me" section as guiding prompts — that's for the person to fill (or for agents to propose → confirm over time).
4. **Don't over-fill.** A thin-but-correct profile is fine; deeper preferences fill in through use. Never invent working-style preferences.
5. **Confirm.** Print the path created and note that the person should flesh out "How to work with me" when they're next in.

## Notes

- Only the person themselves (or someone acting for them) should edit their folder — it's `owner-only`.
- Live context (what they're working on) comes from the connector, not this folder — don't paste it in.
- If a live connector is set up, you may *offer* to pre-fill role/slack from it — propose → confirm, never fabricate.
