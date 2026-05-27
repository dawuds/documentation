# 02 — Policies (Layer 3)

Principle-level mandatory documents. Board- or RMC-approved. Annual review.

← [Repo home](../README.md) · [Architecture](../00-architecture/) ↑ · [Frameworks](../01-frameworks/) ↑

---

## TRMF cascade (Session 3 build)

These policies cascade from the [Technology Risk Management Framework (TRMF)](../01-frameworks/TRMF.md) — the IT-governance umbrella.

| Policy ID | Title | Owner | RMiT clause | COBIT |
|---|---|---|---|---|
| [POL-01](POL-01-it-governance-policy.md) | IT Governance Policy | CIO + CRO | Section 8 (Governance); Section 9 | EDM01, APO01 |
| [POL-02](POL-02-technology-risk-management-policy.md) | Technology Risk Management Policy | CRO | Section 9 | EDM03, APO12 |
| [POL-03](POL-03-technology-risk-appetite-statement.md) | Technology Risk Appetite Statement | CRO + Board | Section 8.1 | EDM03 |
| [POL-07](POL-07-change-management-policy.md) | Change Management Policy | CIO | Section 10.11 + ITIL 4 | BAI06 |
| [POL-08](POL-08-capacity-and-performance-management-policy.md) | Capacity and Performance Management Policy | CIO | Section 10.29–10.31 | BAI04 |
| [POL-09](POL-09-it-asset-management-policy.md) | IT Asset Management Policy | CIO + CDO | Section 11.3(h) | BAI09 |
| [POL-15](POL-15-physical-and-environmental-security-policy.md) | Physical and Environmental Security Policy | Head of Facilities + CISO | Section 10.26 | DSS05 |
| [POL-16](POL-16-operations-security-policy.md) | Operations Security Policy | CIO + CISO | Section 10 + Section 11.9 | DSS01 |
| [POL-17](POL-17-secure-development-policy.md) | Secure Development Policy | Head of Engineering + CISO | Section 10.4–10.16 | BAI03 |
| [POL-22](POL-22-it-compliance-policy.md) | IT Compliance Policy | CCO | Section 13 + 18 | MEA03 |

## CRMF cascade (Session 5 build — re-anchored from v1)

| Policy ID | Title | Owner | RMiT clause | COBIT |
|---|---|---|---|---|
| [POL-04](POL-04-information-security-policy.md) | Information Security Policy (master under CRMF) | CISO | Section 5.2 (ISO 27001); Section 8, 9, 11 (RMiT) | APO13, EDM03, APO12 |
| [POL-05](POL-05-acceptable-use-policy.md) | Acceptable Use Policy | CISO | Section 10.53–10.57; Section 15 | APO01, DSS06 |
| [POL-06](POL-06-access-control-policy.md) | Access Control Policy | CISO | Section 10.53–10.57 | APO13, DSS05 |
| [POL-12](POL-12-cryptography-policy.md) | Cryptography Policy | CISO | Section 10.20–10.23 | APO13 |
| [POL-13](POL-13-incident-management-policy.md) | Incident Management Policy | CISO | Section 11.13; Section 11.1–11.20 | DSS02, DSS05 |
| [POL-18](POL-18-vulnerability-management-policy.md) | Vulnerability and Patch Management Policy | CISO | Section 10.17–10.19; Section 11.6, 11.7 | DSS05, APO13 |
| [POL-19](POL-19-supplier-security-policy.md) | Supplier and Third-Party Security Policy | CISO + Procurement | Section 10.46–10.49 + Section 14 | APO10, APO13 |

## Other framework cascades

Policies cascading from BCMF, TPRMF, CIMF, NCIIF, CloudRMF, DGF, AIGF — see those framework documents' Section 9 Implementation Requirements for the planned cascade. These will be built in subsequent sessions.

## Anatomy

Every policy uses the 10-section template at [`../_templates/policy-template.md`](../_templates/policy-template.md).

## Cross-links

- ↑ [Frameworks (Layer 2)](../01-frameworks/) — parent frameworks
- ↓ [Standards (Layer 4)](../03-standards/) — measurable requirements implementing these policies
- → [Document control](../07-document-control/) — version history
