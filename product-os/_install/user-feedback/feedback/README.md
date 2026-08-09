---
type: index
owner: "[Workspace steward]"
status: active
last_updated: YYYY-MM-DD
last_updated_by: "[Setup author]"
edit_policy: team
---

# Feedback

Short product signals captured close to the source: chat messages, email replies, support notes,
call comments, and observed reactions.

Use `/feedback` or copy `../_template.md`.

## Rules

- Preserve the person's meaning. Use verbatim language when available.
- Record `source_url` whenever a permalink, ticket, recording, or email reference exists. Use
  `unavailable` rather than inventing one.
- Set `capture_mode` to `verbatim`, `paraphrase`, or `summary`.
- Put exact quotations under `## Their words`. Omit that section when the source wording is not
  available.
- A single complaint stays here unless it is an explicit feature request or a genuinely blocking
  problem from a structured interview.
- If the person asks for a specific capability, create or update a linked file in
  `../feature-requests/`.
- Do not create a recurring painpoint from one casual comment.
- Run `/feedback-sync` after adding or changing an entry.
