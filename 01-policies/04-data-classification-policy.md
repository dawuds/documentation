# Data Classification & Handling Policy

| | |
|---|---|
| **Document ID** | POL-04 |
| **Layer** | Policy (Tier 1) |
| **Owner** | CISO |
| **Approver** | Risk Management Committee |
| **Classification** | Internal |
| **Version** | 1.0 |
| **Effective date** | 2026-02-01 |
| **Next review** | 2027-02-01 |
| **ISO/IEC 27002:2022 controls** | 5.12 (Classification of information), 5.13 (Labelling of information) |
| **BNM RMiT (28 Nov 2025)** | §9.2(d) (asset classification within TRMF); §10.44(d) and Appendix 1 (sensitive data in removable media); §12 (Digital Services — minimum controls for customer information confidentiality and integrity per Appendices 2 and 3) |

> Skeleton policy. Requires extension to detail handling rules per classification × media combination, and to define the data discovery and DLP technical implementation.

---

## 1. Purpose

To establish how General Bank classifies information by sensitivity and impact, labels it, and applies appropriate handling controls across its lifecycle.

## 2. Scope

All information processed by General Bank, in any form, owned by the bank or entrusted to it by customers, employees, partners, or regulators.

## 3. Classification scheme

| Classification | Definition | Examples |
|---|---|---|
| **Public** | Authorised for unrestricted public disclosure. | Published marketing materials, public press releases. |
| **Internal** | For use within the bank and contracted third parties. Unauthorised disclosure causes limited harm. | Internal procedures, internal communications. |
| **Confidential** | Disclosure causes significant harm to the bank, customers, or partners. | Customer account details, internal financial information, employee records. |
| **Highly Restricted** | Disclosure causes severe harm. Subject to strict legal, regulatory, or contractual protection. | Authentication credentials, cryptographic keys, board papers, regulator-confidential information, sensitive personal data. |

## 4. Policy statements

### 4.1 Classification

- **4.1.1** All information shall be classified by the **information owner** at the point of creation or acquisition, using the scheme in §3. *(Implements ISO/IEC 27002:2022 control 5.12.)*
- **4.1.2** Where information of different classifications is combined or aggregated, the aggregate inherits the **highest** classification of its components.

### 4.2 Labelling

- **4.2.1** Information shall be labelled at the file, document, message, and database-record level where technically feasible, using consistent labels aligned with the classification scheme. *(Implements ISO/IEC 27002:2022 control 5.13.)*

### 4.3 Handling

- **4.3.1** Handling controls shall be applied in proportion to classification, covering: storage, transmission, processing, sharing, retention, and destruction. A consolidated handling matrix shall be maintained by the CISO and referenced by all supporting standards and SOPs.
- **4.3.2** **Highly Restricted** information shall be encrypted in transit and at rest using approved algorithms per [POL-05 Cryptography Policy](05-cryptography-policy.md). Removable-media handling shall meet the minimum controls in BNM RMiT §10.44(d) and Appendix 1. Digital service delivery shall meet the minimum security controls in BNM RMiT §12 and Appendices 2 and 3.

### 4.4 Personal data

- **4.4.1** Personal data shall be handled in accordance with the Personal Data Protection Act 2010 (Malaysia) and any applicable foreign data protection law. Personal data is classified Confidential or Highly Restricted depending on sensitivity.

### 4.5 Retention and disposal

- **4.5.1** Information shall be retained only as long as required by business, regulatory, or legal need, per the records retention schedule. Information past retention shall be destroyed using methods appropriate to its classification and media.

## 5. Roles and responsibilities

| Role | R | A | C | I |
|---|---|---|---|---|
| Risk Management Committee | | A | | I |
| CISO | A | | | |
| Data Protection Officer | R | | C | I |
| Information owners | R | | | I |

## 6. Exceptions

Per [POL-00](00-information-security-policy.md). Reclassification downward requires CISO approval.

## 7. Enforcement

Per [POL-00](00-information-security-policy.md). Mishandling of Highly Restricted information is treated as a material control failure.

## 8. Related documents

[POL-00](00-information-security-policy.md), [POL-02](02-access-control-policy.md), [POL-05](05-cryptography-policy.md), [POL-08](08-incident-management-policy.md), [POL-14](14-compliance-policy.md).

## 9. References

ISO/IEC 27002:2022 — controls 5.12, 5.13. BNM RMiT (28 Nov 2025) §9.2(d); §10.44(d) + Appendix 1; §12 + Appendices 2 and 3. Personal Data Protection Act 2010 (Malaysia). [Regulatory Mapping Reference](../00-foundations/regulatory-mapping-reference.md).

## 10. Document control

| Version | Date | Author | Reviewer | Approver | Change summary |
|---|---|---|---|---|---|
| 1.0 | 2026-01-15 | CISO | Risk Management Committee | Risk Management Committee | Initial Effective version (skeleton). |
