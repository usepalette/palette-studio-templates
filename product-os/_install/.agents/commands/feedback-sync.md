---
description: Rebuild the feedback dashboard data from markdown without changing the viewer code
---

# Feedback sync

Rebuild `user-feedback/index.html` from the markdown source files.

## 1. Collect entries

Read markdown files under:

- `user-feedback/feedback/`
- `user-feedback/user-interviews/`
- `user-feedback/feature-requests/`
- `user-feedback/painpoints/`

Skip README and template files.

## 2. Normalize each item

Create one dashboard item with:

```json
{
  "kind": "feedback | interview | feature-request | painpoint",
  "file": "feedback/YYYY-MM-DD_company_person_topic.md",
  "date": "YYYY-MM-DD",
  "title": "Short title",
  "people": ["Full name"],
  "companies": ["Company"],
  "tags": ["tag"],
  "summary": "Primary section text",
  "details": "Supporting context",
  "source_count": 1,
  "source_url": "https://example.com/original",
  "capture_mode": "verbatim | paraphrase | summary",
  "sentiment": "positive | neutral | negative | mixed",
  "priority_signal": "low | medium | high",
  "severity": "low | medium | high",
  "frequency": "occasional | recurring | blocking"
}
```

Only include optional fields when present.

`file` must be a relative path inside `feedback/`, `user-interviews/`, `feature-requests/`, or
`painpoints/`. `source_url` must be an HTTP(S) URL; omit `unavailable` and any malformed value from
dashboard data.

Mapping:

- **Feedback:** `kind=feedback`, person/company/tags/sentiment/source URL/capture mode from
  frontmatter, summary from `## Feedback`, details from `## Context`.
- **Interview:** same mapping with `kind=interview`.
- **Feature request:** person from `requested_by`, summary from `## Request`, details from
  `## Why they want it` plus `## Evidence`, source count from `source_files`.
- **Painpoint:** companies from `companies`, summary from `## Painpoint`, details from
  `## Evidence` plus `## Impact`, source count from `source_files`.

Use the first H1 as the title. If absent, derive a readable title from the filename. Derive a
missing date from the filename only when it begins with `YYYY-MM-DD`.

Sort items by date descending, then company and title ascending.

## 3. Build the JSON

```json
{
  "updated": "YYYY-MM-DD",
  "items": []
}
```

Pretty-print with two-space indentation and valid JSON escaping. Then make the serialized JSON
safe to embed in HTML without changing the parsed values:

- Replace every literal `<` with `\u003c`.
- Replace every literal `>` with `\u003e`.
- Replace every literal `&` with `\u0026`.
- Escape U+2028 and U+2029 when the serializer leaves them literal.

Valid JSON alone is not enough: user-provided text containing `</script>` must never be able to
close the data block.

## 4. Replace only the data block

In `user-feedback/index.html`, locate the single block:

```html
<!-- FEEDBACK_DATA_START -->
<script id="feedback-data" type="application/json">
...
</script>
<!-- FEEDBACK_DATA_END -->
```

Replace that full block with the new JSON. Do not rewrite the HTML, CSS, or JavaScript around it.

If either marker is missing or appears more than once, stop and report the problem.

After replacement, verify:

- The markers and `feedback-data` script each exist exactly once.
- The script's text parses as JSON.
- No literal `<`, `>`, or `&` occurs inside the serialized JSON text.
- Every `file` uses one of the allowed local source paths, and every `source_url` is HTTP(S).
- The executable viewer JavaScript still parses.

## 5. Confirm

Report the number of items by kind, the path `user-feedback/index.html`, and that the embedded data
passed the safety checks.
