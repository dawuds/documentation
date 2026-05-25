# 02 — Standards (Tier 2)

The **mandatory, measurable** layer. CISO-approved. Quantifies what the policies leave as principle.

← [Back to repo home](../README.md) · [Foundations](../00-foundations/) ↑ · [Policies](../01-policies/) ↑

---

## What standards are for

A policy says: *"All privileged access shall require multi-factor authentication."*
A standard says: *"Privileged accounts shall use FIDO2/WebAuthn or smart cards. SMS OTP is prohibited. Passwords shall be ≥ 16 characters, machine-generated, rotated per use or every 24 hours, stored in PAM vault."*

Standards make policy testable. Without a standards layer, every SOP author has to make their own security decisions — which means inconsistency, drift, and audit findings.

---

## Standards in this repo

Two standards fully drafted as worked examples — one per cascade. In a real M3 ISMS at General Bank's size, expect 15–25 standards covering specific domains.

| ID | Document | Parent policy | ISO 27002:2022 | BNM RMiT |
|---|---|---|---|---|
| **STD-02-01** | [Password & Authentication Standard](password-and-authentication-standard.md) | [POL-02 Access Control](../01-policies/02-access-control-policy.md) | 5.17, 8.2, 8.5 | §10.53–10.57 (esp. §10.55 MFA) |
| **STD-08-01** | [Incident Classification & Severity Standard](incident-classification-and-severity-standard.md) | [POL-08 Incident Management](../01-policies/08-incident-management-policy.md) | 5.25, 5.26 | §11.12; §11.13; §11.18 (with 4-hour BNM notification) |

---

## Standards General Bank would add as the suite matures

(Not yet drafted — listed here as the natural extension path.)

| Suggested standard | Parent policy | Why |
|---|---|---|
| Cryptographic Standard (algorithms, key lengths, deprecation schedule, post-quantum migration) | POL-05 | Concrete algorithm and key-length choices need a single source of truth |
| Logging Standard (what events to log, format, retention, time-sync) | POL-11 | Auditors and forensics depend on consistent logging |
| Network Security Standard (segmentation tiers, firewall rules baseline, perimeter) | POL-11 | RMiT §10.36–10.43 Network Resilience requires explicit network controls |
| Cloud Security Standard (per provider — AWS / Azure / GCP — landing zone, IAM, encryption defaults) | POL-07 | Operational specificity for §10.50–10.52 + App. 10 |
| Endpoint Standard (managed device baseline, EDR config, MDM rules) | POL-11 / POL-01 | Workforce endpoint security |
| Data Handling Standard (per classification × media combination) | POL-04 | Operationalises Public / Internal / Confidential / Highly Restricted |
| Secure Coding Standard (per language, per framework) | POL-12 | Developer-actionable detail |
| Vulnerability Triage Standard (CVSS thresholds, EPSS factors, KEV handling) | POL-13 | Quantifies POL-13 §3.2 prioritisation |

---

## Document anatomy

Every standard in this folder follows the same seven-section structure:

1. **Purpose** — what measurable requirements this sets
2. **Scope** — systems, environments, data classes
3. **Requirements** — the quantified **shall** statements with evidence/measurement
4. **Exceptions** — typically inherited from the parent policy
5. **Related documents** — parent policy, implementing procedures, supporting baselines
6. **References** — ISO controls, RMiT clauses, technical references (NIST, CIS, etc.)
7. **Document control** — version history

See [`../_templates/standard-template.md`](../_templates/standard-template.md).

---

## Cross-links

- ↑ [Policies (Tier 1)](../01-policies/) — the principle layer that standards implement
- ↓ [Procedures (Tier 3)](../03-procedures/) — the operational layer that implements standards
- → [Statement of Applicability](../05-registers/statement-of-applicability.md) — implementation column references this folder
- → [Document control](../06-document-control/) — version history for every standard
