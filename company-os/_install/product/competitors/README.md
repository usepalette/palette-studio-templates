---
type: index
owner: [Owner]
status: draft
last_updated: YYYY-MM-DD
last_updated_by: [Owner]
edit_policy: team
read_when: [You're prioritizing the roadmap, scoping a spec against an alternative, or briefing the team on a competitor's latest release]
---

# Competitors

Structured profiles of what competitors actually *ship* — features, gaps, roadmap signals. The product-side companion to `../../gtm/foundations/market/competitors/` (which covers positioning and GTM); this folder covers capability.

## How this works

- **One file per competitor** — `<competitor-name>.md`, using the template below.
- **Capability-focused, not narrative** — this is about what they built, what it does, and how it stacks up against what we ship. Positioning and messaging live in `../../gtm/foundations/market/competitors/`; link to that file rather than repeating it.
- **Synthesized, not raw** — distill what we know into a consistent shape. Raw research (changelogs, demos, docs) is linked under "Sources".
- **The template lives here, in this README.** Read it before writing a profile, so every profile has the same shape. Extend the template here and future profiles inherit it.
- **Be honest.** "Where they're ahead" must be real — we sharpen the roadmap by naming real gaps, not ignoring them.
- **Keep it current.** Update when they ship a release, announce an integration, or a capability gap closes.

## Profile template

```markdown
---
type: competitor
status: active
last_updated: YYYY-MM-DD
---

# [Competitor name]
> [Their one-liner / how they describe their product]

## Profile
| | |
|---|---|
| Website | [url] |
| Segment | [who they serve] |
| Stage / funding | [if known] |

## What they ship
[Their product surface in plain terms — core features, editions/tiers, platforms.]

## Capabilities vs ours
| Capability | Them | Us |
|---|---|---|
| [capability] | [what they have] | [what we have] |
| [capability] | [what they have] | [what we have] |

## Where they're ahead
[Specific capabilities or integrations they've shipped that we haven't. Be honest.]

## Where we're ahead
[Specific capabilities we've shipped that they haven't. Read `../strategy/` as the lens.]

## Gaps/roadmap signals
[Capabilities they're missing, hiring for, or have publicly signaled (job posts, changelogs, waitlists) as coming.]

## Sources
[Links to their changelog, docs, demo notes, deep research.]
```

## Tracked competitors

| Competitor | Segment | Threat |
|---|---|---|
| _[Add the first one — copy the template into `<name>.md`]_ | | |

**Threat:** 🔴 High (direct overlap, same buyer) · 🟡 Medium (adjacent, could evolve) · ⚪ Low (different segment).
