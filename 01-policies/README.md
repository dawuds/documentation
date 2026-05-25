# 01 — Policies (Tier 1)

The **principle layer** of the documentation suite. Board- or executive-approved. Mandatory. Stable (annual review).

← [Back to repo home](../README.md) · [Foundations](../00-foundations/) ↑

---

## What policies are for

Policies state the **what** and the **why** — the principles by which General Bank protects information assets. They use **shall** statements. They are written so a non-technical reader can understand the intent.

Policies do not say *how*. The moment a policy says "click here", "use Okta", or "the script is at \\\\share\\onboarding\\", it has become a procedure dressed as a policy. See [`../00-foundations/document-hierarchy.md`](../00-foundations/document-hierarchy.md) §3 confusions for why this matters.

---

## The master policy

| Document | What it does |
|---|---|
| **[POL-00 Information Security Policy](00-information-security-policy.md)** | **Master.** Board-approved per ISO/IEC 27001:2022 Clause 5.2. Establishes the ISMS. Names the supporting policies. Cites Cyber Security Act 2024 and BNM RMiT (28 Nov 2025). |

The master is the only document in this folder that **must** be read in full by every reader of the repo. Read it first.

---

## Supporting policy suite

Each supporting policy is mandatory within its scope. **Bold** rows are fully drafted as worked examples; the others are first-pass skeletons suitable as starting points.

| ID | Document | One-line | Cascade target | ISO 27002:2022 | BNM RMiT |
|---|---|---|---|---|---|
| POL-01 | [Acceptable Use Policy](01-acceptable-use-policy.md) | What users may and may not do with bank assets | — | 5.10, 8.1 | §10.53–10.57; §15 |
| **POL-02** | **[Access Control Policy](02-access-control-policy.md)** ★ | Least-privilege, RBAC, MFA, privileged access, quarterly reviews | [Cascade 1](#cascade-1-access-control) | 5.15–5.18, 8.2–8.5 | §10.53–10.57 |
| POL-03 | [Asset Management Policy](03-asset-management-policy.md) | Identifying, owning, classifying, lifecycle of assets | — | 5.9–5.11 | §9.2; §11.3(h) |
| POL-04 | [Data Classification & Handling Policy](04-data-classification-policy.md) | Public / Internal / Confidential / Highly Restricted | — | 5.12, 5.13 | §9.2(d); §12 |
| POL-05 | [Cryptography Policy](05-cryptography-policy.md) | Use of crypto, key management, PKI, post-quantum readiness | — | 8.24 | §10.20–10.23 |
| POL-06 | [HR Security Policy](06-hr-security-policy.md) | Screening, NDAs, training, disciplinary, off-boarding | — | 6.1–6.6 | §15 |
| POL-07 | [Supplier & Third-Party Security Policy](07-supplier-security-policy.md) | TPSP onboarding, contracts, cloud, monitoring, exit | — | 5.19–5.23 | §10.46–10.49; §14; App. 10 |
| **POL-08** | **[Incident Management Policy](08-incident-management-policy.md)** ★ | CRF, detection, response, notification, learning | [Cascade 2](#cascade-2-incident-management) | 5.24–5.28 | §11 (whole section) |
| POL-09 | [Business Continuity Policy](09-business-continuity-policy.md) | BIA, RTO/RPO, ICT readiness, testing, supplier continuity | — | 5.29, 5.30 | §10.24–10.28; §10.29–10.35 |
| POL-10 | [Physical & Environmental Security Policy](10-physical-security-policy.md) | Perimeter, entry, visitors, clear desk, equipment | — | 7.1–7.14 | §10.26 |
| POL-11 | [Operations Security Policy](11-operations-security-policy.md) | Change, capacity, malware, backup, logging, monitoring | — | 8.6, 8.7, 8.13, 8.15, 8.16, 8.32 | §10; §11.9–11.11 |
| POL-12 | [Secure Development Policy](12-secure-development-policy.md) | SDLC, threat modelling, secure coding, SAST/DAST | — | 8.25–8.31 | §10.4–10.16 |
| POL-13 | [Vulnerability & Patch Management Policy](13-vulnerability-management-policy.md) | Scanning, prioritisation, remediation timelines, red team | — | 8.8 | §10.17–10.19; §11.6; §11.7 |
| POL-14 | [Compliance Policy](14-compliance-policy.md) | Legal/regulatory register, NCII, independent review | — | 5.31–5.36 | §13; §14; §18; §11.4 |

★ = fully drafted (with cascade to standards, SOPs, plans, registers).

---

## Cascade 1 — Access Control

How a single principle ("access shall be least-privilege, RBAC, reviewed quarterly") flows from policy → standard → procedure → register.

| Layer | Document |
|---|---|
| Policy | [POL-02 Access Control Policy](02-access-control-policy.md) |
| ↓ Standard | [STD-02-01 Password & Authentication Standard](../02-standards/password-and-authentication-standard.md) |
| ↓ Procedure | [SOP-02-01 Joiner / Mover / Leaver SOP](../03-procedures/joiner-mover-leaver-sop.md) |
| ↓ Register (evidence) | [REG-PAR Privileged Access Review Register](../05-registers/privileged-access-review-register.md) |

---

## Cascade 2 — Incident Management

How a single principle ("we detect, classify, respond, notify, and learn") flows from policy → standard → procedure → plan → register, anchored on the BNM RMiT Cyber Resilience Framework (§11.2, §11.3).

| Layer | Document |
|---|---|
| Policy | [POL-08 Incident Management Policy](08-incident-management-policy.md) |
| ↓ Standard | [STD-08-01 Incident Classification & Severity Standard](../02-standards/incident-classification-and-severity-standard.md) |
| ↓ Procedure | [SOP-08-01 Incident Triage SOP](../03-procedures/incident-triage-sop.md) |
| ↓ Plan | [PLN-08-01 Incident Response Plan](../04-plans/incident-response-plan.md) |
| ↓ Register (evidence) | [REG-INC Incident Register](../05-registers/incident-register.md) |

---

## Document anatomy (all policies share the same skeleton)

Every policy in this folder follows the same ten-section structure — readers learn one template, not fifteen.

1. **Purpose** — why this policy exists
2. **Scope** — who/what it applies to
3. **Definitions** — terms used in this policy
4. **Policy statements** — the **shall** clauses with citations
5. **Roles & responsibilities** — RACI
6. **Exceptions** — how deviations are handled
7. **Enforcement** — consequences of non-compliance
8. **Related documents** — links up to parent, down to children
9. **References** — ISO clauses, regulation, internal docs
10. **Document control** — version history, owner, approver

See [`../_templates/policy-template.md`](../_templates/policy-template.md) for the template.

---

## Cross-links

- ↑ [Foundations](../00-foundations/) — read first for the document model
- ↓ [Standards (Tier 2)](../02-standards/) — quantified detail implementing these policies
- → [Statement of Applicability](../05-registers/statement-of-applicability.md) — maps each ISO 27002:2022 control to its implementing policy
- → [Document control](../06-document-control/) — current state, change log, approvals for every policy
