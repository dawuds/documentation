# 01 — Policies (Tier 1)

Principle-level documents. Board- or executive-approved. Mandatory. Annual review.

← [Repo home](../README.md) · [Foundations](../00-foundations/) ↑

---

## Master

| Document | Approver |
|---|---|
| [**POL-00 Information Security Policy**](00-information-security-policy.md) | Board of Directors (per ISO/IEC 27001:2022 Clause 5.2) |

POL-00 establishes the ISMS, names the supporting policies, and is the only document in this folder that every reader of the suite must read in full.

## Supporting suite

★ = fully drafted as worked example. Others are first-pass skeletons; see [`../_learning/extension-roadmap.md`](../_learning/extension-roadmap.md) for the completion path.

| ID | Document | ISO 27002:2022 | BNM RMiT (28 Nov 2025) |
|---|---|---|---|
| POL-01 | [Acceptable Use Policy](01-acceptable-use-policy.md) | 5.10, 8.1 | §10.53–10.57; §15 |
| **POL-02** ★ | [Access Control Policy](02-access-control-policy.md) | 5.15–5.18, 8.2–8.5 | §10.53–10.57 |
| POL-03 | [Asset Management Policy](03-asset-management-policy.md) | 5.9–5.11 | §9.2; §11.3(h) |
| POL-04 | [Data Classification & Handling Policy](04-data-classification-policy.md) | 5.12, 5.13 | §9.2(d); §12 |
| POL-05 | [Cryptography Policy](05-cryptography-policy.md) | 8.24 | §10.20–10.23 |
| POL-06 | [HR Security Policy](06-hr-security-policy.md) | 6.1–6.6 | §15 |
| POL-07 | [Supplier & Third-Party Security Policy](07-supplier-security-policy.md) | 5.19–5.23 | §10.46–10.49; §14; App. 10 |
| **POL-08** ★ | [Incident Management Policy](08-incident-management-policy.md) | 5.24–5.28 | §11 (whole section) |
| POL-09 | [Business Continuity Policy](09-business-continuity-policy.md) | 5.29, 5.30 | §10.24–10.28; §10.29–10.35 |
| POL-10 | [Physical & Environmental Security Policy](10-physical-security-policy.md) | 7.1–7.14 | §10.26 |
| POL-11 | [Operations Security Policy](11-operations-security-policy.md) | 8.6, 8.7, 8.13, 8.15, 8.16, 8.32 | §10; §11.9–11.11 |
| POL-12 | [Secure Development Policy](12-secure-development-policy.md) | 8.25–8.31 | §10.4–10.16 |
| POL-13 | [Vulnerability & Patch Management Policy](13-vulnerability-management-policy.md) | 8.8 | §10.17–10.19; §11.6; §11.7 |
| POL-14 | [Compliance Policy](14-compliance-policy.md) | 5.31–5.36 | §13; §14; §18; §11.4 |

## Cascades

How a single principle flows from policy to evidence. Two cascades drafted in full:

| Cascade | Policy | Standard | Procedure | Plan | Register |
|---|---|---|---|---|---|
| Access Control | [POL-02](02-access-control-policy.md) | [STD-02-01](../02-standards/password-and-authentication-standard.md) | [SOP-02-01](../03-procedures/joiner-mover-leaver-sop.md) | — | [REG-PAR](../05-registers/privileged-access-review-register.md) |
| Incident Management | [POL-08](08-incident-management-policy.md) | [STD-08-01](../02-standards/incident-classification-and-severity-standard.md) | [SOP-08-01](../03-procedures/incident-triage-sop.md) | [PLN-08-01](../04-plans/incident-response-plan.md) | [REG-INC](../05-registers/incident-register.md) |

## Anatomy

Every policy uses the ten-section skeleton in [`../_templates/policy-template.md`](../_templates/policy-template.md): Purpose · Scope · Definitions · Policy statements (the **shall** clauses) · Roles & responsibilities · Exceptions · Enforcement · Related documents · References · Document control.

---

[`../02-standards/`](../02-standards/) ↓ · [`../05-registers/statement-of-applicability.md`](../05-registers/statement-of-applicability.md) — maps every ISO 27002 control to its implementing policy · [`../06-document-control/`](../06-document-control/) — version history and approvals
