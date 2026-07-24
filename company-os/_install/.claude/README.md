---
type: index
---

# Claude adapters

Thin Claude-specific files that point back at `../AGENTS.md` and the canonical `../.agents/` layer.

- `commands/` — one adapter per canonical command in `../.agents/commands/`, so Claude registers them as slash-commands.
- `skills/` — one adapter per canonical skill in `../.agents/skills/`.
- `settings.json` — wires the Palette live-context connector (MCP).

Keep these thin. The real content lives in `../.agents/`; other agents (Codex/Gemini/Mistral) read that directly.
