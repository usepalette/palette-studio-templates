# Accounts

Working memory for the companies you're actively engaged with — the stuff
that doesn't fit in a CRM field. What you actually think about an account,
your strategy, meeting takeaways, what they care about, internal dynamics.
Plain markdown, version-controlled, and driven by a single skill.

## What you get

- **`/account` skill** — the one entry point. Modes for creating an account,
  logging a meeting, prepping for a call, updating a health read, and listing
  what's live. Invoke it explicitly (`/account new "Acme"`) or just ask
  ("log my call with Acme", "prep me for the Globex check-in").
- **`accounts/<company>/`** — one folder per account. Starts with two files
  (a `README.md` brief and a `health.md` read) from `_template/`, and grows
  `meetings/` and `shareables/` as the relationship does.
- **`accounts/accounts.md`** — the roster. One row per account: stage, owner,
  last touch, next step. The file you skim to see where everything stands.
- **`accounts/approach.md`** — your sales approach, personalized at install:
  discovery questions, qualification signals, what you do and don't do. The
  `prep` mode reads it so briefs sound like *you*, not a generic playbook.

## How install works

When you install this workflow, an agent will:

1. Confirm where the `accounts/` workspace should live (defaults to the
   project root; offers to move it if you have an obvious home for it).
2. Personalize `approach.md` — pulling your company, product, and ICP from
   the Palette MCP or project files where it can, and asking you for the rest
   in one short round.

The skill and the folder templates are placed as-is. Palette Desktop creates a
checkpoint right before install so you can revert.

## After install

```bash
/account new "Acme Corp"            # scaffold the account folder
/account meeting acme-corp          # log a meeting, extract follow-ups
/account prep acme-corp             # pre-call brief from the account + your approach
/account health acme-corp           # refresh the health read
/account list                       # roster, grouped by stage
```

Each account's `README.md` is the one file you read to understand it — keep
it scannable; detail belongs in the meeting files.
