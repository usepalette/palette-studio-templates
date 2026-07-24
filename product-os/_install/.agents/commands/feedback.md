---
description: Capture raw product feedback and any explicit feature requests without over-synthesizing
argument-hint: "<raw feedback or interview notes>"
---

# Feedback

Capture a new product signal faithfully, link it to its company, and refresh the dashboard.

Load the `feedback-synthesis` skill before interpreting the source.

## 1. Read the source

Use the text in the request, a named file, or a connector result the user explicitly asked to use.
Extract:

- Date
- Source: chat, interview, email, support, call, or other
- Source URL or durable reference, when available
- Capture mode: verbatim, paraphrase, or summary
- Person and company
- Short topic
- Tags
- Sentiment
- Explicit feature requests
- Candidate pains, without assuming they are recurring

If the source date is missing, use today's absolute date and state that it is the capture date.
If an identity is genuinely unknown, use `Unknown` and state why. Do not guess. If no durable
source link exists, use `source_url: unavailable`.

Keep only the product context the workspace audience is allowed to see. Do not copy credentials,
private personal details, restricted transcript text, or an entire raw export. Link to the
access-controlled source, anonymize, or summarize when needed.

## 2. Show the capture plan

Show the proposed metadata, destination, explicit requests, and any assumptions. Ask for
confirmation when identity, attribution, or the source wording is uncertain.

## 3. Save the raw source

- Interviews go to `user-feedback/user-interviews/`.
- Other sources go to `user-feedback/feedback/`.
- Filename: `YYYY-MM-DD_company_person_topic.md`.
- Slug each filename field in lowercase kebab-case; underscores only separate the fields.
- Use the source folder's canonical shape.
- Preserve `source_url` and `capture_mode`.
- Put exact quotations under `## Their words`. A summary or paraphrase never becomes a quote.

## 4. Handle explicit requests

For each explicit ask:

1. Search `user-feedback/feature-requests/` for the same underlying job.
2. If it exists, add the new source to `source_files` and update evidence.
3. Otherwise create `YYYY-MM-DD_company_topic.md` from
   `user-feedback/feature-requests/_template.md`.

Do **not** create a recurring painpoint from one casual comment. Instead, say which candidate pains
could be checked with `/synthesize-feedback`.

## 5. Update the company profile

Create or update `user-feedback/_companies/company-name.md`, using a lowercase kebab-case company
slug:

- Link the raw source.
- Link any feature request created or updated.
- Add only the product context needed to interpret the feedback.
- Set `owner` to the responsible person, team, or role and `last_updated_by` to the current human.

## 6. Refresh and confirm

Run `/feedback-sync`.

Report:

- Raw source file
- Requests created or updated
- Company profile created or updated
- Candidate pains left for synthesis
- Metadata that remained unknown or uncertain
