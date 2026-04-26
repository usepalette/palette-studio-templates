# gtm-os

Your GTM as a file system.

---

## Getting started

1. Open this folder in [Claude Code](https://claude.ai/code)
2. Run `/onboard` — Claude asks about your company, product, and team, then sets everything up

---

## Structure

```
gtm-os/
├── foundations/           # What you know — reference that rarely changes
│   ├── brand/            #   voice, messaging, positioning
│   ├── market/           #   ICP, competitive intel
│   ├── strategy/         #   GTM strategy
│   └── product-marketing/#   product narrative, sales story
│
├── work/                 # What you're doing — changes constantly
│   ├── campaigns/        #   time-bound efforts (launches, pushes)
│   ├── projects/         #   larger initiatives
│   ├── research/         #   market analysis, discovery
│   └── content/          #   blog posts, pitches, copy
│
├── accounts/             # Customer accounts — context, strategy, materials
├── playbooks/            # How you think — philosophy + approach per domain
├── team/                 # Who you are — individual context per person
├── log/                  # What happened — decisions, learnings, session recaps
│
├── CLAUDE.md             # AI instructions — how Claude works here
└── .claude/commands/     # Slash commands (/onboard, /review)
```

Every folder has a README with what belongs there and how to use it.

---

## Folders

| Folder | What's in it | README |
|--------|-------------|--------|
| `foundations/` | Brand, market, strategy, product marketing — the reference layer | [README](foundations/README.md) |
| `foundations/brand/` | Voice, messaging, positioning | [README](foundations/brand/README.md) |
| `foundations/market/` | ICP, competitive intel | [README](foundations/market/README.md) |
| `foundations/strategy/` | GTM strategy and phases | [README](foundations/strategy/README.md) |
| `foundations/product-marketing/` | Product narrative, sales story | [README](foundations/product-marketing/README.md) |
| `work/` | Active work — campaigns, projects, research, content | [README](work/README.md) |
| `accounts/` | One folder per customer with context and materials | [README](accounts/README.md) |
| `playbooks/` | How the team thinks about each domain | [README](playbooks/README.md) |
| `team/` | One folder per person — profile and voice | [README](team/README.md) |
| `log/` | Institutional memory — decisions, learnings, session recaps | [README](log/README.md) |
| `.claude/commands/` | Slash commands Claude can execute | [README](.claude/commands/README.md) |

---

## Palette

Works great standalone. Works even better with [Palette](https://palette.team) — the shared context layer that keeps your AI teammates informed about your company, team, and how you work. The `/onboard` command will help you set it up.
