# REG-CDB — Customer Data Breach Register

| | |
|---|---|
| **Document ID** | REG-CDB | **Owner** | DPO (CCO co-owner for regulator coordination) |
| **Classification** | Internal — restricted | **Cadence** | Per event |
| **Parent framework** | [CIMF](../01-frameworks/CIMF.md); [CRMF](../01-frameworks/CRMF.md) |
| **Source procedure** | [SOP-CI-02](../04-procedures/SOP-CI-02-customer-data-breach-notification-sop.md) |

## Purpose
Authoritative record of all customer data breaches at GIBB, distinct from the broader incident register. Captures PDPA / MCIPD / BNM / NACSA notification status and customer-impact summary. Primary register reviewed by PDPA Commissioner inspections.

## Schema

| Field | Description |
|---|---|
| `cdb_id` | `CDB-YYYY-NNN` |
| `originating_incident_id` | Link to [REG-INC](REG-INC-incident-register.md) |
| `discovery_date` | When breach confirmed |
| `breach_type` | Confidentiality / Integrity / Availability |
| `customer_data_classes_affected` | Per [STD-CI-01](../03-standards/STD-CI-01-customer-data-classification-standard.md) |
| `affected_customer_count` | int (may be estimate at discovery) |
| `sensitive_personal_data` | bool (PDPA elevated treatment) |
| `shariah_confidential_affected` | bool |
| `root_cause` | text |
| `pdpa_threshold_met` | bool |
| `pdpa_notification_made` | bool + date if yes |
| `bnm_threshold_met` | bool |
| `bnm_notification_made` | bool + date if yes |
| `bnm_notification_within_4h` | bool (with source-chain caveat per POL-13) |
| `nacsa_threshold_met` | bool (if NCII-scope) |
| `nacsa_notification_made` | bool + date if yes |
| `customer_notification_made` | bool + date + channel + count notified |
| `customer_communication_owner` | role |
| `remediation_actions` | text (containment + preventive) |
| `pir_completed` | bool |
| `lessons` | text |
| `regulatory_outcome` | Open / Closed / Enforcement action |
| `status` | Open / Notification phase / Remediation phase / Closed |

## Worked example — first entries (sanitised)

| cdb_id | discovery | type | classes | count | sensitive | bnm_notif | customer_notif | status |
|---|---|---|---|---|---|---|---|---|
| CDB-2026-001 | 2026-02-12 | Confidentiality | Customer identifiers | 14 customers | No | Yes (2026-02-12, 3h after detection) | Yes (2026-02-15; email + letter; 14 customers) | Closed (PIR completed; root cause: misconfigured email DLP rule; rule corrected) |
| CDB-2026-002 | 2026-04-22 | Confidentiality | Authentication metadata (linked INC-2026-014 — phishing) | 2 customers (compromised credentials) | No (auth was hashed) | No (below BNM threshold) | Yes (2026-04-23; in-app secure message + phone outreach; 2 customers) | Closed (passwords forcibly reset; MFA re-enrolled; education delivered) |
| CDB-2026-003 | 2026-05-15 | Confidentiality | Sensitive personal data (health declarations in financing applications) | 87 customers | **Yes** | Yes (2026-05-15, 4h after detection; CCO confirmed) | Yes (2026-05-22 after legal review; mail + email; 87 customers) | Closed (PIR; root cause: report mis-delivery to wrong recipient via vendor portal; vendor process corrected) |

## Maintenance

- DPO creates entry on confirmation (not on suspicion).
- All notifications (regulator + customer) recorded with timestamps and evidence references.
- Quarterly DPO report to RMC summarising open breaches, trends, regulatory engagements.
- PDPA Commissioner inspection: this register is primary evidence.

## Related documents
[POL-CI-01](../02-policies/POL-CI-01-customer-data-protection-policy.md); [SOP-CI-02](../04-procedures/SOP-CI-02-customer-data-breach-notification-sop.md); [STD-CI-01](../03-standards/STD-CI-01-customer-data-classification-standard.md); [REG-INC](REG-INC-incident-register.md); [REG-NCN](REG-NCN-nacsa-notification-register.md); [REG-ROPA](REG-ROPA-records-of-processing-activity.md).
