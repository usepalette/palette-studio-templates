---
type: command
description: Scaffold an accounts/<name>/ folder from the template and register it on the status board
argument-hint: "<company name or domain>"
---

# New Account

Scaffold `accounts/<name>/` from `accounts/_template/` and add it to the status board — so a new customer folder is correctly stamped, complete, and registered, instead of hand-copying (which drifts: missing files, unstamped frontmatter, a folder that never makes it onto `status.md`). The account companion to `/new-person`.

## Trigger

`/new-account Acme`, `/new-account acme.com`, or bare `/new-account` (then ask).

## Inputs

1. **Company name or domain** (required) — slug it kebab-case (`Acme Corp` → `acme-corp`).
2. Anything you already know — stage, owner, key people, what they care about. Don't fabricate; leave placeholders where you don't know.

## Process

1. **Check it doesn't exist.** If `accounts/<slug>/` exists, stop and offer to open it or update it.
2. **Enrich from a connector if one is set up (optional).** If a live-context connector or your CRM/product-analytics tools are available, confirm you're querying the right tenant/workspace and that the user is entitled to the data before looking anything up. Pull what's cheap: description, domain, stage, key people, recent activity. Then **show the facts you propose to persist and write only the ones the user confirms** — an enrichment result is a suggestion, not a source of truth. If nothing's connected, skip — the template placeholders are fine to fill by hand later.
3. **Copy the template.** Create `accounts/<slug>/` from `accounts/_template/`:
   - `README.md` (the brief) — stamp frontmatter (`type: account`, `owner`, `status: active`, `last_updated` = today, `last_updated_by`, `edit_policy: team`); fill the identity table and anything you learned; leave the rest as the template's bracketed prompts.
   - `health.md`, `requests.md`, `meetings/`, `shareables/` — keep the structure; fill only what you know.
4. **Register on the status board.** Add a row to `accounts/status.md`: `| [<Company>](<slug>/) | <stage or [Lead]> | ⚪ | <today> | [next step] |`. This is the step hand-copying always forgets.
5. **No fabrication.** Where a section has no real info, leave the template's placeholder — don't invent people, metrics, or history.
6. **Confirm.** Print the path created, the status row added, and what (if anything) a connector filled vs. what's left to fill by hand.

## Notes

- Follows the per-account model in `accounts/README.md`. Keep the brief under ~120 lines; detail goes in `meetings/`.
- Create a folder only when there's real engagement — a name in the CRM doesn't need one yet (see `accounts/README.md` → "When to create a folder").
- After real meetings, keep `README.md` and `status.md` in sync (or run `/finish-session`, which refreshes the board).
