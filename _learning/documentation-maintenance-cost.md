# Documentation maintenance cost — realistic FTE estimate

How much effort does this 150-document suite cost to keep current and operating once adopted? Honest answer for the adopting bank's resourcing conversation.

← [_learning home](README.md) · [Repo home](../README.md)

> **Source.** Captures the CIO-perspective finding from the v2 multi-agent review: "144 docs × annual review + cycles + audits. Rough estimate: 1.5–2 FTE-years/year just to keep this current, assuming nothing material changes. Add cyber drill + BNM exam + ISO surveillance + internal audit — another 1 FTE-year. Total ~3 FTE on documentation alone. Either accept that cost or cut the scope." This document expands the workings so a CIO can defend (or rebut) the estimate to their CRO and Board.

---

## 1. Scope of the estimate

In scope: the v2 suite as drafted —

- 9 frameworks
- 26 policies
- 27 standards
- 27 procedures (SOPs)
- 9 plans
- 32 registers + 4 new registers (REG-CHG, REG-MR, REG-OBJ, REG-GAP, REG-AUD, REG-AWR)
- 1 master document register + change log + approval register
- 1 Board Reporting and Escalation Annex
- 2 policy annexes (POL-04-A ISMS Scope, POL-04-B InfoSec Policy Statement)

Total documents (post-multi-agent-review): **~150**.

Out of scope of this estimate: the underlying control operation (e.g., actually running the SOC, doing the patching, holding the CAB meetings) — those are operational costs, not documentation costs. This estimate is purely the **document lifecycle and assurance-cycle cost**.

## 2. Cost components

### 2.1 Routine document maintenance (annual review cycle)

Most documents carry an annual review obligation. Workings:

| Activity | Per-doc effort | Docs | Per-year hours |
|---|---|---|---|
| Annual review of standards / SOPs / plans | 2–4 hours (light) | 70 | 210 |
| Annual review of policies | 4–8 hours (drafting + RMC pack) | 28 | 168 |
| Annual review of frameworks | 16–24 hours (substantive; cross-framework reconciliation) | 9 | 180 |
| Quarterly register operation (entry creation, reconciliation, ageing) | 8–16 hours / register / quarter | 36 | 1,728 |
| Master register + change log + approval register upkeep | continuous, ~1.5 hours / week | 1 | 78 |
| **Subtotal** | | | **~2,360 hours = ~1.4 FTE-years** |

(Assumes 1 FTE-year = 1,700 productive hours after leave, training, etc.)

### 2.2 Audit and assurance cycle work

| Activity | Per-cycle effort | Cycles / year | Hours |
|---|---|---|---|
| Annual cyber drill prep + execution + lessons | 200–400 hours across teams | 1 | 300 |
| ISO 27001 annual surveillance audit support | 200–300 hours | 1 | 250 |
| ISO 22301 / 42001 audit support (where applicable) | 100–150 hours | 1 | 125 |
| BNM examination support (when applicable) | 400–800 hours | ~1/3 years | 200 |
| NACSA examination support (when applicable) | 200–400 hours | ~1/2 years | 150 |
| Internal Audit engagements per PLN-08 | 80–160 hours per engagement | 12 engagements | 1,440 |
| Quarterly RMC pack + Annual Board pack | 80 hours / quarter + 200 hours / year | 4 + 1 | 520 |
| Management Review (annual + quarterly focused) | 60 hours + 4×30 | 1 + 4 | 180 |
| **Subtotal** | | | **~3,165 hours = ~1.9 FTE-years** |

### 2.3 Event-driven work

| Activity | Hours / event | Events / year | Hours |
|---|---|---|---|
| Material RMiT amendment / new BNM PD | 80–200 | 1–2 | 200 |
| NACSA directive | 40–120 | 2–4 | 240 |
| Material PIR with document updates | 20–60 | 3–6 | 240 |
| Material outsourcing entry / exit | 40–80 | 2–4 | 240 |
| New AI use case onboarding documentation | 20–40 | 6–12 | 240 |
| Other event-driven document revisions | — | — | 200 |
| **Subtotal** | | | **~1,360 hours = ~0.8 FTE-years** |

### 2.4 Total

| Component | FTE-years |
|---|---|
| Routine maintenance (Section 2.1) | ~1.4 |
| Audit + assurance cycles (Section 2.2) | ~1.9 |
| Event-driven (Section 2.3) | ~0.8 |
| **Total documentation + assurance load** | **≈ 4.1 FTE-years/year** |

## 3. How the work is distributed

This load is **not** carried by a "documentation team." It is distributed across:

- **CISO office** (~1.5 FTE equivalent of the total) — policy / standard authorship, RMC pack, regulator engagement, ISO support
- **CRO office / 2nd-line Technology Risk** (~1.0 FTE) — REG-TR, REG-GAP, REG-EXC, REG-MR, Management Review pack, framework reviews
- **Internal Audit** (~0.5 FTE) — audit engagements, REG-AUD operation, BAC pack
- **CIO / Head of IT Ops** (~0.5 FTE) — REG-CHG, REG-DRR, change-related documentation
- **Function heads (CHRO, CDO, COO, DPO, CCO, Head of Cloud, Head of TPRM)** (~0.5–0.7 FTE aggregate) — their respective domain's documentation
- **ISMS Manager** (~0.5 FTE) — master register, change log, approval register, document lifecycle administration, audit-evidence assembly

## 4. Where the cost can be cut

Honest options for an adopting bank that finds 4 FTE-years unacceptable:

| Option | Saves | Cost |
|---|---|---|
| Reduce 32 registers — collapse evidence-bucket registers into the GRC tool's native objects | ~0.5 FTE | Loses the "document-of-record" abstraction; harder for an auditor unfamiliar with the GRC tool |
| Defer AIGF until FY2027 | ~0.2 FTE | Pushes AI risk to ad-hoc handling — may not pass first AI use case scrutiny |
| Defer the deferred ITIL / COBIT additions (Problem, SLM, Project, EA, Knowledge) | ~0.3 FTE | Already deferred — no further saving here |
| Combine quarterly RMC packs (technology + business risk) into one composite pack | ~0.2 FTE | RMC may want technology separately; depends on Committee preference |
| Outsource ISO 27001 internal audit | ~0.3 FTE (gross) | External cost; loses internal audit independence development |
| Reduce annual SOP review to biennial for low-volatility SOPs | ~0.2 FTE | ISO 27001 may flag — requires documented justification |
| **Aggregate realistic saving** | **~1.0–1.2 FTE-years** | Brings total to ~3.0 FTE-years |

Going below ~3 FTE-years materially compromises ISO 27001 + BNM examination posture.

## 5. The recommendation

Adopt the suite **and accept the ~3 FTE-year documentation load** explicitly — name it in the resourcing request to the Board / RMC. The alternative (under-resource and let the suite decay into theatre) is worse: theatre fails on first BNM examination and damages the bank's regulatory standing.

The right framing for the Board is: this is the cost of an **examiner-ready** ISMS + BCMS + AI governance posture for a Tier-2 NCII-designated Islamic bank. The bank is paying this cost regardless — the question is whether it is paid as planned investment or as crisis-mode remediation when an examiner finds the suite stale.

## 6. Related documents

- [_learning/grc-platform-format.md](grc-platform-format.md) — where GRC-tool adoption can reduce register-operation cost
- [_learning/migration-playbook.md](migration-playbook.md) — adoption guidance
- [Board Reporting and Escalation Annex](../00-architecture/board-reporting-and-escalation-annex.md) — what the Board sees
- [PLN-08 Internal Audit Plan](../05-plans/PLN-08-internal-audit-plan.md)
