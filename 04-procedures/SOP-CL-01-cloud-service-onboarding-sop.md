# SOP-CL-01 — Cloud Service Onboarding SOP

| | |
|---|---|
| **Document ID** | SOP-CL-01 | **Version** | 1.0 |
| **Owner / Approver** | Head of Cloud Engineering + CISO |
| **Parent standard** | [STD-CL-01](../03-standards/STD-CL-01-cloud-security-standard.md) | **Parent policy** | [POL-20](../02-policies/POL-20-cloud-acceptable-use-policy.md) |

## 1. Purpose
Operationalise onboarding of a new cloud service into GIBB consumption — risk assessment, landing zone, security, exit-readiness.

## 2. Trigger
Approved business case for new cloud service consumption.

## 3. Procedure

| # | Actor | Action | Output |
|---|---|---|---|
| 1 | Business requestor | Submit cloud service request — provider, service model, data class, residency | Request |
| 2 | Head of Cloud | Cloud risk assessment per RMiT 10.50 + [STD-CL-01](../03-standards/STD-CL-01-cloud-security-standard.md) | Risk assessment in [REG-CL](../06-registers/REG-CL-cloud-service-register.md) |
| 3 | CISO | Security review — shared-responsibility, IAM model, encryption posture | Security review |
| 4 | DPO | Data residency review per PDPA Section 129 if cross-border | Residency review |
| 5 | CRO | Approve for Tier 0/1; Head of Cloud approves Tier 2/3 | Approval |
| 6 | Procurement | TPSP onboarding (parallel) per [SOP-TP-01](SOP-TP-01-tpsp-onboarding-sop.md) | TPSP entry |
| 7 | Head of Cloud | Provision landing zone aligned to CIS Foundations + bank overlay per [STD-CL-01 §3.1](../03-standards/STD-CL-01-cloud-security-standard.md) | Landing zone operational |
| 8 | Head of Cloud | Configure identity federation per [STD-CL-01 §3.2](../03-standards/STD-CL-01-cloud-security-standard.md) | Federation operational |
| 9 | CISO + Head of Cloud | Enable CSPM coverage; baseline detection rules | CSPM operational |
| 10 | Head of Cloud + CISO | Document exit plan per [POL-20 §4.7](../02-policies/POL-20-cloud-acceptable-use-policy.md); record in [REG-CL](../06-registers/REG-CL-cloud-service-register.md) and REG-CEX (future) | Exit plan recorded |
| 11 | Head of Cloud | Update [REG-CL](../06-registers/REG-CL-cloud-service-register.md) entry to Active | Active entry |

## 4. Exception handling
Material RMiT Appendix 10 departure: RMC approval required per [POL-20 §4.8](../02-policies/POL-20-cloud-acceptable-use-policy.md); justified in REG-CL `appendix_10_departures`.

## 5. Evidence
Risk assessment; security review; residency review; CRO approval; landing zone IaC; CSPM configuration; exit plan; REG-CL entry. Retained per [STD-TP-01 §3.3](../03-standards/STD-TP-01-tpsp-due-diligence-standard.md).

## 6. Document control
| Version | Date | Author | Approver | Change |
|---|---|---|---|---|
| 1.0 | [Effective] | Head of Cloud + CISO | CISO | Initial |
