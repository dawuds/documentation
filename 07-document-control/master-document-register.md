# Master Document Register

Single source of truth for every document in the v2 ISMS / IT governance suite. One row per document. Current state only — for change history see [`change-log.md`](change-log.md); for archived prior versions see [`archive/`](archive/).

| | |
|---|---|
| **Owner** | ISMS Manager |
| **Cadence** | Continuous |
| **Implements** | ISO/IEC 27001:2022 Clause 7.5; BNM RMiT 9.2(h) |
| **Last updated** | 2026-05-27 |

---

## Status legend

| Status | Meaning |
|---|---|
| Draft | Being written; not authoritative |
| In Review | Out for 2nd-line / stakeholder review |
| Pending Approval | Review complete; awaiting approver sign-off |
| Approved | Approved but not yet effective |
| **Effective** | Live and authoritative |
| Under Revision | Material update being prepared while current version remains Effective |
| Superseded | Replaced by later version (see archive) |
| Retired | No longer applicable (see archive) |

---

## v2 Architecture (00-architecture)

| ID | Title | Version | Status | Owner | Approver | Effective | Next review |
|---|---|---|---|---|---|---|---|
| ARCH-001 | [GIBB IT Governance Architecture](../00-architecture/architecture.md) | 1.0 | Draft | CRO + CISO | Board Risk Management Committee | [Effective] | Annual |

---

## v2 Layer 2 — Frameworks (01-frameworks)

| ID | Title | Version | Status | Owner | Approver | Effective | Next review |
|---|---|---|---|---|---|---|---|
| TRMF | [Technology Risk Management Framework](../01-frameworks/TRMF.md) | 1.0 | Draft | CRO + Head of TRM | Board RMC | [Effective] | Annual |
| CRMF | [Cyber Risk Management Framework](../01-frameworks/CRMF.md) | 1.0 | Draft | CISO | Board RMC | [Effective] | Annual |
| BCMF | [Business Continuity Management Framework](../01-frameworks/BCMF.md) | 1.0 | Draft | COO | Board RMC | [Effective] | Annual |
| TPRMF | [Third Party Risk Management Framework](../01-frameworks/TPRMF.md) | 1.0 | Draft | Head of Procurement + CRO | Board RMC | [Effective] | Annual |
| CIMF | [Customer Information Management Framework](../01-frameworks/CIMF.md) | 1.0 | Draft | DPO + CCO | Board RMC | [Effective] | Annual |
| NCIIF | [NCII Compliance Framework](../01-frameworks/NCIIF.md) | 1.0 | Draft | CISO + CCO | Board RMC | [Effective] | Annual |
| CloudRMF | [Cloud Risk Management Framework](../01-frameworks/CloudRMF.md) | 1.0 | Draft | Head of Cloud + CISO | Board RMC | [Effective] | Annual |
| DGF | [Data Governance Framework](../01-frameworks/DGF.md) | 1.0 | Draft | CDO | Board RMC | [Effective] | Annual |
| AIGF | [AI Governance Framework](../01-frameworks/AIGF.md) | 1.0 | Draft | CDO + CISO | Board RMC | [Effective] | Annual |

---

## v2 Layer 3 — Policies (02-policies)

| ID | Title | Version | Status | Owner | Approver | Effective | Next review | Parent framework |
|---|---|---|---|---|---|---|---|---|
| POL-01 | [IT Governance Policy](../02-policies/POL-01-it-governance-policy.md) | 1.0 | Draft | CIO + CRO | **Board of Directors** | [Effective] | Annual | TRMF |
| POL-02 | [Technology Risk Management Policy](../02-policies/POL-02-technology-risk-management-policy.md) | 1.0 | Draft | CRO | RMC | [Effective] | Annual | TRMF |
| POL-03 | [Technology Risk Appetite Statement](../02-policies/POL-03-technology-risk-appetite-statement.md) | 1.0 | Draft | CRO | **Board of Directors** | [Effective] | Annual | TRMF |
| POL-07 | [Change Management Policy](../02-policies/POL-07-change-management-policy.md) | 1.0 | Draft | CIO | RMC | [Effective] | Annual | TRMF |
| POL-08 | [Capacity and Performance Management Policy](../02-policies/POL-08-capacity-and-performance-management-policy.md) | 1.0 | Draft | CIO | RMC | [Effective] | Annual | TRMF / BCMF |
| POL-09 | [IT Asset Management Policy](../02-policies/POL-09-it-asset-management-policy.md) | 1.0 | Draft | CIO + CDO | RMC | [Effective] | Annual | TRMF / DGF |
| POL-15 | [Physical and Environmental Security Policy](../02-policies/POL-15-physical-and-environmental-security-policy.md) | 1.0 | Draft | Head of Facilities + CISO | RMC | [Effective] | Annual | TRMF / BCMF |
| POL-16 | [Operations Security Policy](../02-policies/POL-16-operations-security-policy.md) | 1.0 | Draft | CIO + CISO | RMC | [Effective] | Annual | TRMF / CRMF |
| POL-17 | [Secure Development Policy](../02-policies/POL-17-secure-development-policy.md) | 1.0 | Draft | Head of Engineering + CISO | RMC | [Effective] | Annual | TRMF / CRMF |
| POL-22 | [IT Compliance Policy](../02-policies/POL-22-it-compliance-policy.md) | 1.0 | Draft | CCO | RMC | [Effective] | Annual | TRMF |

---

## v2 Layer 4 — Standards (03-standards)

| ID | Title | Version | Status | Owner | Approver | Effective | Next review | Parent policy |
|---|---|---|---|---|---|---|---|---|
| STD-CM-01 | [Change Management Standard](../03-standards/STD-CM-01-change-management-standard.md) | 1.0 | Draft | CIO | CIO | [Effective] | Annual | POL-07 |
| STD-AM-01 | [IT Asset Management Standard](../03-standards/STD-AM-01-it-asset-management-standard.md) | 1.0 | Draft | CIO + CDO | CIO | [Effective] | Annual | POL-09 |

---

## v2 Layer 5 — Procedures (04-procedures)

| ID | Title | Version | Status | Owner | Approver | Effective | Next review | Parent standard |
|---|---|---|---|---|---|---|---|---|
| SOP-CM-01 | [Change Authorisation SOP](../04-procedures/SOP-CM-01-change-authorisation-sop.md) | 1.0 | Draft | Head of IT Operations | Head of IT Operations | [Effective] | Annual | STD-CM-01 |

---

## v2 Layer 6 — Registers (06-registers)

| ID | Title | Owner | Cadence | Parent framework |
|---|---|---|---|---|
| REG-TR | [Technology Risk Register](../06-registers/REG-TR-technology-risk-register.md) | CRO (Head of TRM operates) | Continuous | TRMF |

---

## v2 Templates (_templates)

| ID | Title | Status |
|---|---|---|
| TPL-FRA | [Framework template](../_templates/framework-template.md) | Effective |
| TPL-POL | [Policy template](../_templates/policy-template.md) | Effective |
| TPL-STD | [Standard template](../_templates/standard-template.md) | Effective |
| TPL-SOP | [Procedure template](../_templates/procedure-template.md) | Effective |
| TPL-PLN | [Plan template](../_templates/plan-template.md) | Effective |
| TPL-REG | [Register template](../_templates/register-template.md) | Effective |

---

## v1 snapshot (locked)

v1 documents are not actively maintained. They are accessible at [`../v1/`](../v1/) for reference and (in subsequent v2 sessions) re-anchoring of InfoSec-domain content under CRMF. The v1.0 git tag preserves the v1 build at its final state.

---

## Pending in Phase 1 (build sessions following Session 4)

The following documents are scoped for future sessions:

**CRMF cascade** — Layer 3 policies (POL-04 Information Security, POL-05 Acceptable Use, POL-06 Access Control, POL-12 Cryptography, POL-13 Incident Management, POL-18 Vulnerability Management, POL-19 Supplier Security) re-anchored from v1; STD password-and-authentication and incident-classification-and-severity re-anchored from v1; SOPs JML and Incident Triage re-anchored from v1; PLN-01 IRP re-anchored from v1; REG-INC, REG-PAR re-anchored from v1.

**Other framework cascades** — Layer 3-6 documents per CRMF, BCMF, TPRMF, CIMF, NCIIF, CloudRMF, DGF, AIGF.

**Other v2 Layer 2 cascade exemplars** — STD-CM-02, SOP-CM-02 (Emergency Change), Capacity Standard, etc.

---

## Maintenance

The ISMS Manager reviews this register **monthly** to identify documents approaching their next-review date (60-day lookahead). The CISO reviews **quarterly** as part of the ISMS Management Review (ISO/IEC 27001:2022 Clause 9.3).

A document past its next-review date is a **control deficiency** and reported through the same channel as a control failure — not as an administrative oversight.
