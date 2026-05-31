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
| `tpsp_id` | reference | **Mandatory** link to corresponding [REG-TPS](REG-TPS-third-party-service-provider-register.md) entry — every cloud service is also a third-party service provider relationship; dual-registration is enforced (see Section "Dual-entry rule" below) |
| `tier` | enum | Tier 0 / 1 / 2 / 3 per service criticality |
| `data_classification_processed` | enum | Highest data classification stored/processed |
| `data_residency_in_malaysia` | bool | Resident in Malaysia |
| `cross_border_basis` | text | If extra-Malaysia: PDPA Section 129 basis |
| `shared_responsibility_documented` | bool | Per POL-20 Section 4.2 |
| `landing_zone_compliant` | bool | CIS / bank baseline alignment |
| `cspm_coverage` | bool | Under CSPM monitoring |
| `cmk_used` | bool | Customer-managed keys (not provider-managed) per POL-20 Section 4.6 |
| `appendix_10_compliant` | enum | Yes / Partial (with documented departures per RMiT 10.51) / No |
| `appendix_10_departures` | text | If Partial — list and justifications |
| `exit_plan_documented` | bool | Per POL-20 Section 4.7 |
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

## Dual-entry rule with REG-TPS (TPRMF/CloudRMF seam)

Every cloud service entry in REG-CL **must** have a corresponding entry in [REG-TPS](REG-TPS-third-party-service-provider-register.md) — there is no such thing as a cloud relationship that is not also a third-party relationship. The bidirectional join is:

- **REG-CL.tpsp_id** ↔ **REG-TPS.tpsp_id** (canonical key)
- Cloud-specific attributes (service model, region, residency, CSPM, landing-zone compliance, App. 10 mapping) live in REG-CL.
- Generic TPSP-lifecycle attributes (due diligence, contractual security clauses, attestations, exit plan completeness, material outsourcing flag, BNM notification status, periodic reassessment cadence) live in REG-TPS.
- Either register can refresh first; both reflect the latest state within 5 working days of any material change.
- A REG-CL row with `tpsp_id = null` is a control defect raised in the next quarterly cloud reconciliation and reported to RMC.

The seam is operated jointly by **Head of Cloud** (REG-CL operating) and **Head of TPRM** (REG-TPS operating). Both report through [CRMF Section 11](../01-frameworks/CRMF.md) and [TPRMF Section 11](../01-frameworks/TPRMF.md).

## Maintenance

- New cloud service adoption gated by entry creation in **both** REG-CL and REG-TPS.
- CSPM critical findings trigger immediate posture review and entry update.
- Quarterly Head of Cloud reconciles register against actual cloud-resource inventory (AWS Config, Azure Resource Graph, GCP Asset Inventory) **and** cross-validates REG-CL ↔ REG-TPS join integrity.
- Annual Cloud TRAG-aligned full re-assessment.
- Material change of provider region, service model, or data residency triggers immediate update and CRO notification — and a corresponding REG-TPS update where the change is contractually material.

## Related documents

- **Parent framework:** [CloudRMF](../01-frameworks/CloudRMF.md)
- **Parent policy:** [POL-20](../02-policies/POL-20-cloud-acceptable-use-policy.md)
- **Related registers:** [REG-TPS](REG-TPS-third-party-service-provider-register.md) (for the third-party relationship lifecycle); [REG-CRA Cloud Risk Assessment Register](REG-CRA-cloud-risk-assessment-register.md); [REG-CEX Cloud Exit Plan Register](REG-CEX-cloud-exit-plan-register.md)
