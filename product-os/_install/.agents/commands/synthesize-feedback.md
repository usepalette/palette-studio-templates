---
description: Compare feedback sources and create or update evidence-backed painpoints and requests
argument-hint: "[topic, company, tag, or file paths]"
---

# Synthesize feedback

Turn multiple raw sources into the smallest useful set of canonical painpoints and feature
requests.

Load the `feedback-synthesis` skill.

## 1. Select sources

Use the provided topic, company, tag, or file paths. If none is provided:

- List recent raw feedback and interviews.
- Ask which slice the user wants to synthesize.

Read every selected source in full. Search existing painpoints and feature requests before
proposing anything new.

## 2. Build an evidence table

For each distinct underlying job or problem, show:

| Candidate | Sources | Companies | Explicit ask? | Graduation |
|---|---:|---:|---|---|
| [Short problem] | [Count] | [Count] | yes/no | raw only / request / painpoint |

Apply the skill's graduation rules. State when a one-source blocking interview is the only evidence.

## 3. Propose create, update, or merge

For every candidate:

- Name the existing canonical file, if any.
- Recommend create, update, merge, or leave raw.
- Propose severity, frequency, or priority signal with one-sentence reasoning.
- Include counter-signal or scope boundaries.

Wait for confirmation before writing. Synthesis involves judgment.

## 4. Write confirmed changes

- Create or update painpoints and requests from their folder `_template.md` files.
- Keep `source_files` complete and relative.
- Preserve verbatim quotes.
- Update every affected company profile.
- Add links to discovery, strategy, specs, or the issue tracker only when they exist.

## 5. Refresh and confirm

Run `/feedback-sync`.

Report what was created, updated, merged, and deliberately left raw.
