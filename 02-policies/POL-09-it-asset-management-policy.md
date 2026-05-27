# POL-09 — IT Asset Management Policy

| | |
|---|---|
| **Document ID** | POL-09 |
| **Layer** | Policy (Tier 1) |
| **Version** | 1.0 |
| **Owner** | Chief Information Officer + Chief Data Officer (joint for asset and data scope) |
| **Approver** | Risk Management Committee |
| **Classification** | Internal |
| **Effective** | [Effective] |
| **Next review** | Annual |
| **Parent framework(s)** | [TRMF](../01-frameworks/TRMF.md); secondary [DGF](../01-frameworks/DGF.md) |
| **RMiT clause(s)** | Section 11.3(h) (CRF — centralised automated technology asset inventory); 9.2(d) (asset classification within TRMF); 10.17 (vulnerability and EOL management — depends on inventory) |
| **COBIT objective(s)** | BAI09 Managed Assets; APO14 Managed Data (data asset overlap with DGF) |
| **Practice standard(s)** | ITIL 4 Service Configuration Management; ISO/IEC 19770 series (IT asset management) |

---

## 1. Purpose

To establish how GIBB identifies, classifies, tracks, and lifecycle-manages all IT assets — hardware, software, services, cloud workloads, data — across their lifecycle. A current, complete asset inventory is the foundation of every downstream control: vulnerability management, change management, incident response, license compliance, and end-of-life remediation.

## 2. Scope

All IT assets owned, leased, contracted, or operated by GIBB: hardware (servers, endpoints, network devices, mobile, IoT, OT), software (applications, libraries, container images, infrastructure-as-code), services (SaaS, IaaS, PaaS, third-party APIs), data assets (per [DGF](../01-frameworks/DGF.md) — joint scope), physical media.

## 3. Definitions

| Term | Definition |
|---|---|
| **IT asset** | An item of value to GIBB requiring identification, ownership, lifecycle management, and accounting treatment where applicable. |
| **Configuration item (CI)** | An IT asset whose configuration is tracked, typically in a Configuration Management Database (CMDB). |
| **Asset owner** | Accountable role for an asset's classification, lifecycle, and protection. |
| **Custodian** | Operational role for day-to-day management of an asset. |

## 4. Policy statements

### 4.1 Inventory completeness

- **4.1.1** GIBB **shall** maintain a **centralised automated tracking system for technology assets** per RMiT 11.3(h). *(Implements RMiT 11.3(h); ITIL 4 Service Configuration Management.)*
- **4.1.2** Inventory completeness **shall** be assessed through automated discovery (network, endpoint, cloud, SaaS) reconciled with the CMDB. Material discrepancies **shall** be investigated and resolved.

### 4.2 Ownership

- **4.2.1** Every IT asset **shall** have a named **asset owner** and **custodian**.

### 4.3 Classification

- **4.3.1** IT assets **shall** be classified by criticality per RMiT 9.2(d) and by data sensitivity per [POL-11 Data Classification and Handling Policy](POL-11-data-classification-policy.md). Asset class drives downstream protection requirements.

### 4.4 Lifecycle

- **4.4.1** Assets **shall** be tracked from acquisition through deployment, operation, and decommissioning.
- **4.4.2** Decommissioning **shall** include secure data destruction per the [Data Destruction Standard](../03-standards/data-destruction-standard.md) and (for hardware) media sanitisation aligned to NIST SP 800-88 Rev. 1.

### 4.5 End-of-life and end-of-support

- **4.5.1** Assets approaching or beyond vendor end-of-support **shall** be identified at least 12 months in advance, with remediation plans tracked. *(Implements RMiT 10.17.)*

### 4.6 Software supply chain

- **4.6.1** Software components (including open-source libraries and container images) **shall** be tracked through Software Bill of Materials (SBOM) where technically feasible. *(Implements RMiT 10.15 — Third Party Software Supply Chain Risk.)*

### 4.7 Shadow IT

- **4.7.1** Acquisition or deployment of IT services outside the bank's IT governance (Shadow IT) is prohibited. Discovery of shadow IT triggers retrospective onboarding or removal per RMiT 10.16.

## 5. Roles and responsibilities

| Role | R | A | C | I |
|---|---|---|---|---|
| Risk Management Committee | | A | | |
| CIO | A (IT asset scope) | | C | |
| CDO | A (data asset scope, joint with DGF) | | C | |
| Head of IT Operations | R | | C | I |
| Asset owners (function heads) | R | | | I |
| Procurement | R (acquisition) | | C | I |

## 6. Exceptions

Per TRMF Section 12.

## 7. Enforcement

Per TRMF Section 12. Shadow IT discovery triggers control deficiency reporting.

## 8. Related documents

- **Parent framework:** [TRMF](../01-frameworks/TRMF.md); [DGF](../01-frameworks/DGF.md)
- **Related policies:** [POL-11 Data Classification](POL-11-data-classification-policy.md); [POL-18 Vulnerability and Patch Management Policy](POL-18-vulnerability-management-policy.md); [POL-20 Cloud Acceptable Use Policy](POL-20-cloud-acceptable-use-policy.md)
- **Related register:** [REG-DA Data Asset Register](../06-registers/data-asset-register.md); CMDB (operational system)

## 9. References

- BNM RMiT, 28 November 2025: Section 11.3(h); 9.2(d); 10.15; 10.16; 10.17
- COBIT 2019 — BAI09; APO14
- ITIL 4 — Service Configuration Management
- ISO/IEC 19770 series
- NIST SP 800-88 Rev. 1

## 10. Document control

| Version | Date | Author | Reviewer | Approver | Change summary |
|---|---|---|---|---|---|
| 1.0 | [Effective] | CIO + CDO | RMC | RMC | Initial Effective version |
