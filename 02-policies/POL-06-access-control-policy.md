# Access Control Policy

| | |
|---|---|
| **Document ID** | POL-06 |
| **Layer** | Policy (Tier 1) |
| **Owner** | CISO |
| **Approver** | Risk Management Committee |
| **Classification** | Internal |
| **Version** | 1.0 |
| **Effective date** | 2026-02-01 |
| **Next review** | 2027-02-01 (annual) |
| **ISO/IEC 27002:2022 controls** | 5.15 (Access control), 5.16 (Identity management), 5.17 (Authentication information), 5.18 (Access rights), 8.2 (Privileged access rights), 8.3 (Information access restriction), 8.4 (Access to source code), 8.5 (Secure authentication) |
| **BNM RMiT (28 Nov 2025)** | Section 10.53 (Access Control Policy); Section 10.54 (Access Control Principles); Section 10.55 (Multi-Factor Authentication); Section 10.56 (User Access Matrix); Section 10.57 (Access Monitoring and Logging) |
| **Parent framework(s)** | [CRMF](../01-frameworks/CRMF.md) |
| **COBIT objective(s)** | APO13 Managed Security; DSS05 Managed Security Services |

> This is the **first fully drafted policy** in this repo. It is the parent of the Access Control worked cascade — see the related documents in Section 9.

---

## 1. Purpose

To define how access to GIBB's information assets is granted, managed, reviewed, and revoked. The policy ensures that access is granted on a least-privilege, role-based basis, that authentication is appropriate to the risk, and that privileged access in particular is tightly controlled, monitored, and reviewed.

Access control is the single most consequential control domain in financial services. Most data breaches, insider incidents, and material fraud cases trace back to access that was excessive, not revoked, or insufficiently authenticated. The principles in this policy are therefore mandatory across the organisation and across the lifecycle of every system, account, and credential.

## 2. Scope

**Applies to:**

- All GIBB information systems, applications, services, infrastructure, and physical premises.
- All identities (human and non-human / machine / service accounts).
- All access mechanisms (interactive logon, programmatic API access, federated SSO, VPN, physical access).
- All personnel categories (employees, contractors, secondees, third parties, customers where they have privileged-equivalent access).

**Does not apply to:**

- Public-facing internet content with no authentication (the Acceptable Use Policy and the Operations Security Policy apply).
- Read access by the data subject to their own data through customer-facing channels (governed by the Data Classification & Handling Policy and the Personal Data Protection Act 2010).

## 3. Definitions

| Term | Definition |
|---|---|
| **Access** | The ability to use, modify, view, or otherwise interact with an information asset. |
| **Identity** | A digital representation of a person, system, or service that can be authenticated. |
| **Authentication** | The process of verifying that a claimed identity is genuine. |
| **Authorisation** | The process of determining what an authenticated identity is permitted to do. |
| **Least privilege** | The principle that an identity is granted only the access required to perform its function, and no more. |
| **Role-Based Access Control (RBAC)** | An authorisation model where access is granted to roles, and identities are assigned to roles. |
| **Privileged access** | Access that confers elevated rights — administrative, root, super-user, security-administrator, or access to data classified Confidential or above in bulk. |
| **Privileged Access Management (PAM)** | A class of technical control providing brokered, recorded, time-bound privileged access through a vault. |
| **Joiner / Mover / Leaver (JML)** | The lifecycle of an identity: created on joining, modified on internal role change, revoked on leaving. |
| **Service account** | A non-human identity used by a system or process. |
| **Segregation of Duties (SoD)** | The principle that no single identity holds combinations of access that would allow unauthorised, fraudulent, or undetected activity. |

## 4. Policy statements

### 4.1 Identity lifecycle

- **4.1.1** Every identity shall be uniquely attributable to a person or a system. Shared interactive accounts are prohibited. *(Implements ISO/IEC 27002:2022 control 5.16; BNM RMiT Section 10.54 (Access Control Principles).)*
- **4.1.2** Identity creation, modification, and revocation shall be triggered by an authoritative source — Workday for employees and contractors, the supplier-relationship system for third parties, and the configuration management system for non-human identities.
- **4.1.3** Identity provisioning and de-provisioning shall be executed through the [Joiner / Mover / Leaver SOP](../04-procedures/SOP-AC-01-joiner-mover-leaver-sop.md). On termination, all access shall be disabled within the timelines defined in [STD-AC-01](../03-standards/STD-AC-01-password-and-authentication-standard.md). *(Implements ISO/IEC 27002:2022 control 5.16; BNM RMiT Section 10.53 (Access Control Policy); Section 10.56 (User Access Matrix).)*
- **4.1.4** Dormant accounts (no successful interactive logon for 60 days for human accounts, 90 days for service accounts unless documented exception) shall be automatically disabled and reviewed for revocation. *(Implements ISO/IEC 27002:2022 control 5.18.)*

### 4.2 Authorisation and least privilege

- **4.2.1** Access shall be granted on a **least-privilege**, **role-based** basis. Direct, identity-level entitlements outside an approved role are prohibited except via documented exception. *(Implements ISO/IEC 27002:2022 controls 5.15, 5.18; BNM RMiT Section 10.54 (Access Control Principles); Section 10.56 (User Access Matrix).)*
- **4.2.2** Every role shall have a named role owner (typically the business application owner) who is accountable for the entitlements bundled into that role.
- **4.2.3** Segregation of Duties conflicts shall be identified, documented in an SoD matrix per application, and prevented in provisioning. Where business need requires an SoD-conflicting combination, the residual risk shall be approved by the Risk Management Committee, with a compensating detective control. *(Implements ISO/IEC 27002:2022 control 5.3.)*
- **4.2.4** Source code repositories shall enforce least privilege on read and write, with branch protection and required code review for production-bound branches. *(Implements ISO/IEC 27002:2022 control 8.4.)*

### 4.3 Authentication

- **4.3.1** Authentication strength shall be commensurate with the sensitivity of the asset and the risk of the access channel. Quantified requirements are specified in [STD-AC-01 Password & Authentication Standard](../03-standards/STD-AC-01-password-and-authentication-standard.md). *(Implements ISO/IEC 27002:2022 controls 5.17, 8.5.)*
- **4.3.2** Multi-Factor Authentication (MFA) is **mandatory** for: all remote access; all access to internet-facing administrative interfaces; all privileged access; all access to systems processing Confidential or Highly Restricted data. *(Implements ISO/IEC 27002:2022 control 8.5; BNM RMiT Section 10.55 (Multi-Factor Authentication).)*
- **4.3.3** Authentication factors shall include a phishing-resistant factor (FIDO2 / WebAuthn or smart card) for privileged access. SMS one-time passwords shall not be used as a factor for privileged access. *(Implements ISO/IEC 27002:2022 control 8.5; BNM RMiT Section 10.55; aligned with NIST SP 800-63B AAL3 guidance.)*
- **4.3.4** Passwords shall conform to the requirements in [STD-AC-01](../03-standards/STD-AC-01-password-and-authentication-standard.md), be stored only in hashed form using an approved algorithm, and never transmitted in clear over untrusted networks.

### 4.4 Privileged access

- **4.4.1** Privileged accounts shall be **distinct** from standard user accounts of the same person. Day-to-day work shall not be performed under a privileged account. *(Implements ISO/IEC 27002:2022 control 8.2; BNM RMiT Section 10.54 (Access Control Principles); Section 10.56 (User Access Matrix).)*
- **4.4.2** All privileged access shall be brokered through a **Privileged Access Management (PAM)** platform, with session recording, time-bound check-out, and credential vaulting. *(Implements ISO/IEC 27002:2022 control 8.2; BNM RMiT Section 10.54; Section 10.57 (Access Monitoring and Logging).)*
- **4.4.3** Privileged sessions shall be logged with sufficient detail to reconstruct activity, with logs centrally collected and retained per [POL-16 Operations Security Policy](POL-16-operations-security-policy.md).
- **4.4.4** Privileged access grants shall be **time-bound** by default (just-in-time access), with standing privileged access requiring documented justification and re-approval annually.
- **4.4.5** Privileged access entitlements shall be **reviewed quarterly** by the asset owner and recorded in the [Privileged Access Review Register](../06-registers/REG-PAR-privileged-access-review-register.md). *(Implements ISO/IEC 27002:2022 control 5.18.)*

### 4.5 Non-human identities

- **4.5.1** Service accounts shall be: (a) uniquely named, (b) assigned to a named human owner accountable for them, (c) restricted to the minimum permissions required for the specific function, (d) credentials rotated per [STD-AC-01](../03-standards/STD-AC-01-password-and-authentication-standard.md).
- **4.5.2** Service-account credentials shall be stored in a secrets management platform, not in source code, configuration files, or shared drives.
- **4.5.3** Interactive logon by service accounts shall be disabled where technically feasible.

### 4.6 Customer access

- **4.6.1** Customer authentication to digital banking channels shall conform to the BNM RMiT requirements for digital services (Section 12), including the minimum security controls for delivery channels and for authentication/authorisation set out in **Appendices 2 and 3**, and the standards issued by the CISO for the customer authentication platform.
- **4.6.2** Customer access mechanisms shall be subject to the same threat-modelling and secure design requirements as internal systems, per [POL-17 Secure Development Policy](POL-17-secure-development-policy.md).

### 4.7 Physical access

- **4.7.1** Physical access to data centres, network closets, and secure work areas shall be controlled, logged, and reviewed in accordance with [POL-15 Physical & Environmental Security Policy](POL-15-physical-and-environmental-security-policy.md). *(Implements ISO/IEC 27002:2022 controls 7.2, 7.3.)*

### 4.8 Monitoring and detection

- **4.8.1** Authentication events, privileged session activity, and access entitlement changes shall be logged centrally and monitored for indicators of compromise. *(Implements ISO/IEC 27002:2022 controls 5.18, 8.15, 8.16; BNM RMiT Section 10.57 (Access Monitoring and Logging); Section 11.9 (Continuous Security Monitoring and SOC); Section 11.10 (Cyber Threat Intelligence); Section 11.11 (Anomalous Activity Response).)*
- **4.8.2** Anomalous access patterns shall trigger investigation per the [Incident Triage SOP](../04-procedures/SOP-IR-01-incident-triage-sop.md).

## 5. Roles and responsibilities

| Role | R | A | C | I |
|---|---|---|---|---|
| Risk Management Committee | | A | | I |
| CISO | A | | | |
| Head of Identity & Access Management | R | | C | I |
| Application owners | R | | C | I |
| Line managers | R | | C | I |
| Human Resources | R | | | I |
| Internal Audit | | | C | I |

R = Responsible · A = Accountable · C = Consulted · I = Informed.

**Specific accountabilities:**

- **CISO** — Accountable for this policy, the access control standards, and the operating model.
- **Head of IAM** — Responsible for the identity, authentication, authorisation, and PAM platforms; for executing the JML SOP; for running the quarterly privileged access reviews.
- **Application owners** — Define the roles, role-entitlement mappings, and SoD matrices for their applications; recertify access quarterly.
- **Line managers** — Initiate access requests for their reports; recertify access for their reports quarterly; report leaver events without delay.
- **HR** — Operate the authoritative joiner/mover/leaver source; ensure trigger events flow without delay.

## 6. Exceptions

Any deviation from this policy shall be documented in the Exception Register, approved by the CISO (or the Risk Management Committee for material residual risk), time-bound to a maximum of 12 months (renewable once), and accompanied by a compensating control.

Examples of access patterns that require an exception:

- A standing privileged account that cannot be time-bound (technical limitation of legacy system).
- Shared accounts that cannot be split (vendor-imposed limitation).
- Direct identity-level entitlements outside an approved role.
- Service accounts with interactive logon enabled.

## 7. Enforcement

Violations of this policy may result in disciplinary action up to and including termination of employment or contract, and where applicable, civil or criminal proceedings under the Computer Crimes Act 1997.

## 8. Related documents

- **Parent:** [POL-04 Information Security Policy](POL-04-information-security-policy.md)
- **Supporting standards:**
  - [STD-AC-01 Password & Authentication Standard](../03-standards/STD-AC-01-password-and-authentication-standard.md)
- **Supporting procedures:**
  - [SOP-AC-01 Joiner / Mover / Leaver SOP](../04-procedures/SOP-AC-01-joiner-mover-leaver-sop.md)
- **Related registers:**
  - [REG-PAR Privileged Access Review Register](../06-registers/REG-PAR-privileged-access-review-register.md)

## 9. References

- ISO/IEC 27001:2022 — Information security management systems — Requirements.
- ISO/IEC 27002:2022 — Information security controls (5.3, 5.15–5.18, 8.2–8.5).
- NIST SP 800-63B — Digital Identity Guidelines: Authentication and Lifecycle Management (informative reference for authentication assurance levels).
- Bank Negara Malaysia, *Risk Management in Technology (RMiT)*, **issued 28 November 2025** — Section 10.53–10.57 (Access Control); Section 12 with Appendices 2 and 3 (Digital Services delivery channels and authentication minimum controls).
- Computer Crimes Act 1997 (Malaysia).
- [Regulatory Mapping Reference](../00-foundations/regulatory-mapping-reference.md).

## 10. Document control

| Version | Date | Author | Reviewer | Approver | Change summary |
|---|---|---|---|---|---|
| 0.1–0.9 | 2025-11-20 → 2026-01-10 | CISO | Technology Risk, IAM, Internal Audit | — | Drafting cycle |
| 1.0 | 2026-01-15 | CISO | Risk Management Committee | Risk Management Committee | Initial Effective version. Approved by RMC (minutes 2026-01-15, agenda item 6.1). |

---

## v2 re-anchoring (2026-05-28)

This document was re-anchored as part of the v2 build (Session 5) per [DEC-001](../_context/decisions.md). Substantive content preserved from the v1 snapshot at [`../v1/`](../v1/). Changes applied:

- Document ID updated to v2 numbering convention
- **Parent framework(s)** and **COBIT objective(s)** added to metadata block
- Bank name normalised from "General Bank" to **GIBB** (General Islamic Bank Berhad)
- Internal cross-references migrated from v1 paths to v2 paths
- v1 sister-document references updated to v2 document IDs

Pending formal GIBB approval under v2. The Effective and Next review dates above are inherited from the v1 1.x lifecycle and will be updated when this document is approved under v2 governance.
