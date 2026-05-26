> ## ARCHIVED — SUPERSEDED
>
> **Document:** POL-13 Vulnerability Management Policy
> **Archived version:** 0.9 (pre-Effective draft preserved for traceability)
> **Status:** Superseded
> **Effective period:** Never went Effective — superseded during the initial drafting cycle
> **Superseded by:** [POL-13 v1.0](../../01-policies/13-vulnerability-management-policy.md)
> **Reason:** Initial draft used CVSS v3.1 as the sole scoring basis. RMC review required addition of EPSS-informed prioritisation for internet-facing systems before approval. Draft v1.0 was issued addressing the comment.
> **Approved retirement by:** ISMS Manager
> **Archived on:** 2026-01-12
> **Archived by:** ISMS Manager
>
> This document is retained for audit and forensic reference only. It is **not** authoritative.
> Do not rely on this document for current obligations — consult the current effective version.

---

# Vulnerability Management Policy — DRAFT v0.9 (illustrative archive example)

This is a worked example of what an archived document looks like once superseded. The content below is intentionally truncated — the purpose is to show the **supersession block above**, not to illustrate the policy itself.

## 1. Purpose

To define the requirements for identifying, assessing, prioritising, and remediating technical vulnerabilities in information systems owned by General Bank.

## 4. Policy statements

### 4.1 Vulnerability scanning

- **4.1.1** All internet-facing systems shall be scanned for vulnerabilities at least weekly. *(Implements ISO/IEC 27002:2022 control 8.8.)*
- **4.1.2** All internal systems shall be scanned for vulnerabilities at least monthly.

### 4.2 Remediation timelines

| CVSS v3.1 score | Remediation timeline |
|---|---|
| Critical (9.0–10.0) | 7 days |
| High (7.0–8.9) | 30 days |
| Medium (4.0–6.9) | 90 days |
| Low (0.1–3.9) | Next maintenance window |

*[Remainder of draft truncated — see successor v1.0 for the approved policy, which retains CVSS-based timelines and adds EPSS-informed prioritisation for internet-facing systems.]*

---

## Document control (as archived)

| Version | Date | Author | Reviewer | Approver | Change summary |
|---|---|---|---|---|---|
| 0.9 | 2026-01-08 | CISO | Technology Risk | Pending RMC | First-pass draft using CVSS v3.1 alone |
| — | 2026-01-12 | — | — | — | Superseded by v1.0 before going Effective; reason noted above |
