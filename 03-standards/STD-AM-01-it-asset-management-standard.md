# STD-AM-01 — IT Asset Management Standard

| | |
|---|---|
| **Document ID** | STD-AM-01 |
| **Layer** | Standard (Tier 2) |
| **Version** | 1.0 |
| **Owner** | CIO + CDO |
| **Approver** | CIO |
| **Classification** | Internal |
| **Effective** | [Effective] |
| **Next review** | Annual |
| **Parent policy** | [POL-09 IT Asset Management Policy](../02-policies/POL-09-it-asset-management-policy.md) |
| **Parent framework(s)** | [TRMF](../01-frameworks/TRMF.md); [DGF](../01-frameworks/DGF.md) |
| **RMiT clause(s)** | Section 11.3(h) (centralised automated technology asset inventory); 9.2(d) (asset classification); 10.17 |
| **COBIT objective(s)** | BAI09; APO14 |
| **Practice standard(s)** | ITIL 4 Service Configuration Management; ISO/IEC 19770 |

---

## 1. Purpose

To specify the measurable requirements for IT asset identification, classification, tracking, lifecycle, and decommissioning at GIBB, satisfying the centralised automated inventory required by RMiT 11.3(h).

## 2. Scope

All IT assets as defined in [POL-09](../02-policies/POL-09-it-asset-management-policy.md).

## 3. Requirements

### 3.1 Inventory completeness

| Ref | Requirement | Measurement |
|---|---|---|
| 3.1.1 | All hardware assets **shall** be discoverable through automated network and endpoint discovery, reconciled with CMDB **weekly**. | Weekly reconciliation report; discrepancy count |
| 3.1.2 | All software assets (installed software, container images, libraries) **shall** be tracked via SBOM where the language ecosystem supports it. | SBOM generation report |
| 3.1.3 | All cloud assets **shall** be discoverable via cloud-native inventory tooling (e.g., AWS Config, Azure Resource Graph) reconciled with CMDB **daily**. | Daily reconciliation report |
| 3.1.4 | All SaaS subscriptions **shall** be tracked through the SaaS inventory; SaaS discovery via SSO logs and procurement records cross-checked **quarterly**. | Quarterly SaaS reconciliation |

### 3.2 Asset attributes

Each CI **shall** carry minimum attributes:

| Attribute | Mandatory | Source |
|---|---|---|
| Asset ID | Yes | Auto |
| Asset name and description | Yes | Owner |
| Asset type | Yes | Discovery + Owner |
| Owner (role) | Yes | Owner-assigned |
| Custodian | Yes | Owner-assigned |
| Classification (criticality per RMiT 9.2(d)) | Yes | Owner per [DGF/CIMF](../01-frameworks/DGF.md) |
| Data classification (Public/Internal/Confidential/Highly Restricted/Shariah-Confidential) | Yes | Owner |
| Location | Yes | Auto (network/cloud) or Owner-recorded |
| Vendor / source | Yes | Procurement |
| Acquisition date | Yes | Procurement |
| Lifecycle stage (Active/Pending Retire/Retired) | Yes | Owner |
| End-of-support date (where applicable) | Yes | Vendor source |
| Dependencies (upstream and downstream) | Recommended | CMDB |

### 3.3 Classification

| Ref | Requirement | Measurement |
|---|---|---|
| 3.3.1 | Asset criticality classification **shall** use Tier 0 / Tier 1 / Tier 2 / Tier 3, with Tier 0 reserved for systems whose failure has direct material customer or regulatory impact. | Tier assignment in CMDB |
| 3.3.2 | Reclassification **shall** require owner approval and notification to TRMF (for Tier 0 → Tier 1 movement) or to RMC (for Tier 0 retirement). | Approval record |

### 3.4 End-of-life management

| Ref | Requirement | Measurement |
|---|---|---|
| 3.4.1 | Assets within 12 months of vendor end-of-support **shall** be flagged in the End-of-Life Register with a remediation plan. | EOL report; plan tracked |
| 3.4.2 | Internet-facing systems past end-of-support **shall** not operate without compensating controls and time-bound exception per [POL-13/POL-18](../02-policies/POL-09-it-asset-management-policy.md). | Exception register |

### 3.5 Decommissioning

| Ref | Requirement | Measurement |
|---|---|---|
| 3.5.1 | Decommissioned hardware **shall** undergo media sanitisation aligned to NIST SP 800-88 Rev. 1 before disposal or re-use. | Sanitisation certificate |
| 3.5.2 | Decommissioned software/services **shall** trigger data destruction per retention schedule and access revocation. | Destruction certificate; access revocation log |
| 3.5.3 | Decommissioning of Tier 0/1 systems **shall** follow RMiT 10.13 (Critical System Decommissioning) — RMC notification, customer notification (where applicable), data preservation per retention. | RMC paper |

### 3.6 Shadow IT detection

| Ref | Requirement | Measurement |
|---|---|---|
| 3.6.1 | Shadow IT discovery **shall** be performed quarterly via SaaS usage analytics, expense system pattern matching, and SSO logs. | Quarterly Shadow IT report |
| 3.6.2 | Discovered shadow IT **shall** be triaged within 10 business days for onboarding or removal per RMiT 10.16. | Triage record |

### 3.7 Reconciliation cadence

| Ref | Requirement | Measurement |
|---|---|---|
| 3.7.1 | CMDB completeness **shall** be measured monthly as % of discovered assets present in CMDB; target ≥ 95% with reconciliation actions for shortfall. | Monthly CMDB completeness report |

## 4. Exceptions

Per [POL-09](../02-policies/POL-09-it-asset-management-policy.md) and TRMF Section 12.

## 5. Related documents

- **Parent policy:** [POL-09](../02-policies/POL-09-it-asset-management-policy.md)
- **Implementing procedures:** SOP-AM-01 Asset Onboarding SOP; SOP-AM-02 Decommissioning SOP (future)
- **Related register:** [REG-DA Data Asset Register](../06-registers/data-asset-register.md) (DGF-owned, with asset overlap)

## 6. References

- BNM RMiT 28 November 2025 — Section 11.3(h); 9.2(d); 10.13; 10.15; 10.16; 10.17
- COBIT 2019 — BAI09; APO14
- ITIL 4 — Service Configuration Management
- ISO/IEC 19770 series
- NIST SP 800-88 Rev. 1

## 7. Document control

| Version | Date | Author | Reviewer | Approver | Change summary |
|---|---|---|---|---|---|
| 1.0 | [Effective] | CIO + CDO | TRMF team | CIO | Initial Effective |
