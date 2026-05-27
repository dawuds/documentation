# 01 — Frameworks (Layer 2)

The nine bank-authored framework documents of the GIBB IT governance architecture. Each is Board RMC-approved, annually reviewed, citation-precise, and binding within its scope.

← [Repo home](../README.md) · [Architecture](../00-architecture/) ↑

---

## The nine frameworks

| # | Framework | Acronym | Owner | RMiT clause | COBIT objective(s) |
|---|---|---|---|---|---|
| 1 | [Technology Risk Management Framework](TRMF.md) | **TRMF** | CRO + Head of Tech Risk | Section 9.2 | EDM03, APO12, APO01 |
| 2 | Cyber Risk Management Framework | **CRMF** | CISO | Section 11.2, 11.3 | APO13, DSS05 |
| 3 | Business Continuity Management Framework | **BCMF** | COO | 10.24–10.45 | DSS04 |
| 4 | Third Party Risk Management Framework | **TPRMF** | Head of Procurement + CRO | 10.46–10.49 + Section 14 | APO10 |
| 5 | Customer Information Management Framework | **CIMF** | DPO + CCO | + MCIPD + PDPA | APO14 |
| 6 | NCII Compliance Framework | **NCIIF** | CISO + CCO | + Cyber Security Act 2024 | MEA03 |
| 7 | Cloud Risk Management Framework | **CloudRMF** | Head of Cloud + CISO | 10.50–10.52 + App. 10 | APO10 + APO13 |
| 8 | Data Governance Framework | **DGF** | Chief Data Officer | (industry practice) | APO14 |
| 9 | AI Governance Framework | **AIGF** | CDO + CISO | (NIST AI RMF + EU AI Act) | EDM03 + APO12 + APO14 |

Frameworks 2–9 will be drafted in subsequent sessions. TRMF (Framework 1) is drafted as the canonical worked example.

---

## Anatomy

Every framework follows the same 17-section spec at [`../_templates/framework-template.md`](../_templates/framework-template.md): Foreword · Purpose · Scope · Definitions · Governance · Framework principles · Framework structure · Lifecycle / operating model · Implementation requirements · Performance measurement · Reporting and escalation · Exceptions · Independent review · Related frameworks · References · Document control.

Length target: 600–1,200 lines per framework. RMiT-mandated frameworks (TRMF, CRMF) toward the upper bound.

---

## Seams

The three framework seams (TRMF/CRMF, DGF/CIMF, TPRMF/CloudRMF) are explicitly resolved per [`../_context/seams.md`](../_context/seams.md). Each affected framework states the seam in its Section 14 (Related frameworks).

---

## Cross-links

- [`../00-architecture/`](../00-architecture/) — the layered model these frameworks sit within
- [`../02-policies/`](../02-policies/) — Layer 3 policies that cascade from these frameworks (drafted as part of the TRMF cascade in a later session)
- [`../_context/`](../_context/) — design decisions binding these frameworks
- [`../_templates/`](../_templates/) — the framework template
