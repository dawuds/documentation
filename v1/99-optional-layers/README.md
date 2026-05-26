# 99 — Optional layers

Guidance on Charter / Guideline / Baseline / Manual layers. General Bank does not maintain these as first-class folders in this suite.

← [Repo home](../README.md) · [Foundations](../00-foundations/) ↑

---

## Contents

| Document | Add this layer when… |
|---|---|
| [when-to-add-charter.md](when-to-add-charter.md) | Board-level visibility requires explicit terms of reference (post-IPO, post-merger, post-regulatory escalation) |
| [when-to-add-guidelines.md](when-to-add-guidelines.md) | Multiple teams implementing the same standard inconsistently |
| [when-to-add-baselines.md](when-to-add-baselines.md) | Configuration drift is causing repeated audit findings; engineering capacity exists to maintain and assess |
| [when-to-add-manuals.md](when-to-add-manuals.md) | 15+ SOPs in a function with handover-heavy workforce |

## General Bank position

| Layer | Used? | Reason |
|---|---|---|
| Charter | No | ISMS establishment held within [POL-00 Section 4](../01-policies/00-information-security-policy.md) |
| Guidelines (standalone) | No | Advisory content captured in SOP intros |
| Baselines | Yes (selectively) | Server OS, container, cloud landing zone — live in engineering repos |
| Manuals | Yes (selectively) | Security Operations Manual once SOC SOPs exceed ~15 |

See [`../00-foundations/tiering-model.md`](../00-foundations/tiering-model.md) for the M3 vs M4 reasoning behind these defaults.

---

[`../00-foundations/`](../00-foundations/) ↑ · [Repo home](../README.md)
