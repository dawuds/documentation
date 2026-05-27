# REG-CEX — Cloud Exit Plan Register

| | |
|---|---|
| **Document ID** | REG-CEX | **Owner** | Head of Cloud + Procurement |
| **Cadence** | Annual review per cloud service | **Parent framework** | [CloudRMF](../01-frameworks/CloudRMF.md); [TPRMF](../01-frameworks/TPRMF.md) |
| **Source procedure** | [SOP-CL-03](../04-procedures/SOP-CL-03-cloud-exit-validation-sop.md) |

## Purpose
Authoritative record of cloud exit plans per cloud service — what GIBB would do to transition away from each provider / service.

## Schema
| Field | Description |
|---|---|
| `cex_id` | `CEX-NNN` |
| `cloud_service_id` | Link to [REG-CL](REG-CL-cloud-service-register.md) |
| `tpsp_id` | Link to [REG-TPS](REG-TPS-third-party-service-provider-register.md) |
| `service_tier` | Tier 0 / 1 / 2 |
| `alternate_options` | Provider, repatriation, alternate SaaS |
| `data_extraction_format` | Documented extraction method + format |
| `data_extraction_validated` | bool + date |
| `transition_timeline_estimate` | Days/weeks |
| `transition_cost_estimate` | MYR |
| `contractual_exit_assistance` | Per [STD-TP-02 §3.9](../03-standards/STD-TP-02-outsourcing-contractual-security-standard.md) |
| `last_validation_date` | |
| `last_validation_outcome` | Pass / Pass with findings / Fail |
| `next_validation_due` | Annual |
| `cro_signed_off` | date |
| `bnm_notified` | bool (material outsourcing) |
| `status` | Validated / Pending refresh / Issue identified |

## Worked example
| cex_id | service | tier | alternate | timeline | last_validation | status |
|---|---|---|---|---|---|---|
| CEX-001 | CL-0001 IaaS primary | 0 | CL-0002 (alternate provider) + on-prem partial | 6-9 months | 2026-04-15 (Pass) | Validated |
| CEX-002 | CL-0003 Customer IDP | 0 | Alternate IDP vendor under evaluation | 12 months | 2026-03-22 (Pass with findings — identity migration tooling needs build) | Pending refresh |
| CEX-003 | CL-0004 HRIS (Workday) | 2 | Alternate HRIS or insourcing | 9 months | 2026-02-10 (Pass) | Validated |
| CEX-004 | CL-0008 Logs analytics PaaS | 1 | Open-source ELK stack on private cloud | 4 months | 2026-05-01 (Pass) | Validated |

## Related documents
[POL-20 §4.7](../02-policies/POL-20-cloud-acceptable-use-policy.md); [SOP-CL-03](../04-procedures/SOP-CL-03-cloud-exit-validation-sop.md); [SOP-TP-03](../04-procedures/SOP-TP-03-tpsp-exit-sop.md); [REG-CL](REG-CL-cloud-service-register.md); [REG-OUT](REG-OUT-material-outsourcing-register.md)
