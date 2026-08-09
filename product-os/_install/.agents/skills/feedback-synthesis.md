---
name: feedback-synthesis
description: Turn raw feedback and interviews into honest feature requests and recurring painpoints while preserving sources, attribution, quotes, counter-signal, and scoring discipline. Use for feedback capture, interview processing, synthesis, and product evidence review.
---

# Feedback synthesis

The goal is not to produce more files. It is to preserve raw signal, identify the small number of
patterns that matter, and keep the evidence visible.

## Lifecycle

```text
raw feedback ──┬──> explicit ask ──> feature request
               │
               └──> repeated or blocking problem ──> painpoint
user interview ┘
```

Every derived file carries `source_files` pointing to the original material.

## Graduation rules

| Signal | Action |
|---|---|
| One comment, no explicit ask | Keep as raw feedback |
| A specific capability is requested | Create or update a feature request |
| The same underlying pain appears in at least two independent sources | Create or update a painpoint |
| A structured interview reveals a clearly blocking problem | A painpoint may be justified with one source; label this honestly |
| Two sources use different words for the same job | Merge into the existing canonical item |
| Two sources mention the same surface but different jobs | Keep them separate |

When uncertain, keep the raw sources separate. It is easier to merge later than to split a false
pattern.

## Scoring painpoints

Use two axes:

```yaml
severity: low | medium | high
frequency: occasional | recurring | blocking
```

- **Severity** is the impact when the problem occurs.
- **Frequency** is how often the workflow is affected.

Do not score emotional volume. A quiet blocker can be more important than a loud annoyance.

## Scoring feature requests

```yaml
priority_signal: low | medium | high
```

This is evidence strength, not roadmap priority. Consider:

- Strength and urgency of the ask
- Number and relevance of independent sources
- Fit with active strategy

Record tensions. Do not inflate a score because a source is senior or loud.

## Synthesis process

1. Read every selected source in full.
2. List distinct pains and explicit asks.
3. Search existing painpoints and requests for the same underlying job.
4. Cluster only when the job and impact are genuinely the same.
5. Preserve verbatim language under `Their words`.
6. Separate facts, interpretation, and counter-signal.
7. Propose the create/update plan before writing.
8. Update company profiles and run `/feedback-sync`.

## Attribution

- A quote comes from `## Their words` or a source explicitly marked `capture_mode: verbatim`. If
  trimmed, use ellipses.
- A paraphrase is labelled as a paraphrase.
- Preserve `source_url` in the raw source so a future reviewer can trace the evidence.
- Context and impact may be analyst interpretation, but must not be written as the user's words.
- Unknown identity stays unknown. Never guess a company or person.

## Data boundaries

- Include only product context the workspace audience is allowed to see.
- Keep restricted raw material, secrets, and unnecessary personal details in their controlled
  source. Link, anonymize, or summarize when needed.
- Never weaken source permissions by copying material into a more widely shared file or recap.

## Tags

- Prefer existing tags.
- Use lowercase kebab-case.
- Describe the product area, workflow, or friction, not the company name.
- Keep the set small enough to remain useful.
