---
type: index
owner: "[Owner]"
status: draft
last_updated: YYYY-MM-DD
last_updated_by: "[Owner]"
edit_policy: team
---

# Foundations

What we know — reference material that rarely changes. The stuff you load before doing GTM work, not the work itself.

## Structure

```
foundations/
├── brand/            # voice, messaging, positioning — load before writing anything external
├── market/           # ICP, competitors, market intel
├── strategy/         # GTM strategy, vision — how we win, sequencing
└── product-marketing/ # product overview + sales narrative
```

## What goes where

| You have… | Put it in… |
|---|---|
| Brand voice guidelines | `brand/voice.md` |
| Messaging pillars | `brand/messaging.md` |
| Positioning / category | `brand/positioning.md` |
| ICP definition | `market/icp.md` |
| A competitor profile | `market/competitors/` (template in its README) |
| GTM strategy / channels | `strategy/gtm-strategy.md` |
| Vision / north star | `strategy/vision.md` |
| Product overview / how it works | `product-marketing/product-overview.md` |
| The sales story / pitch narrative | `product-marketing/sales-narrative.md` |

**Rule of thumb:** if it's stable and you'd load it before starting a task, it belongs here. If it's active work with a start and end, it belongs in `../work/`.
