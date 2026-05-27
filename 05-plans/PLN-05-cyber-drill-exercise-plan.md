# PLN-05 — Cyber Drill Exercise Plan

| | |
|---|---|
| **Document ID** | PLN-05 | **Version** | 1.0 |
| **Owner / Approver** | CISO / RMC |
| **Parent framework** | [CRMF](../01-frameworks/CRMF.md) |
| **RMiT clause(s)** | Section 11.16 (Annual Cyber Drill Exercise — mandatory) |
| **Source procedure** | [SOP-CR-01 Cyber Drill Exercise SOP](../04-procedures/SOP-CR-01-cyber-drill-exercise-sop.md) |

## 1. Purpose

To establish GIBB's multi-year cyber drill exercise programme, satisfying RMiT 11.16 annual cyber drill obligation and the broader CRF testing requirement at RMiT 11.3(f).

## 2. Scope

All exercise activity testing GIBB cyber resilience — tabletop quarterly, functional annually, plus the mandatory annual full cyber drill (RMiT 11.16).

## 3. Multi-year scenario rotation

| Year | Primary scenario | Secondary scenario |
|---|---|---|
| Year 1 | Ransomware affecting production estate | Insider abuse of privileged access |
| Year 2 | Material cloud provider compromise | Customer-facing service compromise (DDoS + intrusion) |
| Year 3 | Supply-chain compromise via TPSP | Payment-system compromise |
| Year 4 | Destructive cyber attack triggering BCP | Generative AI / data exfiltration |
| Year 5 | NCII-scope cyber event involving NACSA notification | Insider data exfiltration |
| (Continues with refresh of Year 1 scenarios) | | |

## 4. Exercise types

| Type | Cadence | Duration | Participants |
|---|---|---|---|
| Tabletop | Quarterly | 2–3 hours | CISO, Head of SOC, IC roles, observers |
| Functional / hands-on | Annual | Full day | + relevant technical teams; partial executive engagement |
| **Full cyber drill (RMiT 11.16)** | **Annual — mandatory** | 1–2 days | + full executive team; selective Board observation; external facilitator |
| Joint with BCP/DRP | Annually overlapping | Variable | + COO, BC team, service owners |
| Red team operation | Per CISO cadence; aligned with RMiT 11.6 | Multi-week | External red team |

## 5. Participation

| Role | Tabletop | Functional | Full drill |
|---|---|---|---|
| CISO | ✓ | ✓ | ✓ |
| Head of SOC + SOC team | ✓ | ✓ | ✓ |
| CIO + IT Operations | ✓ (sample) | ✓ | ✓ |
| CEO | (sample) | (sample) | ✓ |
| CRO | (sample) | (sample) | ✓ |
| CCO | (sample) | ✓ | ✓ |
| General Counsel | (sample) | (sample) | ✓ |
| Head of Corp Comms | (sample) | ✓ | ✓ |
| Shariah Compliance | (where scenario-relevant) | (where scenario-relevant) | ✓ (where scenario-relevant) |
| Board (observation) | — | — | (selective) |
| External facilitator | — | (optional) | ✓ |
| External red team | — | — | (year-aligned) |

## 6. Activation and scenario design

Per [SOP-CR-01 Phase 1](../04-procedures/SOP-CR-01-cyber-drill-exercise-sop.md). Scenarios designed to test the nine CRF mandatory elements per RMiT 11.3, including:
- Out-of-band communication infrastructure (RMiT 11.15)
- CERT readiness (RMiT 11.14)
- Cyber Crisis Management (RMiT 11.12)
- IRP execution (RMiT 11.13)
- BNM notification (RMiT 11.18) — simulated in exercise
- NACSA notification (if NCII scope) — simulated

## 7. Evaluation criteria

| Criterion | Pass threshold |
|---|---|
| MTTD per [STD-IR-01 §3.3](../03-standards/STD-IR-01-incident-classification-and-severity-standard.md) | Met for scenario severity |
| MTTC per STD-IR-01 §3.3 | Met for scenario severity |
| Decision-quality at IC | Sound per observer assessment |
| Communication accuracy and timing | Per [PLN-04](PLN-04-crisis-communications-plan.md) matrix |
| Out-of-band channel performance | Working as designed |
| Recovery validation | Restored state validated free of IoCs |
| Shariah implications addressed (if scenario-relevant) | Per Shariah Committee criteria |

## 8. Reporting

| Audience | Content | Cadence |
|---|---|---|
| RMC | Drill report — strengths, gaps, action items | After every full drill |
| Board | Annual summary including the annual cyber drill outcome | Annual |
| BNM | Available on examination | On request |

## 9. Record-keeping

Per [REG-DRL Cyber Drill Register](../06-registers/REG-DRL-cyber-drill-register.md). Each exercise generates an entry. Retained permanently for RMiT 11.16 evidence.

## 10. Document control
| Version | Date | Author | Approver | Change |
|---|---|---|---|---|
| 1.0 | [Effective] | CISO | RMC | Initial |
