# REG-DSR — Data Subject Request Register

| | |
|---|---|
| **Document ID** | REG-DSR | **Owner** | DPO |
| **Classification** | Internal | **Cadence** | Continuous |
| **Parent framework** | [CIMF](../01-frameworks/CIMF.md) |
| **Implements** | PDPA Section 30–37 (data subject rights) |

## Purpose
Authoritative record of customer data subject requests under PDPA — access, correction, withdrawal of consent — and GIBB response. Primary register reviewed by PDPA Commissioner.

## Schema

| Field | Description |
|---|---|
| `dsr_id` | `DSR-YYYY-NNN` |
| `request_type` | Access / Correction / Consent withdrawal / Other |
| `received_date` | |
| `received_channel` | Branch / Online / Email / Letter |
| `customer_id` | Hashed reference (PII-minimised) |
| `customer_verified` | bool — identity-verification completed |
| `request_summary` | Sanitised description |
| `triage_status` | Initial review / In progress / Closed |
| `assigned_to_role` | DPO / DPO delegate |
| `statutory_deadline` | date (per PDPA timing — typically 21 days for access) |
| `response_date` | |
| `sla_met` | bool |
| `outcome` | Granted in full / Granted in part / Refused (with statutory basis) |
| `refusal_basis` | If refused — statutory reason |
| `customer_satisfaction` | Optional follow-up indicator |
| `appeals` | Any appeal recorded |
| `consent_changes_made` | If consent withdrawal — confirmation of system updates |
| `status` | Open / Closed / Appealed |

## Worked example — first entries (sanitised)

| dsr_id | type | received | verified | sla_target | response | sla_met | outcome | status |
|---|---|---|---|---|---|---|---|---|
| DSR-2026-001 | Access | 2026-03-15 | 2026-03-16 | 2026-04-05 (21 days) | 2026-03-28 | Yes | Granted in full | Closed |
| DSR-2026-002 | Correction | 2026-03-22 | 2026-03-22 | 2026-04-12 | 2026-03-29 | Yes | Granted (address record corrected; downstream systems updated) | Closed |
| DSR-2026-003 | Consent withdrawal | 2026-04-02 | 2026-04-02 | 2026-04-23 | 2026-04-04 | Yes | Granted (marketing consent withdrawn across channels) | Closed |
| DSR-2026-004 | Access | 2026-04-18 | 2026-04-19 | 2026-05-09 | 2026-05-08 | Yes | Granted in part (transactional data > 7 years redacted per retention) | Closed |
| DSR-2026-005 | Access (complex — combined with dispute) | 2026-05-02 | 2026-05-05 | 2026-05-23 | 2026-05-22 | Yes | Granted in full | Closed |

## Maintenance

- DPO logs every request received via any channel.
- SLA monitoring: 7-day pre-deadline alert.
- Quarterly DPO report to RMC: volume, SLA, refusal rate, trend.
- PDPA Commissioner inspection: this register is examined.

## Related documents
[POL-CI-01](../02-policies/POL-CI-01-customer-data-protection-policy.md); [REG-ROPA](REG-ROPA-records-of-processing-activity.md); SOP-CI-01 DSAR SOP (future).
