# POL-20 — Cloud Acceptable Use Policy

| | |
|---|---|
| **Document ID** | POL-20 |
| **Layer** | Policy (Tier 1) |
| **Version** | 1.0 |
| **Owner** | Head of Cloud Engineering + CISO (joint) |
| **Approver** | Risk Management Committee |
| **Classification** | Internal |
| **Effective** | [Effective] |
| **Next review** | Annual + on cloud provider or BNM Cloud TRAG change |
| **Parent framework(s)** | [CloudRMF](../01-frameworks/CloudRMF.md) |
| **RMiT clause(s)** | Section 10.50 (Cloud Services Risk Assessment); 10.51 (Public Cloud Key Risks and Controls — Appendix 10); 10.52 (Cloud Data Protection Safeguards) |
| **COBIT objective(s)** | APO10; APO13; APO14 (cloud-resident data); BAI03 (cloud architecture) |
| **Practice standard(s)** | CSA Cloud Controls Matrix; CIS Foundations Benchmarks; ISO/IEC 27017:2015; ISO/IEC 27018:2019 |
| **Additional anchors** | BNM Cloud Technology Risk Assessment Guidelines (Cloud TRAG); BNM Outsourcing PD |

---

## 1. Purpose

To establish how GIBB consumes cloud services — what is permissible, what controls apply, what residency and exit requirements bind. Operationalises [CloudRMF](../01-frameworks/CloudRMF.md) at the policy level. Complements [POL-19 Supplier and Third-Party Security Policy](POL-19-supplier-security-policy.md) for relationship-lifecycle aspects.

## 2. Scope

All cloud services consumed by GIBB — IaaS, PaaS, SaaS, FaaS — across all providers and all business lines. Workforce-driven SaaS acquisition (potential shadow IT) per [POL-09](POL-09-it-asset-management-policy.md).

## 3. Definitions

| Term | Definition |
|---|---|
| **Cloud service model** | IaaS / PaaS / SaaS / FaaS. |
| **Shared-responsibility model** | Division of security responsibilities between provider and customer per service. |
| **Cloud landing zone** | Baselined cloud environment for workload deployment. |
| **CSPM** | Cloud Security Posture Management — continuous configuration monitoring. |
| **Data residency** | Jurisdiction in which data is stored and processed. |

## 4. Policy statements

### 4.1 Approved cloud services

- **4.1.1** Only cloud services approved per the GIBB cloud service catalogue **shall** be used. New cloud service adoption follows [POL-07 Change Management Policy](POL-07-change-management-policy.md) with cloud risk assessment per RMiT 10.50.

### 4.2 Shared-responsibility documented

- **4.2.1** Every cloud service engagement **shall** have a documented shared-responsibility model, with named bank-side owners for bank-side controls.

### 4.3 Landing zone baseline

- **4.3.1** Workloads **shall** be deployed only into baselined cloud landing zones meeting CIS Foundations or equivalent benchmark requirements.

### 4.4 Data residency

- **4.4.1** Customer data and Confidential or higher data resident in cloud **shall** comply with PDPA cross-border requirements and any BNM-imposed residency restrictions for licensed FIs.

### 4.5 Continuous posture monitoring

- **4.5.1** Cloud security posture **shall** be continuously monitored through CSPM tooling, with deviation triggering remediation per [POL-18](POL-18-vulnerability-management-policy.md).

### 4.6 Cloud cryptography

- **4.6.1** Confidential or higher data in cloud **shall** be encrypted at rest using customer-managed or bank-managed keys (not solely cloud-provider-managed) where supported by the service.

### 4.7 Cloud exit

- **4.7.1** Every material cloud service engagement **shall** have a documented exit strategy covering data repatriation, knowledge transfer, and orderly transition — discharging BNM Outsourcing PD exit obligations.

### 4.8 Departure from RMiT Appendix 10

- **4.8.1** Where GIBB's cloud risk management practice departs from RMiT Appendix 10 measures, GIBB **shall** be prepared to explain and demonstrate to BNM that the alternative practice is at least as effective per RMiT 10.51.

### 4.9 Shadow cloud prevention

- **4.9.1** Acquisition or use of cloud services outside the approved catalogue is prohibited. Shadow cloud discovery triggers retrospective onboarding or removal per [POL-09](POL-09-it-asset-management-policy.md) and RMiT 10.16.

## 5. Roles and responsibilities

| Role | R | A | C | I |
|---|---|---|---|---|
| Risk Management Committee | | A | | |
| Head of Cloud Engineering | A (joint) | | C | |
| CISO | | A (joint — cloud security) | C | |
| CRO | | | C (risk acceptance for material deployments) | I |
| CDO | | | C (cloud-resident data per DGF) | I |
| DPO | | | C (cross-border per PDPA) | I |

## 6. Exceptions

Per TRMF Section 12. Material departures from RMiT Appendix 10 require explicit RMC approval and documented justification.

## 7. Enforcement

Per TRMF Section 12. Shadow cloud is treated as a control deficiency.

## 8. Related documents

- **Parent framework:** [CloudRMF](../01-frameworks/CloudRMF.md)
- **Related policies:** [POL-19](POL-19-supplier-security-policy.md); [POL-10](POL-10-it-vendor-management-policy.md); [POL-09](POL-09-it-asset-management-policy.md)
- **Related register:** [REG-CL Cloud Service Register](../06-registers/REG-CL-cloud-service-register.md)

## 9. References

- BNM RMiT, 28 November 2025: Section 10.50–10.52; Appendix 10
- BNM Cloud Technology Risk Assessment Guidelines (Cloud TRAG)
- BNM Outsourcing Policy Document
- COBIT 2019 — APO10; APO13; APO14; BAI03
- CSA Cloud Controls Matrix; CIS Foundations Benchmarks
- ISO/IEC 27017:2015; ISO/IEC 27018:2019

## 10. Document control

| Version | Date | Author | Reviewer | Approver | Change summary |
|---|---|---|---|---|---|
| 1.0 | [Effective] | Head of Cloud + CISO | RMC | RMC | Initial Effective version |
