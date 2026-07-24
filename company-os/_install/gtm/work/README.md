---
type: index
owner: [Owner]
status: draft
last_updated: YYYY-MM-DD
last_updated_by: [Owner]
edit_policy: team
---

# Work

What we're doing — active GTM work, changes constantly. Where `foundations/` is stable reference, `work/` is the stuff with a start and an end.

## Structure

```
work/
├── campaigns/   # time-bound efforts — launches, pushes, promotions
├── projects/    # larger initiatives that span multiple campaigns or workstreams
└── research/    # market analysis, discovery, one-off investigations
```

`campaigns/` and `projects/` each ship with a `_template/` — copy it to start a new one (it stamps the brief). `research/` fills as you go. Don't pre-create empty folders.

## What goes where

| You have… | Put it in… |
|---|---|
| A campaign you're running | `campaigns/<campaign-name>/` — copy `campaigns/_template/` |
| A larger initiative like "launch [product]" | `projects/<project-name>/` — copy `projects/_template/` |
| Market research or competitive analysis you did | `research/` |

When a piece of research or a decision hardens into something stable teams should keep checking, promote it into `../foundations/` and link back to the original.
