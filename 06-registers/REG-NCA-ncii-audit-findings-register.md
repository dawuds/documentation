# REG-NCA — NCII Audit Findings Register

| | |
|---|---|
| **Document ID** | REG-NCA | **Owner** | Internal Audit + CISO |
| **Cadence** | Per audit | **Parent framework** | [NCIIF](../01-frameworks/NCIIF.md) |
| **Parent standard** | [STD-NC-02](../03-standards/STD-NC-02-ncii-audit-standard.md) |

## Purpose
Authoritative record of NCII-scope audit findings from Internal Audit, external NCII audit (where mandated), and NACSA examination — with remediation status.

## Schema
| Field | Description |
|---|---|
| `nca_id` | `NCA-YYYY-NNN` |
| `audit_source` | Internal Audit / External NCII audit / NACSA examination |
| `audit_reference` | Engagement / report identifier |
| `audit_date` | |
| `finding_id` | Source-system finding ID |
| `finding_description` | Sanitised |
| `severity` | Per audit-source rating |
| `applicable_ncii_obligation` | NACSA Code / NCII directive reference |
| `owner_role` | Remediation owner |
| `cap_id` | Link to [REG-CAP](REG-CAP-corrective-action-register.md) |
| `target_remediation_date` | NACSA-specified or audit-agreed |
| `actual_remediation_date` | |
| `nacsa_notification_required` | bool |
| `nacsa_notification_status` | |
| `status` | Open / In remediation / Closed / Verified closed |

## Worked example
| nca_id | source | severity | applicable | target | status |
|---|---|---|---|---|---|
| NCA-2026-001 | Internal Audit FY2026 | Medium | NACSA CoP §X.Y — evidence enhancement | 2026-09-30 | In remediation |
| NCA-2026-002 | NACSA examination | High | NACSA CoP §X.Z — specific control gap | 2026-08-15 | In remediation; CAP-2026-0028 |
| NCA-2026-003 | Internal Audit FY2026 | Low | Code of Practice §X.A — documentation update | 2026-06-30 | Verified closed |

## Related documents
[STD-NC-02](../03-standards/STD-NC-02-ncii-audit-standard.md); [POL-23](../02-policies/POL-23-ncii-operational-policy.md); [REG-CAP](REG-CAP-corrective-action-register.md); [SOP-NC-02](../04-procedures/SOP-NC-02-nacsa-examination-response-sop.md)
