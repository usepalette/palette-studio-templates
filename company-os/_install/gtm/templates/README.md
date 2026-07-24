---
type: index
owner: [Owner]
status: draft
last_updated: YYYY-MM-DD
last_updated_by: [Owner]
edit_policy: team
---

# Templates

Reusable **fill-in formats** — the modular partner to `../playbooks/`. A playbook tells you *what to do and how to think*; a template gives you the exact *format to fill in*. You read the playbook to decide, then copy the template to produce.

This is the shape we want the OS to grow in: **codify a repeatable output once as a template, and every future one comes out consistent** — same structure, same quality bar, no reinventing.

## What's here

| Folder | Pairs with | What's inside |
|---|---|---|
| `launch/` | `../playbooks/launch.md` | Fill-in templates for launch content — messaging brief, changelog, blog, docs, social, and more |

Add your own categories as you codify outputs (e.g. `proposals/`, `decks/`, `one-pagers/`). Each new template starts with a short "how to write this" section, then a fill-in block.

## How templates work

- **The template is the source of truth for shape.** Extend a template and every future output inherits the change — you fix it in one place.
- **They compose with the guides.** A template loads your `foundations/brand/` (voice, messaging) so outputs stay on-brand without repeating the rules in every file.
- **Copy, don't edit in place.** Copy a template to where the work lives (a launch folder, an account's `shareables/`), then fill it in.
