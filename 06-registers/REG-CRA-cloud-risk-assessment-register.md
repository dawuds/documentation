# REG-CRA — Cloud Risk Assessment Register

| | |
|---|---|
| **Document ID** | REG-CRA | **Owner** | Head of Cloud + CISO |
| **Cadence** | Per assessment | **Parent framework** | [CloudRMF](../01-frameworks/CloudRMF.md) |

## Purpose
Record per-cloud-service risk assessments per RMiT 10.50 — including Appendix 10 Risk and Control Mapping Matrix coverage.

## Schema
| Field | Description |
|---|---|
| `cra_id` | `CRA-NNN` |
| `cloud_service_id` | Link to [REG-CL](REG-CL-cloud-service-register.md) |
| `assessment_date` | |
| `assessment_trigger` | New service / Material change / Annual refresh |
| `app10_coverage` | Per RMiT Appendix 10 risk categories — coverage assessment |
| `key_risks_identified` | text |
| `controls_in_place` | text |
| `residual_risk_rating` | Per TRMF materiality matrix |
| `appendix_10_departures` | If any — justified per [POL-20 Section 4.8](../02-policies/POL-20-cloud-acceptable-use-policy.md) |
| `cro_concurrence` | date |
| `rmc_approval` | If material residual or App. 10 departure |
| `next_review` | |

## Worked example
| cra_id | service | assessment | residual | departures | status |
|---|---|---|---|---|---|
| CRA-2026-001 | CL-0001 IaaS primary | 2026-02-10 | Moderate (treated) | None | Active |
| CRA-2026-002 | CL-0003 Customer IDP | 2026-02-12 | Moderate (treated) | Key residency departure (justified — vendor architecture) | Active; RMC noted |
| CRA-2026-003 | CL-0007 EDR SaaS | 2026-02-25 | Low (treated) | None | Active |

## Related documents
[POL-20](../02-policies/POL-20-cloud-acceptable-use-policy.md); [STD-CL-01](../03-standards/STD-CL-01-cloud-security-standard.md); [REG-CL](REG-CL-cloud-service-register.md); [REG-CEX](REG-CEX-cloud-exit-plan-register.md); [REG-TR](REG-TR-technology-risk-register.md)
