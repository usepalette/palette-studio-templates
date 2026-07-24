---
type: index
owner: [Owner]
status: draft
last_updated: YYYY-MM-DD
last_updated_by: [Owner]
edit_policy: team
---

# Discovery

Open questions worth exploring — not yet specs, not yet strategy theses. The space between "interesting signal" and "load-bearing claim."

## What goes here

Areas named as worth investigating but not yet answered. Each file is a *question* with framing, constraints, and a learning plan — not an answer.

Discovery sits upstream of strategy and specs:

- A discovery area starts as an open question.
- If learning produces a durable claim about how we win, promote it to `../strategy/`.
- If learning produces a buildable surface, draft a spec.
- If learning closes the question without action, archive it with the reasoning.

## When to create one

- A teammate raises a "worth discovering further" question that doesn't fit an existing surface
- A recurring user pain points at a missing product *mechanic*, not just a missing feature
- A competitive read surfaces a category question with no current position

**Don't create one for:** feature requests with clear scope (spec it directly), one-off input (log it where it belongs), or already-validated claims (`../strategy/`).

## File conventions

**Filename:** kebab-case, frames the question domain, not the answer.

**Frontmatter:**

```
---
title: [short question domain]
status: [open | in-flight | promoted | closed]
opened: YYYY-MM-DD
contributors: [Name, ...]
constraints: [explicit limits on the solution space]
---
```

**Body sections, in order:** The question → Why we care → Constraints → What we know already → Hypotheses (falsifiable) → How we'd learn → Source.
