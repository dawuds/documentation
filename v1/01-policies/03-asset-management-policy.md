# Asset Management Policy

| | |
|---|---|
| **Document ID** | POL-03 |
| **Layer** | Policy (Tier 1) |
| **Owner** | CISO |
| **Approver** | Risk Management Committee |
| **Classification** | Internal |
| **Version** | 1.0 |
| **Effective date** | 2026-02-01 |
| **Next review** | 2027-02-01 |
| **ISO/IEC 27002:2022 controls** | 5.9 (Inventory of information and other associated assets), 5.10 (Acceptable use), 5.11 (Return of assets) |
| **BNM RMiT (28 Nov 2025)** | Section 9.2 (TRMF Minimum Requirements — asset identification, classification); Section 11.3(h) (CRF — centralised automated technology asset inventory) |

> Skeleton policy. Requires extension to address asset-class–specific handling, particularly for cloud-resident assets and software (SBOM) inventory.

---

## 1. Purpose

To define how General Bank identifies, classifies, owns, tracks, and disposes of information assets across their lifecycle. Without a current and authoritative asset inventory, no other security control can be assured of completeness — the inventory is the foundation of every downstream control.

## 2. Scope

Applies to all information assets: hardware (servers, endpoints, network devices, mobile devices, IoT, OT), software (applications, libraries, container images), data (databases, data stores, files), services (SaaS, IaaS, PaaS, third-party APIs), and physical media.

## 3. Policy statements

### 3.1 Inventory

- **3.1.1** An authoritative inventory of all information assets shall be maintained, with each asset attributed to a named owner. *(Implements ISO/IEC 27002:2022 control 5.9; BNM RMiT Section 9.2(d) (asset classification within the TRMF); Section 11.3(h) (centralised automated technology asset inventory as a mandatory CRF element).)*
- **3.1.2** Inventory completeness shall be assessed through automated discovery (network, endpoint, cloud) reconciled with the configuration management database. Material discrepancies shall be investigated and resolved.

### 3.2 Ownership

- **3.2.1** Every asset shall have a named **owner** accountable for its protection and classification, and a **custodian** responsible for day-to-day operation. Owner and custodian may be the same role, but the ownership is non-delegable.

### 3.3 Classification and handling

- **3.3.1** Information assets shall be classified per [POL-04 Data Classification & Handling Policy](04-data-classification-policy.md). Other asset types shall be classified by the highest sensitivity of data they process.

### 3.4 Lifecycle

- **3.4.1** Assets shall be tracked from acquisition through deployment, operation, and decommissioning. Decommissioning shall include secure data destruction per [POL-05 Cryptography Policy](05-cryptography-policy.md) and the bank's media sanitisation standard.
- **3.4.2** End-of-life and end-of-support assets shall be identified, with remediation plans tracked under [POL-13 Vulnerability Management Policy](13-vulnerability-management-policy.md).

### 3.5 Return of assets

- **3.5.1** On termination of employment or contract, all bank assets shall be returned, and access shall be revoked per [POL-02 Access Control Policy](02-access-control-policy.md). *(Implements ISO/IEC 27002:2022 control 5.11.)*

## 4. Roles and responsibilities

| Role | R | A | C | I |
|---|---|---|---|---|
| Risk Management Committee | | A | | I |
| CISO | A | | | |
| Head of IT Operations | R | | C | I |
| Asset owners | R | | | I |

## 5. Exceptions

Per the general exception process in [POL-00](00-information-security-policy.md).

## 6. Enforcement

Per [POL-00](00-information-security-policy.md).

## 7. Related documents

[POL-00](00-information-security-policy.md), [POL-04](04-data-classification-policy.md), [POL-05](05-cryptography-policy.md), [POL-13](13-vulnerability-management-policy.md).

## 8. References

ISO/IEC 27002:2022 — controls 5.9–5.11. BNM RMiT (28 Nov 2025) Section 9.2; Section 11.3(h). [Regulatory Mapping Reference](../00-foundations/regulatory-mapping-reference.md).

## 9. Document control

| Version | Date | Author | Reviewer | Approver | Change summary |
|---|---|---|---|---|---|
| 1.0 | 2026-01-15 | CISO | Risk Management Committee | Risk Management Committee | Initial Effective version (skeleton). |
