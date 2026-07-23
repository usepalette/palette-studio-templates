# Claude adapter

**Before doing anything else, read the *entire* `AGENTS.md` in this folder and follow every rule in it — start to finish.** Begin with its "First-run detection" and "Start here — before any task" sections and actually do those steps.

`AGENTS.md` is the source of truth for this workspace. If this file ever conflicts with it, `AGENTS.md` wins. When you work inside a folder (`context/`, `decisions/`, `meetings/`, …), also read that folder's `README.md`.

Note: `overview.html` is generated from the markdown — never hand-edit it beyond regenerating its `data-snapshot` (see `AGENTS.md` → "The dashboard").

Claude compatibility adapters live in `.claude/commands/` and `.claude/skills/`; canonical content lives in `.agents/`. Don't duplicate shared instructions here.
