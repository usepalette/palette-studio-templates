---
type: doc
---

# product

Company-wide rules — behavior, conventions, how the OS fits together — live in the root [`../AGENTS.md`](../AGENTS.md). This file adds the product-specific rules that layer on top. Root always applies; when they seem to conflict, root wins on company-wide matters, this file wins on product-specific ones.

Work here as a **thinking partner**, not a form-filler. The owner of this space knows their domain — be tight, actionable, no filler.

## How to navigate

| Task | Read first |
|------|------------|
| Capturing a user feedback snippet | `user-feedback/README.md` → matching subfolder README |
| Drafting a product spec | this file's "Specs paste-ready" rule below |
| Synthesizing painpoints from feedback or an interview | `user-feedback/painpoints/README.md` |
| Adding or refreshing a competitor profile | `competitors/<product>/README.md` |
| Capturing or evolving a strategy thesis | `strategy/README.md` |
| Opening a discovery area to explore further | `discovery/README.md` |

## Product behavior

On top of the company-wide behavior in `../AGENTS.md`:

- **Specs paste-ready.** Default format: Problem, Audience, Success Criteria, Open Questions. Should drop straight into your tracker (Linear, Notion, etc.) with no reformatting.
- **Don't synthesize too early.** N=1 is rarely a painpoint. A single piece of feedback goes in `user-feedback/feedback/`, not `painpoints/`, until a pattern repeats across sources.
- **Use what exists.** Check existing feedback, competitor profiles, and strategy docs before duplicating. A new piece of feedback may belong under an existing painpoint rather than as a new file.

## How you work

Most sessions fall into one of three modes. Know which one you're in.

- **Capture** — raw input → structured markdown. Place the file per the relevant subfolder README.
- **Synthesis** — across multiple sources, surface a pattern. Write to `user-feedback/painpoints/` or `user-feedback/feature-requests/`, linking back to the original source. Don't synthesize too early.
- **Strategy** — roadmap framing, prioritization, competitive read. Load `strategy/` and relevant `competitors/` profiles first.

When in doubt which mode you're in: ask. A short clarification beats wrong-direction work.

## Workspace hygiene

Company-wide hygiene rules — including the `lessons.md` / `log.md` convention — are in `../AGENTS.md`. Product's forward-looking learnings live in `lessons.md`; what happened lives in `log.md`. Run `/reflect` to keep them tidy and promote recurring lessons into this file.
