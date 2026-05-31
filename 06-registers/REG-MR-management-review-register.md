# Management Review Register

| | |
|---|---|
| **Document ID** | REG-MR |
| **Layer** | Register |
| **Owner** | CISO (ISMS); COO (BCMS); CDO (AIMS) — joint for combined reviews |
| **Cadence** | At least annually for ISMS, BCMS, AIMS; on material change to context, risk, or performance |
| **Implements** | ISO/IEC 27001:2022 Clause 9.3 (Management Review) — inputs 9.3.2 a–g; outputs 9.3.3 a–c; ISO/IEC 22301:2019 Clause 9.3; ISO/IEC 42001:2023 Clause 9.3; BNM RMiT (28 Nov 2025) Section 8 (Governance — Board and Senior Management oversight); Section 9.2(k) (Performance monitoring) |
| **Source procedure** | [POL-04 Information Security Policy](../02-policies/POL-04-information-security-policy.md) Section 4.3; CRMF Section 11 (Reporting); BCMF Section 11; AIGF Section 11 |
| **Parent framework(s)** | [CRMF](../01-frameworks/CRMF.md) (primary); [BCMF](../01-frameworks/BCMF.md); [AIGF](../01-frameworks/AIGF.md) |
| **COBIT objective(s)** | EDM01 Ensured Governance Framework Setting and Maintenance; EDM05 Ensured Stakeholder Engagement; MEA01 Managed Performance and Conformance Monitoring; MEA04 Managed Assurance |

---

## Purpose

The **mandatory record** of Management Review meetings required by ISO 27001 Clause 9.3, ISO 22301 Clause 9.3, and ISO 42001 Clause 9.3. The Management Review is the regular forum at which top management reviews each management system's continuing suitability, adequacy, and effectiveness, and decides on improvements and resource allocation.

This is one of the **first three documents** an ISO 27001 certifier asks for (alongside the Statement of Applicability and the Information Security Risk Treatment Plan). Without operating evidence here, the ISMS / BCMS / AIMS certification fails on Clause 9.3.

GIBB conducts an integrated Management Review covering ISMS, BCMS, and (from 2026) AIMS to avoid fragmentation. The review is held in the RMC quarterly cycle, with the full Clause 9.3 agenda annually and a focused subset quarterly.

## Schema

| Field | Type | Description |
|---|---|---|
| `review_id` | string | `MR-YYYY-NN` (year + sequence) |
| `scope` | enum (multi) | `ISMS` / `BCMS` / `AIMS` / `Combined` |
| `meeting_date` | date | When the review was held |
| `chair` | role | RMC Chair (annual) or CRO (quarterly) |
| `attendees` | array | Roles present; quorum status |
| `inputs_status_prev_actions` | text | **9.3.2 a** — status of actions from previous reviews |
| `inputs_changes_context` | text | **9.3.2 b** — changes in external and internal issues relevant to the ISMS |
| `inputs_interested_parties` | text | **9.3.2 c** — changes in needs and expectations of interested parties (regulators, customers, Shariah Committee, NACSA) |
| `inputs_performance_evaluation` | text | **9.3.2 d** — feedback on ISMS performance: NC and corrective actions, monitoring and measurement results, audit results, fulfilment of objectives |
| `inputs_risk_assessment_treatment` | text | **9.3.2 e** — results of risk assessment and status of the risk treatment plan |
| `inputs_opportunities` | text | **9.3.2 f** — opportunities for continual improvement |
| `inputs_resources` | text | **9.3.2 g** — adequacy of resources (RMC commentary on staffing, budget, tooling) |
| `output_changes_isms` | text | **9.3.3 a** — decisions on changes to the management system |
| `output_improvements` | text | **9.3.3 b** — decisions on opportunities for improvement |
| `output_resources` | text | **9.3.3 c** — decisions on resource needs |
| `actions` | array | Each: id, owner, due date, status, linked to [REG-CAP](REG-CAP-corrective-action-register.md) |
| `minutes_link` | reference | Authoritative minutes location (Board secretariat) |
| `next_review` | date | When the next review is due |

## Worked example — first entries (illustrative)

| review_id | scope | date | chair | quorum | key outputs |
|---|---|---|---|---|---|
| MR-2026-01 | ISMS + BCMS + AIMS | 2026-02-12 | RMC Chair | Yes | Annual review. Resourcing decision: +2 FTE SOC by 30 Jun. AIMS scope ratified for AI Governance Framework v1.0. SoA reaffirmed; one control re-classified Y→N (5.36 deprecated for shared infra). Corrective: 4 outstanding from MR-2025-04 — all closed. Next annual: 2027-02-11. |
| MR-2026-02 | ISMS (quarterly focus on incidents + objectives) | 2026-05-14 | CRO | Yes | Quarterly review. SOC SLA met at 96% — at target. Two SEV-2 PIRs reviewed; corrective actions tracked. Objectives: 7/8 on track; phishing-resistant MFA rollout behind schedule — resourcing intervention agreed. |

## Maintenance

- The annual full review must cover **all** ISO Clause 9.3.2 inputs and produce **all** Clause 9.3.3 outputs documented above. Quarterly reviews may scope-narrow but must close out actions from prior reviews.
- Minutes are the authoritative document of record; this register is the **evidence index**.
- Every action arising from a Management Review is mirrored to [REG-CAP](REG-CAP-corrective-action-register.md) for tracking to closure.
- The CISO presents performance evaluation data (9.3.2 d) drawing from [REG-INC](REG-INC-incident-register.md), [REG-VUL](REG-VUL-vulnerability-register.md), [REG-PAR](REG-PAR-privileged-access-review-register.md), [REG-OBJ](REG-OBJ-information-security-objectives-register.md), audit findings ([REG-NCA](REG-NCA-ncii-audit-findings-register.md)).
- Failure to hold the annual Management Review is itself an ISO 27001 nonconformity per Clause 9.3 and shall be raised as a finding in [REG-NC](REG-NC-nacsa-directive-tracker.md) (and ISMS internal-audit findings).

## Related documents

- **Parent policy:** [POL-04 Information Security Policy](../02-policies/POL-04-information-security-policy.md) Section 4.3
- **Source frameworks:** [CRMF](../01-frameworks/CRMF.md) Section 11; [BCMF](../01-frameworks/BCMF.md) Section 11; [AIGF](../01-frameworks/AIGF.md) Section 11
- **Feeds-from:** [REG-OBJ](REG-OBJ-information-security-objectives-register.md); [REG-SOA](REG-SOA-statement-of-applicability.md); [REG-TR](REG-TR-technology-risk-register.md); [REG-INC](REG-INC-incident-register.md); [REG-VUL](REG-VUL-vulnerability-register.md); [REG-NCA](REG-NCA-ncii-audit-findings-register.md); [REG-EXC](REG-EXC-exception-register.md)
- **Feeds-to:** [REG-CAP](REG-CAP-corrective-action-register.md); Board / RMC reporting

## Document control

| Version | Date | Author | Reviewer | Approver | Change summary |
|---|---|---|---|---|---|
| 1.0 | 2026-05-30 | CISO | CRO | Risk Management Committee | Initial version. Closes ISO 27001 / 22301 / 42001 Clause 9.3 evidence gap identified in v2 multi-agent review (GRC + IT Governance + Board agreed: POL-04 commits to "Management Review at least annually" but no document exists). |
