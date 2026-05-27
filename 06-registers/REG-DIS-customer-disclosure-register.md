# REG-DIS — Customer Disclosure Register

| | |
|---|---|
| **Document ID** | REG-DIS | **Owner** | DPO + CCO |
| **Cadence** | Per disclosure event | **Parent framework** | [CIMF](../01-frameworks/CIMF.md) |
| **Implements** | BNM MCIPD permitted-disclosure logging |

## Purpose
Authoritative record of customer information disclosures by GIBB to third parties — under BNM MCIPD permitted-disclosure regime or other authorising legal basis. Primary register reviewed during BNM MCIPD examinations.

## Schema
| Field | Description |
|---|---|
| `dis_id` | `DIS-YYYY-NNN` |
| `disclosure_date` | |
| `disclosure_basis` | MCIPD permitted disclosure category / Court order / Subpoena / Regulator request / Customer consent / Statutory obligation |
| `requesting_party` | Law enforcement / Regulator / Court / Other authorised |
| `request_reference` | Order / subpoena / request reference |
| `data_categories_disclosed` | Per [STD-CI-01](../03-standards/STD-CI-01-customer-data-classification-standard.md) |
| `customers_affected_count` | |
| `customer_notified` | bool (where permitted by basis) |
| `customer_notification_date` | |
| `approval_authority` | DPO + CCO + General Counsel as required by basis |
| `evidence_link` | Order / subpoena / consent record |
| `disclosure_documentation` | Sanitised summary |
| `mcipd_basis_cite` | Specific MCIPD clause if applicable |
| `pdpa_basis_cite` | Specific PDPA clause if applicable |

## Worked example
| dis_id | date | basis | requesting | customers | notified | status |
|---|---|---|---|---|---|---|
| DIS-2026-001 | 2026-02-20 | Court order — civil litigation | High Court of Malaya | 1 | No (court order prohibits notification) | Closed |
| DIS-2026-002 | 2026-03-15 | BNM regulatory request | BNM examination team | 47 (aggregate analytical, not individual records) | n/a | Closed |
| DIS-2026-003 | 2026-04-22 | AMLA STR — suspicious transaction report | FIED Malaysia | 2 | No (AMLA prohibits tipping-off) | Closed |
| DIS-2026-004 | 2026-05-10 | Customer consent — disclosure to credit reporting agency | CTOS | 1 (the consenting customer) | Yes (consent itself is the notification) | Closed |
| DIS-2026-005 | 2026-05-25 | Police investigation — Computer Crimes Act | Royal Malaysia Police | 1 | No (active investigation) | Closed |

## Maintenance
- Every disclosure logged at time of disclosure (not retrospectively)
- DPO + CCO joint approval on creation
- Quarterly DPO summary to RMC
- BNM MCIPD examination: this register is primary evidence

## Related documents
[POL-CI-01 §4.3](../02-policies/POL-CI-01-customer-data-protection-policy.md); [STD-CI-01](../03-standards/STD-CI-01-customer-data-classification-standard.md); BNM MCIPD; PDPA 2010
