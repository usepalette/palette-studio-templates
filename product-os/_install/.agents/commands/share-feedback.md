---
description: Draft a sourced feedback recap and optionally send it after explicit approval
argument-hint: "<company, topic, or tag>"
---

# Share feedback

Create a concise, evidence-backed recap from existing Product OS files.

This command does not ingest new feedback. Use `/feedback` first when the source is not yet saved.

## 1. Gather sources

Use the requested company, topic, or tag. Search raw feedback, interviews, feature requests,
painpoints, and company profiles.

Show a numbered list grouped by kind, newest first. Ask which entries to include.

## 2. Read selected files

Read every selected file in full. Quote only text under `## Their words`, or a raw source whose
`capture_mode` is explicitly `verbatim`. Never turn a summary or paraphrase into a quotation. Keep
analyst interpretation separate.

Confirm that the intended audience may see the selected names, quotes, and source details.
Anonymize or omit restricted material before drafting for a broader audience.

## 3. Draft

Use only sections supported by the selection:

```text
[Company or topic] - product feedback recap ([date range])

What users are trying to do
- [Job or context]

What gets in the way
- [Pain with severity/frequency when available]

What they asked for
- [Explicit request with priority signal when available]

Their words
> "[Verbatim quote]"
> - [Person, company]

Sources: [N feedback, M interviews, P painpoints, R requests]
```

Keep it scannable. Do not add a theme that is absent from the selected sources.

## 4. Choose the destination

Show the draft and ask what to do:

- Keep it in chat
- Save it to `user-feedback/recaps/YYYY-MM-DD-company-or-topic.md`
- Send it through an available messaging connector

Before any external send, show the exact content and destination and require an explicit yes.
Discover available connector tools instead of hardcoding a provider or tool name.

If the user chooses to save it, create the exact path shown above with:

```yaml
---
type: doc
date: YYYY-MM-DD
topic: [Company or topic]
source_files: [Every selected Product OS source]
last_updated_by: [Current human]
---
```

The recap is a communication artifact, not a new feedback source.

## 5. Confirm

Report what was included and whether anything was written or sent. If the user declined, say that
nothing external changed.
