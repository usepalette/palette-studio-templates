---
name: prefill-context
description: How to prefill the GTM OS from existing sources — a live connector, docs dropped in _inbox/, or context exported from another AI (Claude, ChatGPT, Gemini) or tool (Notion, Slack, Granola, a CRM). Use during /onboard or whenever setting up / backfilling the OS.
---

# Prefill context

The fastest way to fill this OS is not to type it — it's to pull from where the company's GTM context already lives. Work the sources in this order (most leverage first); stop when you have enough, and always **propose → confirm → write**. Never fabricate; leave a placeholder where you genuinely don't know.

The target is the GTM reference layer: company + product, market/ICP, brand voice, strategy, team, and current customers.

## 1. Live connector (best)

If a live-context connector is available (e.g. Palette, or any MCP that exposes company/people/work context), use it first:

- Ask the connector for the broadest company overview, then product, market, brand, and the team.
- Map what it returns into the template: company + product → `foundations/product-marketing/` + root `README.md`/`AGENTS.md`; market/ICP → `foundations/market/`; brand voice → `foundations/brand/`; strategy → `foundations/strategy/`; people → `team/<name>/` (via `/new-person`); customers → `accounts/` (via `/new-account`); active work → `work/`.
- Confirm the important bits with the user rather than writing silently — the connector is a starting point, not gospel.

## 2. Dropped documents (`_inbox/`)

If the user has dropped files in `_inbox/` (or points you at any folder/files):

- Read everything. Common inputs: pitch deck, one-pager, an existing brand/voice guide, positioning doc, Notion/Docs exports, team list, CRM/pipeline export, meeting notes.
- Extract: company one-liner, stage, ICP/market, brand voice cues, product overview, GTM motion, team names+roles, current customers.
- File each fact into the right folder using the scaffolding commands (`/new-person`, `/new-account`) where they apply, not by hand.
- When done, tell the user what you filed, then **propose** what to do with `_inbox/`: list each original and the exact destination you'd move it to. Default to moving, never deleting. Only delete a source after the user explicitly confirms that specific file — "clear the inbox" is not consent to delete.

## 3. Export from another AI (copy-paste prompts)

If they already use another assistant that knows their company, have them paste its answer to one of these. Give them the exact prompt to run *over there*, then parse what they paste back.

**Claude / ChatGPT / Gemini — general company dump:**
> "Summarize everything you know about my company for a new GTM teammate: what we do (one line), our stage and size, who our customers/ICP are, our main competitors, how we sell, our brand voice, and who's on the team with their roles. Be specific; use bullet points; say 'unknown' where you're not sure."

**Brand voice specifically:**
> "Describe our writing voice: tone in 3 words, words/phrases we use, words we avoid, and who we write for. Give one on-voice and one off-voice example." → `foundations/brand/voice.md`.

**Team:**
> "List everyone on the GTM team: name, role, and one line on what they own." → one `/new-person` each.

## 4. Tool exports (when a connector isn't wired but the tool is used)

- **Notion / Confluence / Google Docs** — ask for an export or a pasted page of the brand/positioning/strategy docs; extract into the matching `foundations/` file.
- **Slack** — a pasted channel description, team roster, or pinned onboarding doc gives team + norms.
- **Granola / meeting tools** — pasted recent meeting summaries seed `accounts/` and `work/research/`.
- **CRM (HubSpot, Attio, Salesforce, a spreadsheet)** — an accounts/pipeline export seeds `accounts/` (one `/new-account` per real, engaged customer — not every row).

## 5. Conversational fallback

No connector, no docs, nothing to paste? Ask the `/onboard` questions directly and build from the answers. Keep it light — a thin-but-real OS beats a perfect-but-empty one.

---

**After any source:** update `SETUP.md` (tick the boxes you completed), tell the user what got filled vs. what's still `[placeholder]`, and point them at the next cheapest source for the gaps.
