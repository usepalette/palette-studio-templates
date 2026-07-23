# Presentations

Go from a rough idea to a polished deck without leaving your editor — a sales
pitch, a product review, a team update, or a conference talk. Draft in
markdown, generate a self-contained HTML slide deck, and keep a running log of
the presentations you've given.

## What you get

- **`/presentation` skill** — the one entry point. Modes for starting a
  draft, refining it, generating slides, logging a presentation, and listing
  your decks. Invoke it explicitly (`/presentation new "..."`) or just ask
  ("turn this draft into slides").
- **`presentations/drafts/`** — presentations as markdown: key message, timed
  outline, and per-slide notes. The thinking stage before any slides exist.
- **`presentations/slides/template.html`** — a single-file HTML deck
  template. No build step, no dependencies. Open it in a browser and you get:
  - keyboard navigation, click-to-advance, fullscreen
  - a dark/light theme toggle that syncs across windows
  - a **presenter view** (`N`) with current/next preview, speaker notes, and
    a timer
  - **PDF export** straight from the browser's print dialog
- **`presentations/snippets.md`** — your reusable slides (intro, company,
  team, CTA), personalized at install, dropped into any deck on demand.
- **`presentations.md`** — a log of presentations you've given.

## How install works

When you install this workflow, an agent will:

1. Confirm where the `presentations/` workspace should live (defaults to the
   project root; offers to move it if you have an obvious home for it).
2. Personalize `snippets.md` — pulling your name, role, company, and team
   from the Palette MCP or project files where it can, and asking you for the
   rest in one short round.

The skill and the HTML template are placed as-is — no customization needed.
Palette Desktop creates a checkpoint right before install so you can revert.

## After install

```bash
/presentation new "Q3 Pipeline Review"      # start a draft
/presentation draft q3-pipeline-review       # refine the outline
/presentation slides q3-pipeline-review      # generate the HTML deck
/presentation log                            # log a presentation you gave
/presentation list                           # see everything
```

Open the generated `presentations/slides/<slug>.html` in a browser, press
`F` for fullscreen and `N` for presenter view. To export a PDF, use the
browser's print dialog.
