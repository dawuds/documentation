# POL-11 — Data Classification and Handling Policy

| | |
|---|---|
| **Document ID** | POL-11 |
| **Layer** | Policy (Tier 1) |
| **Version** | 1.0 |
| **Owner** | Chief Data Officer + Data Protection Officer (joint) |
| **Approver** | Risk Management Committee |
| **Classification** | Internal |
| **Effective** | [Effective] |
| **Next review** | Annual |
| **Parent framework(s)** | [DGF](../01-frameworks/DGF.md); secondary [CIMF](../01-frameworks/CIMF.md) for customer data overlay |
| **RMiT clause(s)** | Section 9.2(d) (asset classification within TRMF); Section 10.44(d) + Appendix 1 (sensitive removable media); Section 12 (Digital Services data handling) |
| **COBIT objective(s)** | APO14 Managed Data; APO03 Managed Enterprise Architecture |
| **Practice standard(s)** | DAMA-DMBOK 2; ISO 8000 (Data Quality); ISO/IEC 27002:2022 controls 5.12, 5.13 |
| **Additional anchors** | BNM Shariah Governance Framework (Shariah-Confidential classification); PDPA 2010 |

---

## 1. Purpose

To establish how GIBB classifies information by sensitivity and applies handling controls across the data lifecycle. The classification scheme is the foundation of every downstream protective control — encryption, access, retention, disclosure.

## 2. Scope

All information processed by GIBB, in any form (digital, physical, in-transit, at-rest, in-processing). Owned by the bank or entrusted to it.

## 3. Classification scheme

| Classification | Definition | Examples |
|---|---|---|
| **Public** | Authorised for unrestricted public disclosure | Published marketing materials, press releases |
| **Internal** | For use within GIBB and contracted third parties; unauthorised disclosure causes limited harm | Internal procedures, internal communications |
| **Confidential** | Disclosure causes significant harm; subject to legal, regulatory, or contractual protection | Customer account details, internal financial information, employee records |
| **Highly Restricted** | Disclosure causes severe harm | Authentication credentials, cryptographic keys, board papers, sensitive personal data |
| **Shariah-Confidential** | Shariah Committee deliberations, fatwa drafts, Shariah-sensitive product design details | (See Shariah Governance Framework) |

## 4. Policy statements

### 4.1 Classification at source

- **4.1.1** All information **shall** be classified by the data owner at point of creation or acquisition per the scheme in Section 3. *(Implements ISO/IEC 27002:2022 control 5.12; RMiT 9.2(d).)*
- **4.1.2** Aggregated information inherits the **highest** classification of its components.

### 4.2 Labelling

- **4.2.1** Information **shall** be labelled at file, document, message, and database-record level where technically feasible, using consistent labels per the scheme. *(Implements ISO/IEC 27002:2022 control 5.13.)*

### 4.3 Handling by classification

- **4.3.1** Handling controls **shall** be applied per classification across storage, transmission, processing, sharing, retention, and destruction.
- **4.3.2** Confidential and Highly Restricted information **shall** be encrypted at rest and in transit using approved algorithms per [POL-12 Cryptography Policy](POL-12-cryptography-policy.md).
- **4.3.3** Removable-media handling **shall** meet the minimum controls in RMiT 10.44(d) and Appendix 1.
- **4.3.4** Digital service delivery handling **shall** meet RMiT Section 12 and Appendices 2, 3.

### 4.4 Customer data overlay

- **4.4.1** Customer data **shall** be classified Confidential or Highly Restricted depending on sensitivity, and additionally governed by [POL-CI-01 Customer Data Protection Policy](POL-CI-01-customer-data-protection-policy.md) and PDPA.

### 4.5 Shariah-Confidential

- **4.5.1** Shariah-Confidential information **shall** be handled with additional restrictions per the Shariah Governance Framework — access limited to Shariah Committee, Shariah Compliance, and named bank officers.

### 4.6 Retention and destruction

- **4.6.1** Information **shall** be retained only as long as required by business, regulatory, or legal need per the records retention schedule. Information past retention **shall** be destroyed using methods appropriate to classification and media.

### 4.7 Personal data

- **4.7.1** Personal data **shall** be handled per PDPA 2010 and any applicable foreign data protection law. Personal data is Confidential or Highly Restricted depending on sensitivity.

## 5. Roles and responsibilities

| Role | R | A | C | I |
|---|---|---|---|---|
| Risk Management Committee | | A | | |
| CDO | A (joint — data governance) | | | |
| DPO | A (joint — personal data) | | | |
| CISO | | | C (security controls per classification) | I |
| Shariah Committee | | A (Shariah-Confidential) | | |
| Data owners (function heads) | R | | | I |

## 6. Exceptions

Per TRMF Section 12. Reclassification downward requires CDO + DPO joint approval.

## 7. Enforcement

Per TRMF Section 12. Mishandling of Highly Restricted or Shariah-Confidential is a material control failure.

## 8. Related documents

- **Parent framework:** [DGF](../01-frameworks/DGF.md); [CIMF](../01-frameworks/CIMF.md)
- **Related policies:** [POL-12 Cryptography](POL-12-cryptography-policy.md); [POL-04 Information Security Policy](POL-04-information-security-policy.md); [POL-CI-01 Customer Data Protection](POL-CI-01-customer-data-protection-policy.md)
- **Related register:** [REG-DA Data Asset Register](../06-registers/REG-DA-data-asset-register.md)

## 9. References

- BNM RMiT, 28 November 2025: Section 9.2(d); 10.44(d) + Appendix 1; Section 12 + Appendices 2, 3
- BNM Shariah Governance Framework
- COBIT 2019 — APO14; APO03
- ISO/IEC 27002:2022 — controls 5.12, 5.13
- DAMA-DMBOK 2; ISO 8000
- Personal Data Protection Act 2010 (Malaysia)

## 10. Document control

| Version | Date | Author | Reviewer | Approver | Change summary |
|---|---|---|---|---|---|
| 1.0 | [Effective] | CDO + DPO | RMC | RMC | Initial Effective version |
