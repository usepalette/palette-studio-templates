---
type: doc
sample: true
last_updated: 2026-06-11
last_updated_by: Sam Rivera
# Edit these outcomes to update the Goals section of overview.html.
# Each outcome: title, metric (how you'll know), baseline (today), target (where you want to be).
outcomes:
  - title: "Cut checkout drop-off"
    metric: "Checkout completion rate"
    baseline: "62%"
    target: "80%+"
  - title: "Self-serve support"
    metric: "Common issues resolved without a ticket"
    baseline: "0%"
    target: "40% deflected"
  - title: "Fast on mobile"
    metric: "Mobile page load (p75)"
    baseline: "4.1s"
    target: "under 2s"
---

# Goals

## Outcomes

What we're trying to achieve — change in the world, not features shipped.

> **Sample data** — replace with your project's real outcomes (`/onboard` does this).

- **Cut checkout drop-off** — the current portal loses too many customers at checkout; a faster, simpler flow should recover most of them.
- **Self-serve support** — let customers resolve common issues themselves, so the support team isn't answering the same questions all day.
- **Fast on mobile** — most traffic is mobile; speed is the single biggest lever on conversion.

## Non-goals

Things people might assume are in play that explicitly are **not** — so scope stays honest.

- Replacing the payment provider (it stays; we integrate with it).
- Rebuilding the internal admin tools — this project is the customer-facing portal only.

## Success metrics

| Metric | Baseline | Target | How we measure |
| ------ | -------- | ------ | -------------- |
| Checkout completion | 62% | 80%+ | Analytics funnel |
| Support deflection | 0% | 40% of common issues | Help-center + ticket tags |
| Mobile load (p75) | 4.1s | under 2s | Real-user monitoring |

---
_Last updated: 2026-06-11_
