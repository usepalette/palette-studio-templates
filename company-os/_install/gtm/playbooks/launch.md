---
type: playbook
owner: "[Owner]"
status: draft
last_updated: YYYY-MM-DD
last_updated_by: "[Owner]"
edit_policy: team
read_when:
  - You're launching a feature or product
  - You're planning launch comms or a release kit
---

# Launches playbook

How we ship product updates to the world — from small changelog entries to major launches.

**Before creating launch content:** read `../foundations/brand/voice.md` (and your brand/design assets) for tonal and visual consistency.

---

## Philosophy

- **Story first, format second.** Before picking a medium, nail *what you're saying* — the hook, the problem, the transformation. The messaging is the launch; everything else is formatting it for a channel.
- **Different, not better.** Position what's new as a new approach, not just an improvement on the old.
- **One thing.** If people remember only one thing about this launch, what should it be?
- **Every launch is earned attention.** Don't waste it on a weak hook or an unclear message.

---

## Launch tiers

Not every update gets the same treatment. Match effort to impact.

### Tier 1 — Changelog update
Small improvements, fixes, minor features. Things users notice but don't need to *learn* — a faster sync, a new shortcut, a fixed edge case.

### Tier 2 — Feature update
A new capability that changes how someone works — a new integration, a new view, a redesigned flow. Existing users go "oh, I can do that now?"; prospects get a reason to look again.

### Tier 3 — Product launch
A significant new capability or product area that changes *what you sell*, not just what the product can do. Timing is coordinated across channels — everything drops together. A new product line, a major workflow, or a shift in who you sell to.

### Picking the right tier

**Default to Tier 2.** Most things are Tier 2. Tier 3 is rarer than it feels in the moment — a well-told story about a feature is not evidence that it needs a full launch.

**The test:** does this change what you *sell*, or what the thing you sell can *do*? If customers would still describe you the same way after it ships — just with more reasons to like you — that's Tier 2.

Signals it's genuinely Tier 3:
- The ICP shifts or expands (new persona, new segment)
- Pricing or packaging changes because of it
- You'd rewrite the homepage hero, not just add a section
- The competitive set changes (you're compared to different products now)

If none of those apply, it's Tier 2 — ship it with confidence and save the full push for when it counts.

---

## Workflow

Two phases, with a hard checkpoint between them.

### Phase 1 — Research & messaging (do this for every launch)

The messaging brief **is** the launch. Don't write any content until it's locked.

1. **Understand what shipped.** Read the PRD / PR / feature description. What does it actually do? Don't write anything until you can explain it in one sentence.
2. **Check customer context.** Who's been asking for this? Scan your accounts (e.g. `../../accounts/*/requests.md`) for champions who care and the language they used — it shapes how you frame it.
3. **Check the landscape.** Look at `../foundations/market/competitors/` — do rivals have this, and how do they position it? This shapes your angle.
4. **Draft the messaging brief** with the user (use `../templates/launch/messaging-brief.md`), and agree it before moving on. Fill in:
   - **One-liner** — the launch in a sentence.
   - **Audience** — who it's for.
   - **Problem** — what was painful before.
   - **Transformation** — what's now possible.
   - **Hook** — the sharpest way to open.
   - **Why now** — the reason it matters today.
   - **Positioning angle** — the frame (different, not better).
5. **Iterate.** Review with the team. Push back on weak hooks; test the one-liner out loud. Every Phase 2 output depends on getting this right.

**Output:** an agreed messaging brief in the launch's folder (e.g. `../work/campaigns/<launch-name>/` or a `work/launches/<launch-name>/`).

### Phase 2 — Content (once messaging is locked)

Pick outputs by tier and by what fits this specific launch — not everything applies every time.

| Output | Tier 1 | Tier 2 | Tier 3 | Template |
|--------|:------:|:------:|:------:|----------|
| Docs update | ✓ | ✓ | ✓ | `../templates/launch/docs-update.md` |
| Changelog entry | ✓ | ✓ | ✓ | `../templates/launch/changelog.md` |
| Community post | ✓ | ✓ | ✓ | `../templates/launch/community-post.md` |
| Product-update email | ✓ | ✓ | ✓ | — |
| Customer blurb | optional | ✓ | ✓ | `../templates/launch/customer-blurb.md` |
| Blog post | — | ✓ | ✓ | `../templates/launch/blog-post.md` |
| Account matching | — | ✓ | ✓ | `../templates/launch/account-messaging.md` |
| Social posts | — | optional | ✓ | `../templates/launch/linkedin-post.md` |
| Landing page | — | — | ✓ | `../templates/launch/landing-page.md` |
| Video / demo script | — | — | ✓ | `../templates/launch/video-script.md` |

Each template carries its own "how to write this" guidance — the playbook says *what* to pick, the template shows *how* to make it (`../templates/launch/README.md`).

**Tier 1 floor:** website changelog + community post (users hear about it where they already are), plus a product-update email for anything worth emailing.

**Where content lives:**
- **Tier 1 (changelog):** a dated release folder (e.g. `../content/changelog/YYYY-MM-DD-<slug>/` if you keep a content space).
- **Tier 2 / 3:** the launch folder — the messaging brief and every produced asset live together.

---

## Preferences

<!-- Builds over time as you launch more things — capture what worked, what to avoid, per channel. -->
