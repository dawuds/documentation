# REG-CL — Cloud Service Register

| | |
|---|---|
| **Document ID** | REG-CL |
| **Layer** | Register (Layer 6) |
| **Owner** | Head of Cloud Engineering (CISO co-owner for security posture) |
| **Classification** | Internal |
| **Cadence** | Continuous |
| **Parent framework(s)** | [CloudRMF](../01-frameworks/CloudRMF.md) |
| **Parent policy** | [POL-20](../02-policies/POL-20-cloud-acceptable-use-policy.md) |

---

## Purpose

The authoritative inventory of GIBB's cloud service consumption — services adopted, shared-responsibility allocation, residency, exit-readiness, posture status. Primary input to BNM examinations on cloud per Cloud TRAG and RMiT 10.50–10.52.

## Schema

| Field | Type | Description |
|---|---|---|
| `cl_id` | string | `CL-NNNN` |
| `service_name` | string | Cloud service identifier |
| `provider` | string | Cloud provider entity |
| `service_model` | enum | IaaS / PaaS / SaaS / FaaS |
| `provider_region` | string | Provider region(s) used |
| `tpsp_id` | reference | Link to REG-TPS entry |
| `tier` | enum | Tier 0 / 1 / 2 / 3 per service criticality |
| `data_classification_processed` | enum | Highest data classification stored/processed |
| `data_residency_in_malaysia` | bool | Resident in Malaysia |
| `cross_border_basis` | text | If extra-Malaysia: PDPA Section 129 basis |
| `shared_responsibility_documented` | bool | Per POL-20 §4.2 |
| `landing_zone_compliant` | bool | CIS / bank baseline alignment |
| `cspm_coverage` | bool | Under CSPM monitoring |
| `cmk_used` | bool | Customer-managed keys (not provider-managed) per POL-20 §4.6 |
| `appendix_10_compliant` | enum | Yes / Partial (with documented departures per RMiT 10.51) / No |
| `appendix_10_departures` | text | If Partial — list and justifications |
| `exit_plan_documented` | bool | Per POL-20 §4.7 |
| `last_risk_assessment` | date | Per RMiT 10.50 |
| `last_posture_review` | date | CSPM consolidated review |
| `material_for_bnm` | bool | Material outsourcing notification to BNM |
| `status` | enum | Approved / Onboarding / Active / Notice / Decommissioning / Decommissioned |

## Worked example — first entries (illustrative)

| cl_id | service | provider | model | tier | data | residency | shared_resp | exit_plan | app10 | status |
|---|---|---|---|---|---|---|---|---|---|---|
| CL-0001 | Production IaaS — region Malaysia | Cloud Provider A | IaaS | 0 | Confidential | Yes (MY-region) | Yes | Yes | Yes | Active |
| CL-0002 | Disaster Recovery IaaS — region Singapore | Cloud Provider A | IaaS | 0 | Confidential | No (SG; cross-border per PDPA SCC) | Yes | Yes | Yes | Active |
| CL-0003 | Customer Identity SaaS (IDP) | Identity Vendor | SaaS | 0 | Authentication | No (regional) | Yes | Yes | Partial — departure on key residency justified | Active |
| CL-0004 | HR SaaS (Workday) | HR Vendor | SaaS | 2 | Sensitive (HR) | No (US-region) | Yes | Yes | Yes | Active |
| CL-0005 | Email security SaaS | Email security vendor | SaaS | 1 | Internal | No (regional) | Yes | Yes | Yes | Active |
| CL-0006 | Office productivity SaaS | Office vendor | SaaS | 2 | Internal | Configurable; configured to MY-region | Yes | Yes | Yes | Active |
| CL-0007 | EDR SaaS | EDR vendor | SaaS | 1 | Behavioural (endpoint telemetry) | No (regional) | Yes | Yes | Yes | Active |
| CL-0008 | Application logs analytics PaaS | Cloud Provider A | PaaS | 1 | Behavioural; Internal | Yes (MY) | Yes | Yes | Yes | Active |
| CL-0009 | AI/ML training PaaS — sandbox | Cloud Provider A | PaaS | 2 | De-identified training data (per DGF + AIGF) | Yes (MY) | Yes | Yes | Yes | Active |

> Real entries carry full architecture diagram references, security control attestations, ongoing CSPM finding counts, named contacts.

## Maintenance

- New cloud service adoption gated by entry creation.
- CSPM critical findings trigger immediate posture review and entry update.
- Quarterly Head of Cloud reconciles register against actual cloud-resource inventory (AWS Config, Azure Resource Graph, GCP Asset Inventory).
- Annual Cloud TRAG-aligned full re-assessment.
- Material change of provider region, service model, or data residency triggers immediate update and CRO notification.

## Related documents

- **Parent framework:** [CloudRMF](../01-frameworks/CloudRMF.md)
- **Parent policy:** [POL-20](../02-policies/POL-20-cloud-acceptable-use-policy.md)
- **Related registers:** [REG-TPS](REG-TPS-third-party-service-provider-register.md) (for the third-party relationship lifecycle); REG-CRA Cloud Risk Assessment Register (future); REG-CEX Cloud Exit Plan Register (future)
