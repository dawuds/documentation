# 05 — Registers (Evidence)

Operational records that evidence the controls are operating. Continuously updated.

← [Repo home](../README.md) · [Foundations](../00-foundations/) ↑

---

## Purpose

If you cannot point to a register that proves a control is operating, the control is theoretical. Registers are what auditors and regulators inspect to verify the ISMS is real, not paper.

## Contents

| ID | Document | Owner | Cadence | Implements |
|---|---|---|---|---|
| REG-SOA | [Statement of Applicability](statement-of-applicability.md) | CISO | Annual + on change | ISO/IEC 27001:2022 Clause 6.1.3 d (**mandatory**) — all 93 Annex A controls mapped |
| REG-RR | [Risk Register](risk-register.md) | CRO (CISO for InfoSec subset) | Continuous | ISO/IEC 27001:2022 Cl. 6.1.2 / 6.1.3; BNM RMiT §9 (TRMF) |
| REG-PAR | [Privileged Access Review Register](privileged-access-review-register.md) | Head of IAM | Quarterly review | ISO/IEC 27002:2022 control 5.18; BNM RMiT §10.53–10.57 |
| REG-INC | [Incident Register](incident-register.md) | CISO | Continuous | ISO/IEC 27002:2022 controls 5.25–5.27; BNM RMiT §11.12–11.20 |

Additional registers a complete M3 ISMS would maintain (Asset, Exception, Training, Supplier, Vulnerability, Cloud Inventory, ROPA): see [`../_learning/extension-roadmap.md`](../_learning/extension-roadmap.md).

## The SoA

[REG-SOA](statement-of-applicability.md) is the most consequential register for ISO/IEC 27001:2022 certification. It is required by Clause 6.1.3 d, is the first document a certification auditor reads, and is the bridge between ISO/IEC 27002:2022 (controls) and the implementation in this ISMS.

## Anatomy

Every register uses the five-section skeleton in [`../_templates/register-template.md`](../_templates/register-template.md): Purpose · Schema · Worked example · Maintenance · Related documents.

---

[`../01-policies/`](../01-policies/) ↑ · [`../02-standards/`](../02-standards/) ↑ · [`../03-procedures/`](../03-procedures/) ↑ · [`../06-document-control/`](../06-document-control/)
