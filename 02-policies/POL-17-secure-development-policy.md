# POL-17 — Secure Development Policy

| | |
|---|---|
| **Document ID** | POL-17 |
| **Layer** | Policy (Tier 1) |
| **Version** | 1.0 |
| **Owner** | Head of Engineering + CISO (joint) |
| **Approver** | Risk Management Committee |
| **Classification** | Internal |
| **Effective** | [Effective] |
| **Next review** | Annual |
| **Parent framework(s)** | [TRMF](../01-frameworks/TRMF.md); secondary [CRMF](../01-frameworks/CRMF.md) |
| **RMiT clause(s)** | Section 10.4 (Enterprise Technology Architecture Framework); 10.5 (SDLC Methodology); 10.6 (Rapid Development Security Requirements); 10.7 (Production Environment Segregation); 10.8 (System Testing Methodology); 10.9 (Scope of System Testing); 10.10 (Source Code Review for Critical Systems); 10.11 (Independent Review of System Changes); 10.13 (Critical System Decommissioning); 10.14 (Automated Development and Security Tools); 10.15 (Third Party Software Supply Chain Risk) |
| **COBIT objective(s)** | BAI03 Managed Solutions Identification and Build; BAI02 Managed Requirements Definition |
| **Practice standard(s)** | ISO/IEC 27002:2022 controls 8.25–8.31; OWASP ASVS; NIST SP 800-218 (SSDF) |
| **Additional anchors** | BNM Shariah Governance Framework (Shariah review for Islamic product systems); RMiT Section 12 + Appendices 2, 3 (Digital Services minimum controls) |

---

## 1. Purpose

To define the secure development requirements for software, services, and infrastructure-as-code created or modified by GIBB or on its behalf, across the lifecycle from requirements through retirement.

## 2. Scope

All software development and engineering activity producing or modifying systems used by GIBB — in-house, outsourced, low-code/no-code, infrastructure-as-code, vendor customisation, AI model code.

## 3. Definitions

| Term | Definition |
|---|---|
| **SDLC** | Software Development Lifecycle. |
| **SAST / SCA / DAST** | Static / software composition / dynamic application security testing. |
| **SBOM** | Software Bill of Materials. |

## 4. Policy statements

### 4.1 SDLC

- **4.1.1** A secure SDLC **shall** be defined and followed, integrating security into each phase from requirements through retirement. *(Implements RMiT 10.5; ISO/IEC 27002:2022 control 8.25.)*

### 4.2 Application security requirements

- **4.2.1** Security requirements **shall** be defined for every application from data classification, threat modelling, and regulatory requirements. *(Implements RMiT 10.5; ISO/IEC 27002:2022 control 8.26.)*

### 4.3 Threat modelling and secure design

- **4.3.1** Threat modelling **shall** be performed for new systems and material changes handling Confidential or higher data. *(Implements ISO/IEC 27002:2022 control 8.27.)*

### 4.4 Secure coding

- **4.4.1** Developers **shall** apply approved secure coding standards. SAST and SCA **shall** run in CI pipelines; findings exceeding agreed thresholds **shall** block release. *(Implements ISO/IEC 27002:2022 control 8.28; RMiT 10.14.)*

### 4.5 Testing

- **4.5.1** Security testing **shall** include SAST, SCA, DAST, and (for material systems and at least annually for internet-facing systems) independent penetration testing. *(Implements RMiT 10.8, 10.9; ISO/IEC 27002:2022 control 8.29.)*

### 4.6 Source code review

- **4.6.1** Critical systems **shall** be subject to source code review per RMiT 10.10.

### 4.7 Environment segregation

- **4.7.1** Development, test, and production environments **shall** be logically and access-segregated. Production data **shall not** be used in non-production environments without anonymisation or strong access control. *(Implements RMiT 10.7; ISO/IEC 27002:2022 control 8.31.)*

### 4.8 Outsourced development

- **4.8.1** Outsourced development **shall** be subject to the same secure development requirements as in-house development, with contractual obligations per [POL-19 Supplier and Third-Party Security Policy](POL-19-supplier-security-policy.md). *(Implements ISO/IEC 27002:2022 control 8.30; RMiT 10.12.)*

### 4.9 Source code protection

- **4.9.1** Source code repositories **shall** enforce access control, branch protection, mandatory code review for production-bound changes, and signed commits where technically supported.

### 4.10 Secrets management

- **4.10.1** Secrets (credentials, tokens, keys) **shall not** be committed to source code or configuration files. Secrets **shall** be managed through an approved secrets management platform.

### 4.11 Third-party software supply chain

- **4.11.1** Third-party software components **shall** be tracked through SBOM and assessed for vulnerabilities per RMiT 10.15.

### 4.12 Shariah review for product systems

- **4.12.1** Development affecting Islamic finance product systems **shall** include Shariah Committee review of Shariah-compliance logic per the BNM Shariah Governance Framework before production deployment.

### 4.13 Digital services minimum controls

- **4.13.1** Customer-facing digital services **shall** meet the BNM RMiT Section 12 and Appendices 2, 3 minimum security controls for delivery channels and for authentication/authorisation.

## 5. Roles and responsibilities

| Role | R | A | C | I |
|---|---|---|---|---|
| Risk Management Committee | | A | | |
| Head of Engineering | A | | C | |
| CISO | | A (security testing, secure design) | C | |
| Application security team | R | | C | I |
| Development teams | R | | | I |
| Shariah Committee | | | C (product systems) | I |

## 6. Exceptions

Per TRMF Section 12.

## 7. Enforcement

Per TRMF Section 12. Unapproved deployment to production is a control failure.

## 8. Related documents

- **Parent framework:** [TRMF](../01-frameworks/TRMF.md); [CRMF](../01-frameworks/CRMF.md)
- **Related policies:** [POL-07 Change Management Policy](POL-07-change-management-policy.md); [POL-12 Cryptography Policy](POL-12-cryptography-policy.md); [POL-19](POL-19-supplier-security-policy.md); [POL-21 AI Acceptable Use Policy](POL-21-ai-acceptable-use-policy.md)

## 9. References

- BNM RMiT, 28 November 2025: Section 10.4–10.16; Section 12; Appendices 2, 3
- COBIT 2019 — BAI03; BAI02
- ITIL 4 — Software Development and Management practice
- ISO/IEC 27002:2022 — controls 8.25–8.31
- OWASP ASVS — Application Security Verification Standard
- NIST SP 800-218 — Secure Software Development Framework
- BNM Shariah Governance Framework

## 10. Document control

| Version | Date | Author | Reviewer | Approver | Change summary |
|---|---|---|---|---|---|
| 1.0 | [Effective] | Head of Engineering + CISO | RMC | RMC | Initial Effective version |
