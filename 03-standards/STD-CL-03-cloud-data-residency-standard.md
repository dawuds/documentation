# STD-CL-03 — Cloud Data Residency Standard

| | |
|---|---|
| **Document ID** | STD-CL-03 | **Version** | 1.0 |
| **Owner / Approver** | CISO + DPO / CISO |
| **Parent policy** | [POL-20](../02-policies/POL-20-cloud-acceptable-use-policy.md); [POL-CI-01](../02-policies/POL-CI-01-customer-data-protection-policy.md) | **Parent framework** | [CloudRMF](../01-frameworks/CloudRMF.md); [CIMF](../01-frameworks/CIMF.md) |
| **Additional anchors** | PDPA 2010 Section 129; BNM Outsourcing PD |

## 1. Purpose
Specify where GIBB data may reside in cloud — by data class, by jurisdiction, by service.

## 2. Scope
All GIBB data resident in or processed by cloud services.

## 3. Requirements

### 3.1 Residency by class

| Data class | Allowed residency | Cross-border basis required if outside Malaysia |
|---|---|---|
| Public | Anywhere | n/a |
| Internal | Malaysia + APAC + EU (with safeguards) | TPSP attestation + due diligence per [STD-TP-01](STD-TP-01-tpsp-due-diligence-standard.md) |
| Confidential | Malaysia preferred; APAC / EU allowed with PDPA Section 129 basis | PDPA Section 129 basis + cross-border safeguard (SCCs or equivalent) |
| Highly Restricted (excl. authentication) | Malaysia only unless explicit RMC approval | RMC approval + PDPA Section 129 basis + strong safeguards |
| Authentication data (passwords, MFA secrets, keys) | Malaysia only — no cross-border | n/a (not permitted cross-border) |
| Shariah-Confidential | Malaysia only — no cross-border | n/a |
| Customer personal data under MCIPD | Per PDPA + MCIPD; cross-border requires Section 129 basis | PDPA Section 129 basis + customer consent where required |

### 3.2 Multi-region for resilience

Cross-border replication of Confidential data for DR purposes requires:
- PDPA Section 129 basis recorded in [REG-ROPA](../06-registers/REG-ROPA-records-of-processing-activity.md)
- DR region's data protection regime assessed by DPO
- Customer-managed encryption keys in customer-controlled jurisdiction
- Documented exit if cross-border DR region becomes unsuitable

### 3.3 Cloud-region selection

Each cloud service entry in [REG-CL](../06-registers/REG-CL-cloud-service-register.md) records:
- Provider region(s) used for primary
- Provider region(s) used for DR
- Cross-border basis (per Section 3.2 if applicable)
- DPO sign-off for any cross-border element

### 3.4 Cloud-provider hyperscaler regions

For each approved provider, specific regions are catalogued as "approved primary", "approved DR", or "not approved". Catalogue maintained by Head of Cloud, reviewed annually.

### 3.5 Departures from RMiT Appendix 10

Where cloud service architecture departs from RMiT Appendix 10 cloud risk mapping due to residency constraints, GIBB shall demonstrate alternative practice is at least as effective per [POL-20 Section 4.8](../02-policies/POL-20-cloud-acceptable-use-policy.md) and RMiT 10.51. Documented in [REG-CL](../06-registers/REG-CL-cloud-service-register.md) `appendix_10_departures`.

### 3.6 Data sovereignty changes

Material changes to data residency (new region, additional cross-border flow) trigger [SOP-CL-01 Cloud Service Onboarding](../04-procedures/SOP-CL-01-cloud-service-onboarding-sop.md) gating control.

## 4. Exceptions
Cross-border residency departures from Section 3.1 require RMC approval + DPO sign-off + PDPA Section 129 basis.

## 5. Related documents
[POL-20](../02-policies/POL-20-cloud-acceptable-use-policy.md); [POL-CI-01](../02-policies/POL-CI-01-customer-data-protection-policy.md); [STD-CL-01](STD-CL-01-cloud-security-standard.md); [STD-CI-01](STD-CI-01-customer-data-classification-standard.md); [REG-CL](../06-registers/REG-CL-cloud-service-register.md); [REG-ROPA](../06-registers/REG-ROPA-records-of-processing-activity.md)

## 6. References
PDPA 2010 Section 129; BNM RMiT 28 Nov 2025 Section 10.50–10.52; BNM Cloud TRAG; BNM MCIPD; BNM Outsourcing PD.

## 7. Document control
| Version | Date | Author | Approver | Change |
|---|---|---|---|---|
| 1.0 | [Effective] | CISO + DPO | CISO | Initial |
