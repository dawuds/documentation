# REG-DQ — Data Quality Register

| | |
|---|---|
| **Document ID** | REG-DQ | **Owner** | Data Governance team (under CDO) |
| **Cadence** | Continuous | **Parent framework** | [DGF](../01-frameworks/DGF.md) |
| **Source procedure** | [SOP-DG-02](../04-procedures/SOP-DG-02-data-quality-triage-sop.md) |

## Purpose
Record data quality issues, root causes, and remediations per [STD-DG-01](../03-standards/STD-DG-01-data-quality-standard.md).

## Schema
| Field | Description |
|---|---|
| `dq_id` | `DQ-YYYY-NNNN` |
| `data_asset_id` | Link to [REG-DA](REG-DA-data-asset-register.md) |
| `issue_description` | What is wrong |
| `dimension` | Accuracy / Completeness / Consistency / Timeliness / Validity / Uniqueness |
| `severity` | Critical / High / Medium / Low per [STD-DG-01 §3.4](../03-standards/STD-DG-01-data-quality-standard.md) |
| `discovery_date` | |
| `discovery_source` | Automated measurement / User report / Audit / Downstream failure |
| `root_cause_category` | Source / User input / Integration / Definition / Timing |
| `affected_records_count` | Estimated / measured |
| `affected_consuming_systems` | |
| `remediation_action` | |
| `remediation_owner` | |
| `target_remediation_date` | Per severity SLA |
| `actual_remediation_date` | |
| `re_measurement_pass` | bool |
| `status` | Open / In remediation / Closed |

## Worked example
| dq_id | asset | dimension | severity | root_cause | status |
|---|---|---|---|---|---|
| DQ-2026-001 | DA-0001 Customer master | Completeness | Medium | Source — customer onboarding allows null address | In remediation (source-system fix Q3) |
| DQ-2026-002 | DA-0010 Country code reference | Consistency | Low | Definition — three sources of country code, inconsistent | Closed (single master adopted) |
| DQ-2026-003 | DA-0006 AML/KYC | Accuracy | High | Integration — sanctions list refresh lag 48h | In remediation (target real-time refresh by Q4) |

## Related documents
[STD-DG-01](../03-standards/STD-DG-01-data-quality-standard.md); [SOP-DG-02](../04-procedures/SOP-DG-02-data-quality-triage-sop.md); [REG-DA](REG-DA-data-asset-register.md); [POL-11](../02-policies/POL-11-data-classification-policy.md)
