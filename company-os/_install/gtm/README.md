---
type: index
owner: [Owner]
status: draft
last_updated: YYYY-MM-DD
last_updated_by: [Owner]
edit_policy: team
---

# gtm

Your go-to-market as a file system.

A workspace where commercial knowledge, active work, and team processes live as markdown — one readable structure for people and agents, so brand voice, market intel, and campaign history don't go stale in scattered docs and people's heads.

## How to think about this space

Three mental buckets:

- **What we know** — `foundations/`: brand voice, market intel, strategy. Stable, changes rarely.
- **What we're doing** — `work/`: campaigns, projects, research. Active, changes constantly.
- **Who we are** — `team/`: individual GTM focus and writing voice per person.

## You need to…

| You need to… | Go to |
|---|---|
| Write anything external | `foundations/brand/` first — voice, messaging, positioning |
| Understand who we're selling to | `foundations/market/` |
| Understand our GTM strategy | `foundations/strategy/` |
| Load the product story or sales narrative | `foundations/product-marketing/` |
| Load how we think about a domain (sales, content, launches) | `playbooks/` |
| Produce launch content (changelog, blog, docs, posts) | `templates/launch/` (with `playbooks/launch.md`) |
| Write or store a content piece | `content/` — blog, email, social, changelog |
| Run a campaign or project | `work/` — copy the `_template/` |
| Do market or competitive research | `work/research/` |
| Write as or for a teammate | `team/<name>/voice.md` |
| Check account status | `../accounts/status.md` |
| Work with a specific account | `../accounts/<name>/` |

## Folder map

```
gtm/
├── foundations/          # what we know — brand, market, strategy
│   ├── brand/            #   voice, messaging, positioning
│   ├── market/           #   ICP, competitors
│   ├── strategy/         #   GTM strategy, vision
│   └── product-marketing/ #  product overview, sales narrative
│
├── playbooks/            # how we think — sales, content, launches
│
├── templates/            # fill-in formats that pair with playbooks (launch/…)
│
├── content/              # the pieces — blog, email, social, changelog
│
├── work/                 # what we're doing — active, changes constantly
│   ├── campaigns/        #   time-bound efforts (copy _template/ to start)
│   ├── projects/         #   larger initiatives (copy _template/ to start)
│   └── research/         #   market analysis, discovery
│
└── team/                 # who we are — one folder per person
```

This is a starting shape — add folders as real work needs them (e.g. `traction/`, `content/`, `routines/`, `processes/`) rather than pre-creating empty ones.

## How this space thinks

This space has its own mindset — see [`AGENTS.md`](AGENTS.md) for the behavioral rules (brand voice, session modes) that layer on top of the company-wide [`../AGENTS.md`](../AGENTS.md).
