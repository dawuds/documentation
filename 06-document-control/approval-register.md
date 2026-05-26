# Approval Register

One row per approval event. The audit-grade evidence trail of *who approved what version of which document, when, and under what authority*.

| | |
|---|---|
| **Owner** | ISMS Manager |
| **Cadence** | Continuous — appended at every approval event |
| **Implements** | ISO/IEC 27001:2022 Clauses 5.1 (leadership commitment), 7.5.3 (control of documented information) |

---

## Why a separate register

The master document register shows the *current* approver per document. The change log shows *what changed*. The approval register answers a distinct question: **"For audit, show me every approval decision made across the ISMS, with the authority under which it was made."**

External auditors and regulators (BNM under RMiT Section 6.6 expects evidence of Board / Board Risk Committee oversight) often ask this question directly. A consolidated register answers it without needing to traverse 30+ individual documents.

---

## Authority legend

| Authority | Documents approved under this authority |
|---|---|
| **Board of Directors** | Master Information Security Policy; Technology Risk Management Framework |
| **Risk Management Committee (RMC)** | Supporting policies (Tier 1, POL-01 through POL-14); Plans (IRP, BCP, DRP) |
| **CISO** | Standards (Tier 2); ISMS-internal exception approvals |
| **Process Owner** | Procedures / SOPs (Tier 3) |
| **CHRO** (joint with CISO) | HR Security Policy |
| **CRO** (joint with CISO) | Risk-related policy clauses |

---

## Register

> Most recent first. Worked example for General Bank.

| Date | Document | Version | Authority | Approver (name / role) | Evidence reference | Notes |
|---|---|---|---|---|---|---|
| 2026-04-22 | STD-02-01 Password & Authentication Standard | 1.1 | CISO | [CISO] | Email approval, archived ISMS-CHG-2026-007 | Minor — service-account rotation language clarified |
| 2026-04-10 | SOP-02-01 Joiner/Mover/Leaver SOP | 1.1 | Process Owner | [Head of IAM] | Workflow JML-CHG-2026-002 | Minor — tool reference update post-IDP migration |
| 2026-01-25 | SOP-08-01 Incident Triage SOP | 1.0 | Process Owner | [Head of SOC] | Workflow IR-CHG-2026-001 | Initial approval |
| 2026-01-25 | SOP-02-01 Joiner/Mover/Leaver SOP | 1.0 | Process Owner | [Head of IAM] | Workflow JML-CHG-2026-001 | Initial approval |
| 2026-01-20 | STD-08-01 Incident Classification & Severity Standard | 1.0 | CISO | [CISO] | Email approval ISMS-2026-002 | Initial approval |
| 2026-01-20 | STD-02-01 Password & Authentication Standard | 1.0 | CISO | [CISO] | Email approval ISMS-2026-001 | Initial approval |
| 2026-01-15 | PLN-08-01 Incident Response Plan | 1.0 | RMC | RMC chair on behalf of committee | RMC minutes 2026-01-15, item 6.3 | Initial approval |
| 2026-01-15 | POL-01 through POL-14 (suite) | 1.0 | RMC | RMC chair on behalf of committee | RMC minutes 2026-01-15, item 6.1 | Initial approval of supporting policy suite |
| 2026-01-15 | POL-00 Information Security Policy | 1.0 | Board of Directors | Board chair on behalf of the Board | Board minutes 2026-01-15, item 4.2 | Initial Board approval of master policy; satisfies ISO 27001 Clause 5.2 |

---

## Maintenance

Each row is **immutable** once added — corrections require a new row referencing the prior one, not an in-place edit. This preserves the audit trail.

When an external audit requests "evidence of approval for [document] [version]", the answer comes from this register, supported by the evidence reference (board minutes, RMC minutes, workflow ID, archived email).

The ISMS Manager reconciles this register quarterly against the master document register to confirm no document is recorded as Effective without a corresponding approval row.
