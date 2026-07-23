# Content

A home for the writing you ship — blog posts, LinkedIn posts, newsletters,
pitches, copy. Draft in markdown, refine against how your team thinks about
content, check it against your brand voice, plan where it goes, and keep a
running log of what you've published. Driven by a single skill.

## What you get

- **`/content` skill** — the one entry point. Modes for starting a draft,
  refining it, checking it against your voice, planning distribution, and
  logging what you ship. Invoke it explicitly (`/content new "..."`) or just
  ask ("help me write a post about X", "does this sound like us?").
- **`content/drafts/`** — pieces in progress as markdown, each with a target
  channel, the one takeaway, and the draft itself.
- **`content/content.md`** — a log of what you've shipped and what's in flight.
- **`content/voice.md`** — your brand voice, personalized at install: tone,
  principles, words to avoid, and a self-check the `voice-check` mode runs
  against any draft. The piece that makes the workflow sound like *you*.
- **`content/playbook.md`** — how your team thinks about content: philosophy,
  the before/while/after of writing, content types, and distribution.

## How install works

When you install this workflow, an agent will:

1. Confirm where the `content/` workspace should live (defaults to the
   project root; offers to move it if you have an obvious home for it).
2. Personalize `voice.md` — pulling your tone, audience, and brand language
   from the Palette MCP or project files where it can, and asking you for the
   rest in one short round.

The skill and the playbook are placed as-is. Palette Desktop creates a checkpoint
right before install so you can revert.

## After install

```bash
/content new "Why we rebuilt our onboarding"   # start a draft for a channel
/content refine why-we-rebuilt-onboarding       # tighten against the playbook
/content voice-check why-we-rebuilt-onboarding  # check it against your voice
/content distribute why-we-rebuilt-onboarding   # plan primary + amplification
/content log                                     # log a piece you shipped
/content list                                    # see everything
```

`voice.md` and `playbook.md` are yours to edit — the skill reads them every
time, so the more they reflect how you actually write, the better the output.
