# SOP-DG-02 — Data Quality Triage SOP

| | |
|---|---|
| **Document ID** | SOP-DG-02 | **Version** | 1.0 |
| **Owner / Approver** | Data Governance team (under CDO) |
| **Parent standard** | [STD-DG-01](../03-standards/STD-DG-01-data-quality-standard.md) | **Parent policy** | [POL-11](../02-policies/POL-11-data-classification-policy.md) |

## 1. Purpose
Triage and resolve data quality issues per severity SLAs in [STD-DG-01 §3.4](../03-standards/STD-DG-01-data-quality-standard.md).

## 2. Trigger
- Quality measurement breach of threshold per [STD-DG-01 §3.2](../03-standards/STD-DG-01-data-quality-standard.md)
- Business user report of suspected quality issue
- Downstream consumption failure
- Audit finding

## 3. Procedure

| # | Actor | Action | SLA |
|---|---|---|---|
| 1 | Data steward | Identify quality issue; record in REG-DQ Data Quality Register | At identification |
| 2 | Data steward | Classify severity per [STD-DG-01 §3.4](../03-standards/STD-DG-01-data-quality-standard.md) | ≤ 24h Critical; ≤ 5BD Medium |
| 3 | Data steward | Investigate root cause per [STD-DG-01 §3.5](../03-standards/STD-DG-01-data-quality-standard.md) (source / user / integration / definition / timing) | Per severity |
| 4 | Data steward + source-system owner | Develop remediation — typically source-side fix preferred over downstream cleansing | Per severity |
| 5 | Source-system owner | Implement source-side fix | Per severity remediation SLA |
| 6 | Data steward | Backfill / correct historical data where required | Per data class |
| 7 | Data steward | Verify remediation effective via quality re-measurement | Within 7 days of remediation |
| 8 | Data steward | Close in REG-DQ; lessons feed back into source-system change process | At verification |

## 4. Critical-severity escalation
Issues affecting Tier 0 service or regulatory reporting: immediate notification to CDO + business head; remediation within 7 days; daily progress updates until closed.

## 5. Pattern detection
Quarterly Data Governance team review of REG-DQ for systemic issues; recurring patterns elevated for source-system redesign or data-quality engineering investment.

## 6. Evidence
REG-DQ entries; root cause analyses; remediation evidence; re-measurement verification. Retained 7 years.

## 7. Document control
| Version | Date | Author | Approver | Change |
|---|---|---|---|---|
| 1.0 | [Effective] | Data Governance team | CDO | Initial |
