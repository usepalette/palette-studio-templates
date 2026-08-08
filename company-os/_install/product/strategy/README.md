---
type: index
owner: "[Owner]"
status: draft
last_updated: YYYY-MM-DD
last_updated_by: "[Owner]"
edit_policy: team
---

# Strategy

Product strategy theses — synthesized from team input, user signal, and competitive read. Lives one level above the roadmap.

## What goes here

Stable, evolving claims about *how we win* — not *what ships next*. Each file is a claim about positioning, moat, or sequencing, with evidence and open questions attached. A thesis should outlive a single roadmap window.

This is **not** where raw input lands. Raw input flows in from:

- `../user-feedback/painpoints/` — recurring patterns in user signal
- `../competitors/` — what competitors actually ship
- team roadmap input (wherever that lives for you)

When input recurs or sharpens, promote it into a thesis here.

## File conventions

**Filename:** kebab-case, describes the thesis, not the source (`provider-agnostic-os.md`, not `notes-from-standup.md`).

**Frontmatter:**

```
---
type: strategy
title: "[short thesis title]"
owner: "[Owner]"
status: "[draft | active | parked | archived]"
last_updated: YYYY-MM-DD
last_updated_by: "[Owner]"
edit_policy: team
contributors: [Name, ...]
related: [other strategy/ files this connects to]
---
```

**Body sections, in order:** Thesis (the claim, 1-2 sentences) → Why it matters → Evidence (dated, attributed) → Counter-arguments → Open questions → Implications for the roadmap → Sources.

## What does NOT go here

- Specific feature specs — draft those paste-ready and send straight to your tracker
- One-off user quotes — `../user-feedback/feedback/`
- Competitor profiles — `../competitors/`

If you can answer "what does this ship?" in one sentence, it's a feature, not a thesis.
