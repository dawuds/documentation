# REG-TPI — TPSP Incident Register

| | |
|---|---|
| **Document ID** | REG-TPI | **Owner** | CISO + CRO |
| **Cadence** | Per incident | **Parent framework** | [TPRMF](../01-frameworks/TPRMF.md); [CRMF](../01-frameworks/CRMF.md) |

## Purpose
Authoritative record of incidents originating at TPSPs that materially affect GIBB — distinct from [REG-INC](REG-INC-incident-register.md) which covers GIBB-side incidents.

## Schema
| Field | Description |
|---|---|
| `tpi_id` | `TPI-YYYY-NNN` |
| `tpsp_id` | Link to [REG-TPS](REG-TPS-third-party-service-provider-register.md) |
| `tpsp_notification_date` | Per [STD-TP-03 Section 3.2](../03-standards/STD-TP-03-tpsp-continuous-monitoring-standard.md) 24h SLA |
| `tpsp_notification_within_24h` | bool |
| `tpsp_description` | TPSP-provided incident description |
| `gibb_assessment_severity` | Per [STD-IR-01](../03-standards/STD-IR-01-incident-classification-and-severity-standard.md) |
| `gibb_originating_incident_id` | Link to [REG-INC](REG-INC-incident-register.md) if material to GIBB |
| `gibb_services_affected` | Multi link to [REG-BIA](REG-BIA-business-impact-analysis-register.md) |
| `bnm_notification_required` | bool |
| `nacsa_notification_required` | bool (if NCII-scope) |
| `tpsp_remediation_action` | |
| `tpsp_remediation_completion` | date |
| `gibb_compensating_action` | What GIBB did during TPSP-side issue |
| `tpsp_reassessment_triggered` | bool — material adverse change |
| `status` | Open / Remediated / Closed |

## Worked example
| tpi_id | tpsp | severity | bnm_notif | tpsp_remediated | reassess | status |
|---|---|---|---|---|---|---|
| TPI-2026-001 | TPS-0001 Cloud Provider A — regional service disruption | SEV-3 (no GIBB data impact; service degradation) | No (below material) | Yes (2026-04-22) | No | Closed |
| TPI-2026-002 | TPS-0005 CDN/WAF — DDoS-related saturation | SEV-3 (degraded GIBB defence; managed) | No | Yes (2026-05-10) | No | Closed |
| TPI-2026-003 | TPS-0008 IDP — minor authentication delay | SEV-4 | No | Yes (2026-03-15) | No | Closed |

## Related documents
[STD-TP-03](../03-standards/STD-TP-03-tpsp-continuous-monitoring-standard.md); [POL-19](../02-policies/POL-19-supplier-security-policy.md); [REG-TPS](REG-TPS-third-party-service-provider-register.md); [REG-INC](REG-INC-incident-register.md)
