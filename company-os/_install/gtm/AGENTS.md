---
type: doc
owner: "[Owner]"
status: active
last_updated: YYYY-MM-DD
last_updated_by: "[Owner]"
edit_policy: team
---

# gtm

Company-wide rules — behavior, conventions, how the OS fits together — live in the root [`../AGENTS.md`](../AGENTS.md). This file adds the GTM-specific rules that layer on top. Root always applies; when they seem to conflict, root wins on company-wide matters, this file wins on GTM-specific ones.

## How to navigate

| Task | Read first |
|------|-----------|
| Writing external content | `foundations/brand/` (voice, messaging, positioning) |
| Writing as or for a teammate | `team/<name>/voice.md` + `foundations/brand/voice.md` |
| Sales or outreach work | `foundations/market/` |
| Starting a campaign or project | `work/` + any existing playbook for that tactic |
| Market or competitive research | `foundations/market/` for what's already known, `work/research/` for prior work |
| Understanding a teammate's focus | `team/<name>/README.md` + the live connector |
| Checking account status | `../accounts/status.md` |
| Working with a specific account | `../accounts/<name>/` |
| Strategic decisions | `foundations/strategy/` |

## GTM behavior

On top of the company-wide behavior in `../AGENTS.md`:

- **Know the brand before you write.** Always load `foundations/brand/voice.md` (and `messaging.md`, if it exists) before writing anything external. Never write external copy from memory.
- **Use what exists.** Check `foundations/` and `work/research/` before starting from scratch — the intel may already be there.
- **Keep the status board current.** When an account's situation changes, update the corresponding row in `../accounts/status.md` too.
- **Be direct, tight, no filler.** No corporate speak, no "Great question!" Draft, then tighten further.

## Session modes

Most GTM sessions fall into one of four patterns. Know which one you're in before you start.

- **Strategy** — decision docs, positioning, competitive read. Read `foundations/strategy/` and relevant context first. Write to convince a skeptical teammate, not to fill a template.
- **Content** — copy, campaign assets, messaging. Always load `foundations/brand/voice.md` before writing. Draft tight, then tighten further.
- **Research** — market signals, competitor analysis, synthesis. Check `foundations/market/` and `work/research/` for what's already known before starting. Write findings back there.
- **Campaign** — time-bound pushes in `work/campaigns/`. Load any relevant playbook or process before starting.

When in doubt which mode you're in, ask. A short clarification beats wrong-direction work.

## Workspace hygiene

Company-wide hygiene rules — including the `lessons.md` / `log.md` convention — are in `../AGENTS.md`. GTM's forward-looking learnings live in `gtm/lessons.md`; what happened lives in `gtm/log.md`. Run `/reflect` to keep them tidy and promote recurring lessons into this file.
