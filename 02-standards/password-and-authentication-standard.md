# Password & Authentication Standard

| | |
|---|---|
| **Document ID** | STD-02-01 |
| **Layer** | Standard (Tier 2) |
| **Owner** | CISO |
| **Approver** | CISO |
| **Classification** | Internal |
| **Version** | 1.0 |
| **Effective date** | 2026-02-01 |
| **Next review** | 2027-02-01 (annual or on material technology change) |
| **Implements policy** | [POL-02 Access Control Policy](../01-policies/02-access-control-policy.md) |
| **ISO/IEC 27002:2022 controls** | 5.17 (Authentication information), 8.2 (Privileged access rights), 8.5 (Secure authentication) |
| **BNM RMiT** | Appendix 6 (Access Control) |

---

## 1. Purpose

This standard operationalises the authentication requirements in [POL-02 Access Control Policy](../01-policies/02-access-control-policy.md). It specifies the **measurable, mandatory** requirements for passwords, multi-factor authentication, session controls, account lifecycle thresholds, and authentication of non-human identities. It is the single source of truth for "how strong must our authentication be?" across General Bank.

## 2. Scope

All authentication to General Bank information systems, applications, and services, including:

- Workforce access (employees, contractors, third parties) via SSO, application, VPN, and direct logon.
- Privileged access via interactive logon, PAM brokered sessions, jump hosts, and emergency break-glass.
- Non-human / service / machine identities.
- Customer authentication is governed by separate standards aligned with BNM RMiT Appendix 8 (Security of Digital Services); requirements below apply where customer-facing systems have administrative interfaces accessed by workforce.

## 3. Requirements

### 3.1 Account types and authentication strength

| Account type | Minimum factors | Phishing-resistant factor required? | Notes |
|---|---|---|---|
| Standard workforce account | Password + MFA (any approved factor) | No (recommended) | SSO-federated. |
| Privileged account (any tier) | Password + MFA — phishing-resistant | **Yes** | FIDO2/WebAuthn or smart card; SMS OTP prohibited. |
| Domain Admin / equivalent (Tier 0) | Password + MFA — phishing-resistant + dedicated admin workstation | **Yes** | PAW (Privileged Access Workstation) mandatory. |
| Service account (interactive logon disabled) | Credential vault + scoped permission | n/a | Interactive logon must be disabled where feasible. |
| Service account (interactive logon required for legacy reasons) | Password + MFA where supported; documented exception otherwise | Yes where MFA supported | Exception required; quarterly review. |
| Break-glass / emergency account | Password (long, vaulted, multi-custodian) + MFA + workflow approval | Yes | Use generates SEV-2 incident automatically. |

### 3.2 Password requirements

| Ref | Requirement | Measurement / evidence |
|---|---|---|
| 3.2.1 | Standard workforce account passwords **shall** be a minimum of 14 characters. | Policy enforcement in IDP / directory; quarterly evidence extract. |
| 3.2.2 | Privileged account passwords **shall** be a minimum of 16 characters and **shall** be machine-generated. | PAM configuration; quarterly extract. |
| 3.2.3 | Passwords **shall not** be reused across the last 12 passwords for the same account. | IDP history configuration. |
| 3.2.4 | Passwords **shall** be checked against known compromised-password lists (e.g., HIBP Pwned Passwords API) at set and at periodic rotation. | IDP configuration; quarterly attestation. |
| 3.2.5 | Standard workforce passwords **shall** be rotated only on **suspicion of compromise** (aligned with NIST SP 800-63B guidance). Forced periodic rotation alone is not required. | IDP configuration. |
| 3.2.6 | Privileged account passwords managed by PAM **shall** be rotated automatically per use or at least every 24 hours, whichever is more frequent. | PAM logs. |
| 3.2.7 | Passwords **shall not** be transmitted, stored, or displayed in clear text. Stored passwords **shall** use approved hashing (Argon2id, bcrypt with appropriate cost factor, or PBKDF2-HMAC-SHA-256 with ≥ 600,000 iterations as minimum acceptable). | Code review; security testing; vendor attestation for SaaS. |
| 3.2.8 | Initial passwords issued by an administrator **shall** be single-use and require change at first logon. | IDP workflow. |

### 3.3 Multi-factor authentication

| Ref | Requirement | Measurement / evidence |
|---|---|---|
| 3.3.1 | MFA **shall** be required for: all remote access (VPN, ZTNA, remote desktop); all administrative interfaces of internet-facing systems; all privileged access; all access to systems processing Confidential or Highly Restricted data. | MFA enforcement reports; quarterly attestation. |
| 3.3.2 | Approved MFA factors are: FIDO2/WebAuthn security keys; smart cards; mobile-app push with number-matching; mobile-app TOTP; client certificates. | Approved factor list maintained by CISO. |
| 3.3.3 | **Prohibited as a sole second factor** for privileged or high-sensitivity access: SMS OTP, voice OTP, security questions. | IDP policy. |
| 3.3.4 | Phishing-resistant MFA (FIDO2/WebAuthn or smart card) **shall** be the only approved factor for Tier 0 administrative access. | IDP / PAM configuration. |
| 3.3.5 | MFA fatigue protection (number-matching, rate limiting, anomaly detection) **shall** be enabled for push-based MFA. | IDP configuration. |

### 3.4 Session management

| Ref | Requirement | Measurement / evidence |
|---|---|---|
| 3.4.1 | Interactive workforce sessions **shall** be re-authenticated after 12 hours of inactivity or 8 hours of continuous session, whichever is sooner. | IDP session policy. |
| 3.4.2 | Privileged sessions brokered through PAM **shall** be limited to a maximum of 4 hours per check-out, with re-check-out required thereafter. | PAM configuration. |
| 3.4.3 | Customer-facing sessions handling financial transactions **shall** comply with the Digital Banking Authentication Standard (separate document under POL-12). | n/a in this standard. |
| 3.4.4 | Concurrent active sessions for the same account **shall** be detected and alerted where unusual. | SIEM use case. |

### 3.5 Account lifecycle thresholds

| Ref | Requirement | Measurement / evidence |
|---|---|---|
| 3.5.1 | Identity creation **shall** complete within 1 business day of authoritative HR trigger. | JML SOP metrics. |
| 3.5.2 | Identity modification (role change) **shall** complete within 2 business days of authoritative HR trigger. | JML SOP metrics. |
| 3.5.3 | Identity disablement on termination **shall** complete: workforce — within **2 hours** of HR trigger; high-risk leavers (e.g., privileged users, dismissals) — within **30 minutes** of HR trigger. | JML SOP metrics; quarterly extract. |
| 3.5.4 | Dormant accounts (no successful interactive logon): workforce accounts disabled after **60 days**; service accounts reviewed after **90 days**. | IDP scheduled job + quarterly extract. |
| 3.5.5 | Account lock-out **shall** occur after **5 consecutive failed authentication attempts** in a **15-minute** window, with progressive back-off thereafter. | IDP configuration. |

### 3.6 Service-account credential management

| Ref | Requirement | Measurement / evidence |
|---|---|---|
| 3.6.1 | Service-account credentials **shall** be stored in an approved secrets management platform. | Code-scanning for secrets; quarterly attestation. |
| 3.6.2 | Service-account passwords **shall** be rotated at least every **90 days** for accounts supporting rotation; for those that do not, the underlying technology limitation **shall** be documented and a remediation plan tracked. | Secrets management reports. |
| 3.6.3 | Service accounts **shall not** have interactive logon enabled where technically feasible. | Directory configuration; exception register. |

### 3.7 Break-glass / emergency access

| Ref | Requirement | Measurement / evidence |
|---|---|---|
| 3.7.1 | Each Tier-0 system **shall** have a documented break-glass procedure with at least **two named human custodians** of credential parts (split-knowledge) and a workflow-controlled retrieval process. | Break-glass procedure per Tier-0 system. |
| 3.7.2 | Any use of a break-glass credential **shall** automatically generate a **SEV-2 incident** triggering review per [SOP-08-01 Incident Triage SOP](../03-procedures/incident-triage-sop.md). | SIEM use case; Incident Register entries. |

## 4. Exceptions

Exceptions to this standard shall be approved by the CISO, logged in the Exception Register, time-bound to a maximum of 12 months (renewable once), and accompanied by a compensating control. Exceptions extending beyond a further 12 months require Risk Management Committee approval.

## 5. Related documents

- **Parent policy:** [POL-02 Access Control Policy](../01-policies/02-access-control-policy.md)
- **Implementing procedures:** [SOP-02-01 Joiner / Mover / Leaver SOP](../03-procedures/joiner-mover-leaver-sop.md)
- **Related registers:** [REG-PAR Privileged Access Review Register](../05-registers/privileged-access-review-register.md)

## 6. References

- ISO/IEC 27002:2022 — controls 5.17, 8.2, 8.5.
- NIST SP 800-63B — Digital Identity Guidelines (informative reference for authentication assurance levels and password guidance).
- FIDO Alliance — FIDO2/WebAuthn specifications.
- Bank Negara Malaysia, *Risk Management in Technology (RMiT)*, Appendix 6 (Access Control).

## 7. Document control

| Version | Date | Author | Reviewer | Approver | Change summary |
|---|---|---|---|---|---|
| 1.0 | 2026-01-20 | CISO | Technology Risk, IAM | CISO | Initial Effective version. |
| 1.1 | 2026-04-22 | ISMS Manager | CISO | CISO | Minor — updated example PAM vendor reference; clarified service-account rotation language. No "shall" changes. |
