---
type: command
description: Add a product teammate using the team profile template
argument-hint: "<name> [email] [role]"
---

# New person

Create `team/<name>/` from `team/_template/`.

## Inputs

- Full name is required.
- Email and role are optional, but ask one concise question when either is needed to identify or
  route work correctly.
- Resolve the folder slug as lowercase kebab-case.

## Process

1. Search `team/` for an existing matching name or email. If one exists, offer to update it rather
   than creating a duplicate. Read the matched profile's frontmatter first and honor its
   `edit_policy`: profiles are `owner-only`, so unless you are acting for that owner, propose the
   change and get the owner's approval before writing. This applies to every later edit too, not
   just the first.
2. Show the proposed name, email, role, folder, and owner-only edit policy.
3. After confirmation, create:
   - `team/<name>/README.md`
   - `team/<name>/lessons.md`
   - `team/<name>/log.md`
4. Fill known fields. In the created living profile, write `unknown` or omit an optional item
   rather than copying template placeholders.
5. Add or update the `## Product contributors` table in `team/README.md` with name, role, and
   ownership.
6. Set `owner` to the profile subject. Stamp `last_updated_by` with the current human making the
   change, which may be a different person.

Never invent communication preferences or ownership. Propose them, then confirm.
