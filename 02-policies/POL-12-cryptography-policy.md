# Cryptography Policy

| | |
|---|---|
| **Document ID** | POL-12 |
| **Layer** | Policy (Tier 1) |
| **Owner** | CISO |
| **Approver** | Risk Management Committee |
| **Classification** | Internal |
| **Version** | 1.0 |
| **Effective date** | 2026-02-01 |
| **Next review** | 2027-02-01 |
| **ISO/IEC 27002:2022 controls** | 8.24 (Use of cryptography) |
| **BNM RMiT (28 Nov 2025)** | Section 10.20 (Cryptography Policy and Standards); Section 10.21 (Cryptographic Controls Due Diligence); Section 10.22 (Cryptographic Protocol Implementation); Section 10.23 (Public Key Certificate Management) |
| **Parent framework(s)** | [CRMF](../01-frameworks/CRMF.md) |
| **COBIT objective(s)** | APO13 Managed Security |

> Skeleton policy. Requires a supporting **Cryptographic Standard** specifying approved algorithms, key lengths, key management procedures, and migration plans for post-quantum readiness.

---

## 1. Purpose

To establish requirements for the use of cryptography to protect the confidentiality, integrity, and authenticity of GIBB information.

## 2. Scope

All use of cryptography across GIBB — encryption at rest and in transit, digital signatures, hashing, key management, and supporting infrastructure (PKI, HSMs, KMS).

## 3. Policy statements

### 3.1 Use of cryptography

- **3.1.1** Cryptography shall be applied based on the classification of the information being protected, with **Confidential** and **Highly Restricted** information encrypted at rest and in transit. *(Implements ISO/IEC 27002:2022 control 8.24.)*
- **3.1.2** Cryptographic algorithms, modes, key lengths, and protocols shall be those approved in the Cryptographic Standard, which the CISO maintains. Deprecated algorithms shall not be used.

### 3.2 Key management

- **3.2.1** Cryptographic keys shall be generated, stored, distributed, used, rotated, and destroyed using approved key management systems (HSM or cloud KMS with FIPS 140-2 / FIPS 140-3 validated modules).
- **3.2.2** Access to cryptographic keys shall be restricted to authorised processes and individuals, with separation of duties between key custodianship and key use where feasible.

### 3.3 Public Key Infrastructure

- **3.3.1** Certificates issued by the bank's PKI shall conform to the Certificate Policy and Certification Practice Statement. Public certificates shall be issued by trusted Certificate Authorities.

### 3.4 Cryptographic agility and quantum readiness

- **3.4.1** Systems shall be designed for cryptographic agility, supporting algorithm replacement without re-architecture. A post-quantum cryptography migration plan shall be maintained by the CISO and updated annually as NIST and other authoritative guidance evolves.

### 3.5 Prohibited uses

- **3.5.1** Cryptography shall not be used to evade legitimate inspection by the bank's security or compliance functions. Personal use of cryptography to conceal bank information from authorised audit is prohibited.

## 4. Roles and responsibilities

| Role | R | A | C | I |
|---|---|---|---|---|
| Risk Management Committee | | A | | I |
| CISO | A | | | |
| Cryptographic key custodians | R | | C | I |
| System owners | R | | C | I |

## 5. Exceptions

Per [POL-04](POL-04-information-security-policy.md). Use of any non-approved cryptographic algorithm requires written CISO approval.

## 6. Enforcement

Per [POL-04](POL-04-information-security-policy.md).

## 7. Related documents

[POL-04](POL-04-information-security-policy.md), [POL-11](POL-11-data-classification-policy.md), [POL-17](POL-17-secure-development-policy.md).

## 8. References

ISO/IEC 27002:2022 — control 8.24. NIST SP 800-57 (Key Management). NIST FIPS 140-3. BNM RMiT (28 Nov 2025) Section 10.20–10.23 (Cryptography). [Regulatory Mapping Reference](../_context/framework-stack.md).

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
