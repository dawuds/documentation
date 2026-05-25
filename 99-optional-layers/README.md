# 99 — Optional layers

Guidance on **when to add** Charter / Guideline / Baseline / Manual layers. General Bank does not maintain these as first-class folders — see [`../00-foundations/tiering-model.md`](../00-foundations/tiering-model.md) for the M3 vs M4 reasoning.

← [Back to repo home](../README.md) · [Foundations](../00-foundations/) ↑

---

## Why this section exists

The reference document hierarchy has nine layers ([`../00-foundations/document-hierarchy.md`](../00-foundations/document-hierarchy.md)). Most banks should operate at Maturity 3 (Policy / Standard / Procedure + Plans + Registers). Adding the M4 layers (Charter / Guideline / Baseline / Manual) prematurely creates paperwork that nobody reads.

This section helps you answer: *"Do I need this layer yet?"* — and if yes, *"What does a good one look like?"*

---

## Contents

| Layer | When to add | Anti-pattern to avoid |
|---|---|---|
| [Charter / Mandate](when-to-add-charter.md) | Board-level visibility; explicit terms of reference required (post-IPO, post-merger, post-regulatory escalation) | Charter that duplicates the master policy |
| [Guidelines (advisory)](when-to-add-guidelines.md) | Multiple teams implementing the same standard inconsistently | Guideline → de facto standard drift |
| [Baselines (technical hardening)](when-to-add-baselines.md) | Configuration drift causing repeated audit findings; you have engineering capacity to maintain and assess | Baseline that nobody enforces |
| [Manuals (SOP aggregator)](when-to-add-manuals.md) | 15+ SOPs in a function; handover-heavy workforce | Manual that contains policy-grade statements |

---

## The General Bank position

| Layer | General Bank uses it? | Reason |
|---|---|---|
| Charter | No (held within POL-00 §4) | Master policy is itself board-approved |
| Guidelines | No (advisory content captured in SOP intros) | Avoids guideline-graveyard pattern |
| Baselines | Yes, **selectively** (server OS, container, cloud landing zone — but live in engineering repos, not here) | Engineering capacity exists to maintain |
| Manuals | Yes, **selectively** (Security Operations Manual once SOC SOPs exceed ~15) | Operational navigability |

A real bank's choices may differ — these are not mandatory M4 additions, just informed defaults.

---

## Cross-links

- ↑ [Foundations — tiering model](../00-foundations/tiering-model.md) — the M1→M4 maturity framework
- ↑ [Foundations — document hierarchy](../00-foundations/document-hierarchy.md) — the full nine-layer reference
- ← [Back to repo home](../README.md)
