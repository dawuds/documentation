# 05 — Registers (Evidence)

The **evidence layer**. Risk, asset, control applicability, training, exception, access review, incident — these registers are what auditors and regulators actually inspect.

← [Back to repo home](../README.md) · [Foundations](../00-foundations/) ↑

---

## What registers are for

A policy says *what shall happen*. A standard says *measurably*. A procedure says *how*. A register **proves** the control is operating.

If you cannot point to a register that proves a control is operating, the control is theoretical, no matter how good the policy reads. This is the single most common audit-failure pattern for ISMS suites: full policy stack, no operating evidence.

Registers in this repo are **operational** — they are updated continuously, not annually. The annual ISMS Management Review consumes them; they don't exist for the Review.

---

## Registers in this repo

| ID | Document | Owner | Cadence | Implements |
|---|---|---|---|---|
| **REG-SOA** | [Statement of Applicability](statement-of-applicability.md) | CISO | Annual + on change | ISO/IEC 27001:2022 Clause 6.1.3 d (**mandatory**) |
| **REG-RR** | [Risk Register](risk-register.md) | CRO (CISO for InfoSec risk subset) | Continuous | ISO/IEC 27001:2022 Cl. 6.1.2 / 6.1.3; BNM RMiT §9 (TRMF) |
| **REG-PAR** | [Privileged Access Review Register](privileged-access-review-register.md) | Head of IAM | **Quarterly** review | ISO/IEC 27002:2022 control 5.18; BNM RMiT §10.53–10.57 |
| **REG-INC** | [Incident Register](incident-register.md) | CISO | Continuous | ISO/IEC 27002:2022 controls 5.25–5.27; BNM RMiT §11.12–11.20 |

---

## Registers General Bank would add

(Not yet drafted — natural extensions for a complete M3 ISMS.)

| Register | Owner | Cadence | Why |
|---|---|---|---|
| Asset Register | Head of IT Ops | Continuous | RMiT §11.3(h) requires a centralised automated tracking system |
| Exception Register | ISMS Manager | Continuous | Every documented deviation from policy/standard |
| Training Register | CHRO + CISO | Continuous | ISO 27001 Clause 7.2 evidence of competence |
| Supplier Register | Procurement + CISO | Continuous | Per POL-07 — supplier criticality, attestation status, contract dates |
| Vulnerability Register | CISO | Continuous | Per POL-13 — beyond the scanner; SLA tracking, exceptions |
| Cloud Inventory Register | Head of Cloud Eng + CISO | Continuous | Per RMiT §10.50–10.52 |
| Records of Processing Activity | DPO | Continuous | Per PDPA 2010 and POL-14 §3.3 |

---

## The SoA is the showpiece

The Statement of Applicability is the single most consequential register for ISO 27001 certification. It is:

- **Required** by ISO/IEC 27001:2022 Clause 6.1.3 d.
- The **first** document a certification auditor reads.
- The **bridge** between ISO 27002:2022 (controls) and the bank's own ISMS implementation.

In this repo, [REG-SOA](statement-of-applicability.md) covers **all 93 Annex A controls** (4 themes: Organisational 37, People 8, Physical 14, Technological 34), each mapped to its implementing policy/standard/SOP and to the BNM RMiT clause it co-satisfies.

---

## Document anatomy

Every register in this folder follows the same five-section structure:

1. **Purpose** — what this register evidences
2. **Schema** — fields, types, sources
3. **Worked example** — first rows so readers see the shape
4. **Maintenance** — who updates, when, how
5. **Related documents** — source SOP, parent standard, parent policy

See [`../_templates/register-template.md`](../_templates/register-template.md).

---

## Cross-links

- ↑ [Policies (Tier 1)](../01-policies/) — the principles each register evidences
- ↑ [Standards (Tier 2)](../02-standards/) — the requirements each register measures
- ↑ [Procedures (Tier 3)](../03-procedures/) — the SOPs that populate each register
- → [Document control](../06-document-control/) — version history and approval for each register
