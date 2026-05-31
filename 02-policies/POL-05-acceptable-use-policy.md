# Acceptable Use Policy

| | |
|---|---|
| **Document ID** | POL-05 |
| **Layer** | Policy (Tier 1) |
| **Owner** | CISO |
| **Approver** | Risk Management Committee |
| **Classification** | Internal |
| **Version** | 1.0 |
| **Effective date** | 2026-02-01 |
| **Next review** | 2027-02-01 |
| **ISO/IEC 27002:2022 controls** | 5.10 (Acceptable use of information and other associated assets), 8.1 (User endpoint devices) |
| **BNM RMiT (28 Nov 2025)** | Section 10.53–10.57 (Access Control); Section 15 (Security Awareness and Education) |
| **Parent framework(s)** | [CRMF](../01-frameworks/CRMF.md) |
| **COBIT objective(s)** | APO01 Managed I&T Management Framework; DSS06 Managed Business Process Controls |

> Skeleton policy. First-pass content suitable as a starting point. Requires extension before production use — in particular the detailed channel-by-channel rules (email, messaging, removable media, social media, AI tools) should be expanded based on the bank's environment.

---

## 1. Purpose

To define the acceptable use of GIBB information assets — including systems, networks, devices, applications, data, and communication channels — by all personnel, and to set out the responsibilities of users in protecting those assets.

## 2. Scope

Applies to all personnel (employees, contractors, secondees, third parties) and all use of GIBB information assets, whether on bank premises, on bank-issued devices, or through personally owned devices accessing bank resources.

## 3. Policy statements

### 3.1 General principles

- **3.1.1** Bank information assets shall be used for authorised business purposes. Limited and reasonable personal use is permitted provided it does not interfere with duties, consume disproportionate resources, or breach this policy.
- **3.1.2** Users shall not use bank assets for any illegal activity, harassment, discrimination, or activity that would bring the bank into disrepute.

### 3.2 Authentication and access

- **3.2.1** Users shall not share authentication credentials. Credentials shall be kept confidential and stored only in approved password managers.
- **3.2.2** Users shall lock unattended workstations and devices.

### 3.3 Device and software

- **3.3.1** Only bank-approved software shall be installed on bank-issued devices. *(Implements ISO/IEC 27002:2022 control 8.1.)*
- **3.3.2** Bank data shall not be stored on personally owned devices or personal cloud services except via approved bring-your-own-device controls.

### 3.4 Email, messaging, and collaboration

- **3.4.1** External communication channels shall be used in accordance with the data classification of the information being shared, per [POL-11 Data Classification & Handling Policy](POL-11-data-classification-policy.md).
- **3.4.2** Users shall not click on suspicious links or open suspicious attachments, and shall report suspected phishing through the published channel.

### 3.5 AI and generative tools

- **3.5.1** Only bank-approved AI tools shall be used for work involving bank information. Confidential or higher-classification data shall not be entered into any AI tool not explicitly approved for that classification.

### 3.6 Removable media

- **3.6.1** Removable media use shall be restricted to approved devices and shall apply approved encryption.

### 3.7 Reporting

- **3.7.1** Users shall report any suspected security event, loss of bank assets, or breach of this policy without delay through the channels defined in [POL-13 Incident Management Policy](POL-13-incident-management-policy.md).

## 4. Roles and responsibilities

| Role | R | A | C | I |
|---|---|---|---|---|
| Risk Management Committee | | A | | I |
| CISO | A | | | |
| Line managers | R | | | I |
| All personnel | R | | | I |

## 5. Exceptions

Documented in the Exception Register; approved by the CISO; time-bound.

## 6. Enforcement

Non-compliance may result in disciplinary action and, where applicable, civil or criminal proceedings.

## 7. Related documents

- **Parent:** [POL-04 Information Security Policy](POL-04-information-security-policy.md)
- [POL-06 Access Control Policy](POL-06-access-control-policy.md), [POL-11 Data Classification & Handling Policy](POL-11-data-classification-policy.md), [POL-13 Incident Management Policy](POL-13-incident-management-policy.md).

## 8. References

ISO/IEC 27002:2022 — controls 5.10, 8.1. BNM RMiT (28 Nov 2025) Section 10.53–10.57; Section 15. [Regulatory Mapping Reference](../_context/framework-stack.md).

## 9. Document control

| Version | Date | Author | Reviewer | Approver | Change summary |
|---|---|---|---|---|---|
| 1.0 | 2026-01-15 | CISO | Risk Management Committee | Risk Management Committee | Initial Effective version (skeleton). |

---

## v2 re-anchoring (2026-05-28)

This document was re-anchored as part of the v2 build (Session 5) per [DEC-001](../_context/decisions.md). Substantive content preserved from the v1 snapshot at [`../v1/`](../v1/). Changes applied:

- Document ID updated to v2 numbering convention
- **Parent framework(s)** and **COBIT objective(s)** added to metadata block
- Bank name normalised from "General Bank" to **GIBB** (General Islamic Bank Berhad)
- Internal cross-references migrated from v1 paths to v2 paths
- v1 sister-document references updated to v2 document IDs

Pending formal GIBB approval under v2. The Effective and Next review dates above are inherited from the v1 1.x lifecycle and will be updated when this document is approved under v2 governance.
