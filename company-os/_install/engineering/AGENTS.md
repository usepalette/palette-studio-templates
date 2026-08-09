---
type: doc
---

# engineering — how to work here

Company-wide rules live in the root [`../AGENTS.md`](../AGENTS.md); this file adds the engineering-specific posture. Read the [`README.md`](README.md) first (structure + the **What lives elsewhere** table + **surface ownership**), then work the way below.

## Mindset

- **The code is the source of truth.** For anything about how the system actually works, the repos win over any doc here or in a wiki. When a doc and the code disagree, fix the doc. Don't state a stack or architecture fact you haven't checked against the code.
- **Security is not optional.** Treat any cross-tenant or trust boundary as sacred, and prefer designs that **fail closed**. Incidents around a silent wrong-permission or wrong-tenant serve are the dangerous class.
- **Durable why, not live status.** This folder holds decisions and stable operating knowledge. Current sprint/ticket status lives in your issue tracker and the live connector — read it live, never paste it into files.
- **Postmortems are blameless.** Write about the system and contributing factors, never individuals.

## Source-of-truth discipline (don't duplicate)

Follow the **What lives elsewhere** table in the README. Your code host is canonical for code (synthesize + link, don't copy); your issue tracker is canonical for tasks and decision tracking (link, never duplicate — an ADR carries the durable *why* and links the issue trail); a wiki is reference (link, or copy in deliberately, never mirror); the live connector is live context (read, don't copy).

## Conventions

- New markdown files start with frontmatter (`type`, `owner`, `status`, dates, `edit_policy`) per the root conventions. ADRs use `decisions/_template.md`; runbooks use `runbooks/_template.md`; postmortems use `postmortems/_template.md`.
- Set a doc's `owner` to the surface owner from the README's ownership table; set `last_updated_by` to the person you're working for — never an agent name.
- If you're recording something unverified (from a chat sweep, or not yet checked against the code), mark it clearly so a reviewer knows to confirm it.
