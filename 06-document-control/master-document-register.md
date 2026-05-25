# Master Document Register

Single source of truth for every document in the ISMS. One row per document. Current state only — for change history, see [`change-log.md`](change-log.md); for archived prior versions, see [`archive/`](archive/).

| | |
|---|---|
| **Owner** | ISMS Manager |
| **Cadence** | Continuous — updated at every document state transition |
| **Implements** | ISO/IEC 27001:2022 Clause 7.5 (Control of documented information) |

---

## Status legend

| Status | Meaning |
|---|---|
| Draft | Document is being written; not authoritative |
| In Review | Out for stakeholder and 2nd-line review |
| Pending Approval | Review complete; awaiting approver sign-off |
| Approved | Approved but not yet effective (staged rollout) |
| **Effective** | Live and authoritative |
| Under Revision | A material update is being prepared while the current version remains Effective |
| Superseded | Replaced by a later version (see archive) |
| Retired | No longer applicable (see archive) |

---

## Register

> **Note.** Dates in this register are illustrative for the General Bank worked example. In a real ISMS, every row carries verifiable approval evidence (minute reference, email archive, workflow ticket).

### Tier 1 — Policies

| ID | Title | Version | Status | Owner | Approver | Approval date | Effective | Next review | ISO 27002:2022 | BNM RMiT |
|---|---|---|---|---|---|---|---|---|---|---|
| POL-00 | [Information Security Policy](../01-policies/00-information-security-policy.md) | 1.0 | Effective | CISO | Board of Directors | 2026-01-15 | 2026-02-01 | 2027-02-01 | 5.1 | §8, §10 |
| POL-01 | [Acceptable Use Policy](../01-policies/01-acceptable-use-policy.md) | 1.0 | Effective | CISO | RMC | 2026-01-15 | 2026-02-01 | 2027-02-01 | 5.10, 8.1 | App. 6 |
| POL-02 | [Access Control Policy](../01-policies/02-access-control-policy.md) | 1.0 | Effective | CISO | RMC | 2026-01-15 | 2026-02-01 | 2027-02-01 | 5.15–5.18, 8.2–8.5 | App. 6 |
| POL-03 | [Asset Management Policy](../01-policies/03-asset-management-policy.md) | 1.0 | Effective | CISO | RMC | 2026-01-15 | 2026-02-01 | 2027-02-01 | 5.9–5.11 | §9 |
| POL-04 | [Data Classification & Handling Policy](../01-policies/04-data-classification-policy.md) | 1.0 | Effective | CISO | RMC | 2026-01-15 | 2026-02-01 | 2027-02-01 | 5.12, 5.13 | App. 9 |
| POL-05 | [Cryptography Policy](../01-policies/05-cryptography-policy.md) | 1.0 | Effective | CISO | RMC | 2026-01-15 | 2026-02-01 | 2027-02-01 | 8.24 | §10 |
| POL-06 | [HR Security Policy](../01-policies/06-hr-security-policy.md) | 1.0 | Effective | CHRO + CISO | RMC | 2026-01-15 | 2026-02-01 | 2027-02-01 | 6.1–6.6 | §12 |
| POL-07 | [Supplier & Third-Party Security Policy](../01-policies/07-supplier-security-policy.md) | 1.0 | Effective | CISO | RMC | 2026-01-15 | 2026-02-01 | 2027-02-01 | 5.19–5.23 | App. 5, §13 |
| POL-08 | [Incident Management Policy](../01-policies/08-incident-management-policy.md) | 1.0 | Effective | CISO | RMC | 2026-01-15 | 2026-02-01 | 2027-02-01 | 5.24–5.28 | §10.36–10.43 |
| POL-09 | [Business Continuity Policy](../01-policies/09-business-continuity-policy.md) | 1.0 | Effective | COO | RMC | 2026-01-15 | 2026-02-01 | 2027-02-01 | 5.29, 5.30 | App. 3 |
| POL-10 | [Physical & Environmental Security Policy](../01-policies/10-physical-security-policy.md) | 1.0 | Effective | Head of Facilities | RMC | 2026-01-15 | 2026-02-01 | 2027-02-01 | 7.1–7.14 | App. 3 |
| POL-11 | [Operations Security Policy](../01-policies/11-operations-security-policy.md) | 1.0 | Effective | Head of IT Ops | RMC | 2026-01-15 | 2026-02-01 | 2027-02-01 | 8.6, 8.7, 8.13, 8.15, 8.16, 8.32 | §9 |
| POL-12 | [Secure Development Policy](../01-policies/12-secure-development-policy.md) | 1.0 | Effective | Head of Engineering | RMC | 2026-01-15 | 2026-02-01 | 2027-02-01 | 8.25–8.31 | App. 8 |
| POL-13 | [Vulnerability Management Policy](../01-policies/13-vulnerability-management-policy.md) | 1.0 | Effective | CISO | RMC | 2026-01-15 | 2026-02-01 | 2027-02-01 | 8.8 | App. 7 |
| POL-14 | [Compliance Policy](../01-policies/14-compliance-policy.md) | 1.0 | Effective | Chief Compliance Officer | RMC | 2026-01-15 | 2026-02-01 | 2027-02-01 | 5.31–5.36 | §11 |

### Tier 2 — Standards

| ID | Title | Version | Status | Owner | Approver | Approval date | Effective | Next review | Parent policy |
|---|---|---|---|---|---|---|---|---|---|
| STD-02-01 | [Password & Authentication Standard](../02-standards/password-and-authentication-standard.md) | 1.0 | Effective | CISO | CISO | 2026-01-20 | 2026-02-01 | 2027-02-01 | POL-02 |
| STD-08-01 | [Incident Classification & Severity Standard](../02-standards/incident-classification-and-severity-standard.md) | 1.0 | Effective | CISO | CISO | 2026-01-20 | 2026-02-01 | 2027-02-01 | POL-08 |

### Tier 3 — Procedures / SOPs

| ID | Title | Version | Status | Owner | Approver | Approval date | Effective | Next review | Parent standard |
|---|---|---|---|---|---|---|---|---|---|
| SOP-02-01 | [Joiner / Mover / Leaver SOP](../03-procedures/joiner-mover-leaver-sop.md) | 1.0 | Effective | Head of IAM | Head of IAM | 2026-01-25 | 2026-02-01 | 2027-02-01 | STD-02-01 |
| SOP-08-01 | [Incident Triage SOP](../03-procedures/incident-triage-sop.md) | 1.0 | Effective | Head of SOC | Head of SOC | 2026-01-25 | 2026-02-01 | 2027-02-01 | STD-08-01 |

### Plans

| ID | Title | Version | Status | Owner | Approver | Approval date | Effective | Next review | Parent policy |
|---|---|---|---|---|---|---|---|---|---|
| PLN-08-01 | [Incident Response Plan](../04-plans/incident-response-plan.md) | 1.0 | Effective | CISO | RMC | 2026-01-15 | 2026-02-01 | 2027-02-01 | POL-08 |

### Registers

| ID | Title | Owner | Cadence | Purpose |
|---|---|---|---|---|
| REG-SOA | [Statement of Applicability](../05-registers/statement-of-applicability.md) | CISO | Annual + on change | ISO 27001 Clause 6.1.3 d evidence |
| REG-RR | [Risk Register](../05-registers/risk-register.md) | CRO | Continuous | Risk identification, treatment, monitoring |
| REG-PAR | [Privileged Access Review Register](../05-registers/privileged-access-review-register.md) | Head of IAM | Quarterly | Evidence of quarterly privileged access reviews |
| REG-INC | [Incident Register](../05-registers/incident-register.md) | CISO | Continuous | Log of all security incidents |

---

## Maintenance

The ISMS Manager reviews this register **monthly** to identify documents approaching their next-review date (60-day lookahead). The CISO reviews it **quarterly** as part of the ISMS Management Review (ISO 27001 Clause 9.3).

A document past its next-review date is treated as a **control deficiency** and reported through the same channel as a control failure — not as an administrative oversight.
