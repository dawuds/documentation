# SOP-CL-03 — Cloud Exit Validation SOP

| | |
|---|---|
| **Document ID** | SOP-CL-03 | **Version** | 1.0 |
| **Owner / Approver** | Head of Cloud + Head of Procurement |
| **Parent policy** | [POL-20 Section 4.7](../02-policies/POL-20-cloud-acceptable-use-policy.md) | **Parent framework** | [CloudRMF](../01-frameworks/CloudRMF.md); [TPRMF](../01-frameworks/TPRMF.md) |

## 1. Purpose
Periodically validate that GIBB's cloud exit plans are executable — not just documented. Discharges BNM Outsourcing PD exit-readiness expectations.

## 2. Trigger
Annual exit-readiness validation per cloud service. Plus on material cloud architecture change.

## 3. Procedure — exit-readiness validation

| # | Actor | Action | Output |
|---|---|---|---|
| 1 | Head of Cloud | Select cloud service for validation (rotating annual schedule) | Selection |
| 2 | Head of Cloud + workload owner | Review documented exit plan (in REG-CEX Cloud Exit Plan Register) | Plan review |
| 3 | Head of Cloud | Identify alternate options (other cloud provider, repatriation, alternate SaaS) | Options assessed |
| 4 | Head of Cloud | Validate data-portability — can data be extracted in usable format? | Portability validated |
| 5 | Head of Cloud | Estimate transition timeline + cost | Estimate |
| 6 | Head of Cloud | Document or update exit plan in REG-CEX | Updated plan |
| 7 | Head of Cloud + Procurement | Validate contractual exit-assistance provisions | Contract validated |
| 8 | Head of Cloud | Update [REG-CL](../06-registers/REG-CL-cloud-service-register.md) `exit_plan_documented` and reference | REG-CL updated |
| 9 | CRO + CCO | Annual exit-readiness report to RMC | Report |

## 4. Procedure — actual exit
On exit decision: per [SOP-TP-03 TPSP Exit](SOP-TP-03-tpsp-exit-sop.md) with cloud-specific overlay:
- Data extraction in agreed format
- Identity de-federation
- Network disconnection
- Final billing closure
- CSPM coverage transitioned to alternate

## 5. Evidence
Exit plan; validation record; CRO + CCO sign-off; REG-CEX entry. Retained 7 years.

## 6. Document control
| Version | Date | Author | Approver | Change |
|---|---|---|---|---|
| 1.0 | [Effective] | Head of Cloud | Head of Cloud + Procurement | Initial |
