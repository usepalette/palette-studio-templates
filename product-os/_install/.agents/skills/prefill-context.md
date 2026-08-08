---
name: prefill-context
description: How to prefill Product OS from a live connector, documents in _inbox, exported context, research tools, support systems, or a short conversation. Use during /onboard or when backfilling an existing Product OS.
---

# Prefill context

Product OS should start from context the user or team already has. Work through available,
authorized sources in this order. Skip source types that do not exist and stop when there is
enough to create a useful, honest first version.

Always **propose, confirm, then write**. Never fabricate product facts, team members, users,
customers, metrics, priorities, or competitor claims.

## 1. Live context connector

If a connector exposes current company, product, people, customers, projects, or activity:

- Get a broad overview first.
- Map stable product facts to `documentation/product-overview.md`.
- Add people through `/new-person` only when profiles would be useful.
- Map current product opinions to `team-input/`, not stable team profiles.
- When an issue tracker exists, treat initiatives, projects, tasks, status, and delivery dates as
  tracker data. Link them; do not recreate them.
- Confirm important facts before writing. Live context is a starting point, not authority.
- Verify that the authenticated account represents the current human before making an external
  write.

## 2. Documents in `_inbox/`

Read every relevant file. Common inputs:

- Product brief or pitch deck
- Research repository or interview notes
- Support or feedback export
- Strategy or roadmap document
- Existing specs
- Competitor research
- Team or org list

Propose a file-by-file mapping. Preserve complete useful content where the workspace must remain
understandable without the source. Keep external links for provenance. Do not import secrets,
restricted transcripts, unnecessary private details, or bulk raw exports; link, anonymize, or
summarize them.

After the material is filed, propose what happens to the original — the narrowest durable location
you would move it to, or removal. Both are workspace writes, so both need the user's approval
before you act. Default to moving rather than removing.

## 3. Exports from another AI or tool

If another assistant already knows the product, give the user this prompt:

> Summarize everything you know about this product for a person joining the work: what it does
> today, primary users and jobs, core workflows, current product direction, known user painpoints,
> explicit feature requests, active discovery questions, strategy claims, main alternatives,
> people and ownership when relevant, and any issue tracker, analytics, or feedback sources that
> are actually used. Separate fact from inference. Say "unknown" where uncertain and "not used"
> for optional systems that do not exist.

For focused exports:

- Support or CRM: recent attributed feedback, not the entire customer record.
- Research tools: interview summaries plus verbatim quotes and source links.
- Analytics: metric definitions and links, not a copied event warehouse.
- Issue tracker: active themes and links, not a markdown duplicate of every issue.

## 4. Conversational fallback

Ask one short round:

1. Should this workspace cover one product, a product area, a platform, or a portfolio? What is it
   called, and who is it for?
2. What is your name for attribution, and who or what should steward this workspace: you, another
   person, a team, or a role?
3. Would profiles for anyone involved be useful, or should the optional `team/` area stay empty?
4. Where do feedback, analytics, and delivery work live today, if anywhere? Manual capture and
   `not used` are valid answers.
5. What is the current product direction, and which workflow should Product OS help with first:
   feedback, synthesis, discovery, strategy, or specs?

Write `unknown` for unresolved living facts and `not used` for absent optional systems. Never copy
runtime `[bracket placeholders]` into living files.

## After any source

- Update `SETUP.md`.
- Tell the user what was filled, what remains `unknown` or `not used`, and the next cheapest source
  or workflow.
- Run `/workspace-heal report`.
