# Secure Development Policy

| | |
|---|---|
| **Document ID** | POL-12 |
| **Layer** | Policy (Tier 1) |
| **Owner** | Head of Engineering (joint with CISO) |
| **Approver** | Risk Management Committee |
| **Classification** | Internal |
| **Version** | 1.0 |
| **Effective date** | 2026-02-01 |
| **Next review** | 2027-02-01 |
| **ISO/IEC 27002:2022 controls** | 8.25 (Secure development lifecycle), 8.26 (Application security requirements), 8.27 (Secure system architecture and engineering principles), 8.28 (Secure coding), 8.29 (Security testing in development and acceptance), 8.30 (Outsourced development), 8.31 (Separation of development, test and production environments) |
| **BNM RMiT (28 Nov 2025)** | Section 10.4–10.16 (System Development and Acquisition, incl. Section 10.5 SDLC, Section 10.6 Rapid Development, Section 10.10 Source Code Review for Critical Systems, Section 10.11 Independent Review of System Changes, Section 10.14 Automated Development and Security Tools, Section 10.15 Third Party Software Supply Chain Risk, Section 10.16 Shadow IT); Section 12 (Digital Services) with Appendices 2 and 3 |

> Skeleton policy.

---

## 1. Purpose

To define the secure development requirements for software, services, and infrastructure-as-code created or modified by General Bank or on its behalf, across the lifecycle from requirements through retirement.

## 2. Scope

All software development and engineering activity producing or modifying systems used by General Bank, including in-house development, outsourced development, low-code/no-code, infrastructure-as-code, and customisation of vendor software.

## 3. Policy statements

### 3.1 Secure development lifecycle

- **3.1.1** A secure development lifecycle shall be defined and followed, integrating security into each phase from requirements through retirement. *(Implements ISO/IEC 27002:2022 control 8.25.)*

### 3.2 Application security requirements

- **3.2.1** Security requirements shall be defined for every application, derived from data classification, threat modelling, and applicable regulatory requirements. *(Implements ISO/IEC 27002:2022 control 8.26; BNM RMiT Section 10.5 (SDLC Methodology); Section 12 (Digital Services minimum controls per Appendices 2 and 3).)*

### 3.3 Threat modelling and secure design

- **3.3.1** Threat modelling shall be performed for new systems and material changes to existing systems handling Confidential or higher-classification data. Findings shall be tracked to remediation. *(Implements ISO/IEC 27002:2022 control 8.27.)*

### 3.4 Secure coding

- **3.4.1** Developers shall apply approved secure coding standards. Static application security testing (SAST) and software composition analysis (SCA) shall run in the CI pipeline; findings exceeding agreed thresholds shall block release. *(Implements ISO/IEC 27002:2022 control 8.28.)*

### 3.5 Security testing

- **3.5.1** Security testing shall include SAST, SCA, dynamic application security testing (DAST), and — for material systems and at least annually for internet-facing systems — independent penetration testing. *(Implements ISO/IEC 27002:2022 control 8.29.)*
- **3.5.2** Penetration test findings shall be remediated within the timelines defined in [POL-13 Vulnerability Management Policy](13-vulnerability-management-policy.md).

### 3.6 Environment separation

- **3.6.1** Development, test, and production environments shall be logically and access-segregated. Production data shall not be used in non-production environments without anonymisation or strong access control. *(Implements ISO/IEC 27002:2022 control 8.31.)*

### 3.7 Outsourced development

- **3.7.1** Outsourced development shall be subject to the same secure development requirements as in-house development, with contractual obligations and audit rights established per [POL-07 Supplier & Third-Party Security Policy](07-supplier-security-policy.md). *(Implements ISO/IEC 27002:2022 control 8.30.)*

### 3.8 Source code protection

- **3.8.1** Source code repositories shall enforce access control, branch protection, mandatory code review for production-bound changes, and signed commits where technically supported. *(See also [POL-02 Section 4.2.4](02-access-control-policy.md).)*

### 3.9 Secrets management

- **3.9.1** Secrets (credentials, tokens, keys) shall not be committed to source code or configuration files; they shall be managed through an approved secrets management platform.

## 4. Roles and responsibilities

| Role | R | A | C | I |
|---|---|---|---|---|
| Risk Management Committee | | A | | I |
| Head of Engineering | A | | C | |
| CISO | | | C | I |
| Application security team | R | | C | I |
| Development teams | R | | | I |

## 5. Exceptions

Per [POL-00](00-information-security-policy.md).

## 6. Enforcement

Per [POL-00](00-information-security-policy.md).

## 7. Related documents

[POL-00](00-information-security-policy.md), [POL-02](02-access-control-policy.md), [POL-05](05-cryptography-policy.md), [POL-07](07-supplier-security-policy.md), [POL-13](13-vulnerability-management-policy.md).

## 8. References

ISO/IEC 27002:2022 — controls 8.25–8.31. OWASP ASVS (Application Security Verification Standard). NIST SP 800-218 (Secure Software Development Framework). BNM RMiT (28 Nov 2025) Section 10.4–10.16; Section 12 + Appendices 2 and 3. [Regulatory Mapping Reference](../00-foundations/regulatory-mapping-reference.md).

## 9. Document control

| Version | Date | Author | Reviewer | Approver | Change summary |
|---|---|---|---|---|---|
| 1.0 | 2026-01-15 | Head of Engineering + CISO | Risk Management Committee | Risk Management Committee | Initial Effective version (skeleton). |
