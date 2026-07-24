---
name: prefill-context
description: How to prefill the company OS from existing sources — a live connector, docs dropped in _inbox/, or context exported from another AI (Claude, ChatGPT, Gemini) or tool (Notion, Slack, Granola, a CRM). Use during /onboard or whenever setting up / backfilling the OS.
---

# Prefill context

The fastest way to fill this OS is not to type it — it's to pull from where the company's context already lives. Work the sources in this order (most leverage first); stop when you have enough, and always **propose → confirm → write**. Never fabricate; leave a placeholder where you genuinely don't know.

## 1. Live connector (best)

If a live-context connector is available (e.g. Palette, or any MCP that exposes org/people/work context), use it first:

- Ask the connector for the broadest company overview, then teams, then people, then current work.
- Map what it returns into the template: company → root `README.md`/`AGENTS.md`; teams → spaces; people → `people/<name>/` (via `/new-person`); active work → the relevant space.
- Confirm the important bits with the user rather than writing silently — the connector is a starting point, not gospel.

## 2. Dropped documents (`_inbox/`)

If the user has dropped files in `_inbox/` (or points you at any folder/files):

- Read everything. Common inputs: pitch deck, one-pager, an existing `CLAUDE.md`/`AGENTS.md`, Notion/Confluence/Docs exports, org chart, team list, CRM/pipeline export, meeting notes, transcripts.
- Extract: company one-liner, stage, ICP/market, brand voice cues, product overview, team names+roles, current customers, active projects.
- File each fact into the right space using the scaffolding commands (`/new-person`, `/new-account`, `/create-space`), not by hand.
- When done, tell the user what you filed and **clear `_inbox/`** (move originals into the space they informed, or delete if fully absorbed).

## 3. Export from another AI (copy-paste prompts)

If they already use another assistant that knows their company, have them paste its answer to one of these. Give them the exact prompt to run *over there*, then parse what they paste back.

**Claude (Projects / past chats) / ChatGPT / Gemini — general company dump:**
> "Summarize everything you know about my company for a new teammate: what we do (one line), our stage and size, who our customers/ICP are, our main competitors, how we sell, our brand voice, and who's on the team with their roles. Be specific; use bullet points; say 'unknown' where you're not sure."

**Existing `CLAUDE.md` / custom instructions / system prompt:**
> "Paste your current Claude/ChatGPT custom instructions or project instructions here." — these often already contain company + voice context; map them straight into `AGENTS.md`, `gtm/foundations/brand/voice.md`, and `README.md`.

**Brand voice specifically:**
> "Describe our writing voice: tone in 3 words, words/phrases we use, words we avoid, and who we write for. Give one on-voice and one off-voice example." → `gtm/foundations/brand/voice.md`.

**Team:**
> "List everyone on the team: name, role, and one line on what they own." → one `/new-person` each.

## 4. Tool exports (when a connector isn't wired but the tool is used)

- **Notion / Confluence / Google Docs** — ask for an export or a pasted page of the company wiki / handbook; extract into the matching space.
- **Slack** — a pasted #general channel description, team roster, or pinned onboarding doc gives team + norms.
- **Granola / meeting tools** — pasted recent meeting summaries seed `accounts/` and `product/user-feedback/`.
- **CRM (HubSpot, Attio, Salesforce, a spreadsheet)** — an accounts/pipeline export seeds `accounts/` (one `/new-account` per real, engaged customer — not every row).

## 5. Conversational fallback

No connector, no docs, nothing to paste? Ask the `/onboard` questions directly and build from the answers. Keep it light — a thin-but-real OS beats a perfect-but-empty one.

---

**After any source:** update `SETUP.md` (tick the boxes you completed), tell the user what got filled vs. what's still `[placeholder]`, and point them at the next cheapest source for the gaps.
