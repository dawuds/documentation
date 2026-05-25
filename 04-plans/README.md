# 04 — Plans

**Time-bound action sets** for defined scenarios. Plans sit between standards and procedures: scenario-driven, structured by phase, with decision gates and named responders.

← [Back to repo home](../README.md) · [Foundations](../00-foundations/) ↑ · [Policies](../01-policies/) ↑

---

## What plans are for

The big three: **Incident Response Plan (IRP)**, **Business Continuity Plan (BCP)**, **Disaster Recovery Plan (DRP)**. Each has its own activation trigger, authority, phases, and out-of-band communications.

Plans are not procedures (which are steady-state) and not policies (which are principles). They exist because some response activity is scenario-conditional — the plan tells you *how this specific scenario unfolds*, not what to do every day.

---

## Plans in this repo

One plan fully drafted — the IRP, anchored on the BNM RMiT Cyber Resilience Framework.

| ID | Document | Parent policy | Activation authority | Frequency of exercise |
|---|---|---|---|---|
| **PLN-08-01** | [Incident Response Plan](incident-response-plan.md) | [POL-08 Incident Management](../01-policies/08-incident-management-policy.md) | CISO (SEV-1) / Head of SOC (SEV-2) | Quarterly tabletop + annual cyber drill (RMiT §11.16) |

---

## Plans General Bank would add

(Not yet drafted — natural extensions for an M3 ISMS.)

| Plan | Parent policy | Owner | Why |
|---|---|---|---|
| Business Continuity Plan (BCP) | POL-09 | COO | Per BNM RMiT §10.24–10.35 service availability; BCM policy alignment |
| Disaster Recovery Plan (DRP) — per critical system | POL-09 + POL-11 | Head of IT Ops | RTO/RPO-aligned technical recovery procedures per service |
| Crisis Communications Plan | POL-08 + Corporate Communications policy | Head of Corp Comms | Coordinates internal, customer, regulator, media communications during crises |
| Pandemic / Workforce Disruption Plan | POL-09 | COO + CHRO | Workforce-availability scenarios |
| Cyber Crisis Playbook (subordinate to IRP) | POL-08 | CISO | Per-scenario playbooks (ransomware, insider, supplier compromise) — operationalises RMiT §11.12 |

---

## IRP and the Cyber Resilience Framework

The IRP in this repo explicitly maps to the BNM RMiT (28 Nov 2025) Cyber Resilience Framework:

| RMiT clause | IRP section |
|---|---|
| §11.2 — CRF Development | IRP §1 (purpose statement positions IRP as the CRF playbook) |
| §11.3 — CRF nine mandatory elements | Implemented across the IRP and the broader policy suite |
| §11.12 — Cyber Crisis Management | IRP §3 activation, §4 Incident Commander, §5.3 containment authority |
| §11.13 — Cyber Incident Response Plan | This IRP **is** that plan |
| §11.14 — CERT Member Readiness | IRP §5.1 preparation + on-call rotation |
| §11.15 — Out-of-Band Communication Infrastructure | IRP §4 roles & contacts (out-of-band column) |
| §11.16 — Annual Cyber Drill Exercise | IRP §7 testing and exercise |
| §11.17 — Cyber Insurance and Loss Provision | IRP §5.1 preparation |
| §11.18 — Cyber Incident Notification to BNM | IRP §6 communication (with 4-hour clock) |
| §11.19 / §11.20 — Threat Intelligence Sharing / Stakeholder Collaboration | IRP §6 communication |

---

## Document anatomy

Every plan in this folder follows the same nine-section structure:

1. **Purpose** — scenario covered
2. **Scope** — what's in and out
3. **Activation** — triggers and authority
4. **Roles and contacts** — with out-of-band channels
5. **Response phases** — structured per the operative framework (e.g., NIST 800-61 for IR)
6. **Communication** — internal, regulator, customer, public
7. **Testing and exercise** — cadence and type
8. **Reference appendices** — distribution-controlled supporting material
9. **Document control**

See [`../_templates/plan-template.md`](../_templates/plan-template.md).

---

## Cross-links

- ↑ [Policies (Tier 1)](../01-policies/) — the parent policy for each plan
- ↑ [Standards (Tier 2)](../02-standards/) — classification and severity standards that drive IR plan activation
- ↑ [Procedures (Tier 3)](../03-procedures/) — SOPs that the plan invokes during response
- → [Registers](../05-registers/) — incident register populates from IR activation
