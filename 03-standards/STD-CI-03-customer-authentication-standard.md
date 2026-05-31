# STD-CI-03 — Customer Authentication Standard

| | |
|---|---|
| **Document ID** | STD-CI-03 | **Version** | 1.0 |
| **Owner / Approver** | CISO + DPO / CISO |
| **Parent policy** | [POL-CI-01](../02-policies/POL-CI-01-customer-data-protection-policy.md); [POL-06](../02-policies/POL-06-access-control-policy.md) | **Parent framework** | [CIMF](../01-frameworks/CIMF.md); [CRMF](../01-frameworks/CRMF.md) |
| **RMiT clause(s)** | Section 12 (Digital Services); Appendix 3 (authentication minimum controls) |
| **Practice** | NIST SP 800-63B (informative); FIDO Alliance |

## 1. Purpose
Specify customer-side authentication requirements for GIBB digital channels per RMiT Section 12 + Appendix 3.

## 2. Scope
All customer authentication to GIBB digital channels — internet banking, mobile banking, payment authorisation, customer portal, IVR sensitive functions.

## 3. Requirements

### 3.1 Authentication factors
| Service tier | Required factors |
|---|---|
| Account view (read-only) | Password + 2nd factor (push, OTP, biometric) |
| Transaction execution (small value) | Password + 2nd factor + transaction-specific approval |
| Transaction execution (above customer-set threshold or first-time payee) | Strong: device-bound biometric + transaction signing |
| Profile changes (contact details, password) | Strong: 2nd factor + email/SMS confirmation + cool-off period |
| Customer data subject requests | Identity verification per [SOP-CI-01 DSAR SOP](../04-procedures/SOP-CI-01-dsar-sop.md) |

### 3.2 Approved factors
| Factor | Allowed for |
|---|---|
| Password | Knowledge factor (one of) |
| Hardware token | Possession factor |
| Mobile app push with biometric unlock | Possession + inherence |
| TOTP (mobile app) | Possession factor |
| SMS OTP | Limited use — fallback only; not sole 2nd factor for high-value transactions |
| Voice OTP | Limited use — accessibility scenarios only |
| Biometric (fingerprint, face) on device-bound mobile app | Inherence factor; mandatory for high-value |
| FIDO2 / WebAuthn | High-assurance factor for select customers (premium tier) |

### 3.3 Prohibited
- Static PIN as sole 2nd factor for transactions above threshold
- Plain-text email of credentials
- SMS OTP for password reset of customers with mobile-app option

### 3.4 Session management
Active session timeout: 5 minutes inactivity for internet banking; 2 minutes for transaction-signing context. Maximum continuous session: 30 minutes for IB; lower for transaction context.

### 3.5 Step-up authentication
Triggered by: high-value transaction; first-time payee; profile change; access from new device; access from unusual geography per fraud rules.

### 3.6 Anti-fraud integration
Authentication events feed fraud detection per [AIU-0001 Fraud Detection](../06-registers/REG-AIU-ai-use-case-register.md). Anomalous patterns trigger step-up or rejection.

### 3.7 Customer enrolment
Initial enrolment via documented channel verification (in-person, video KYC, mailed activation). Re-enrolment of credentials requires customer verification per [STD-AC-01 Section 3.2.8](STD-AC-01-password-and-authentication-standard.md) equivalent for customer accounts.

### 3.8 Accessibility
Alternative authentication paths for customers unable to use primary factors (vision-impaired, customers without mobile devices). Authorised by DPO + Head of Customer Operations.

### 3.9 Islamic finance customer authentication
Islamic finance product transactions follow same authentication requirements; transaction signing wording (Ijab/Qabul confirmation) integrated into transaction approval UX per Shariah Committee guidance.

## Appendix A — RMiT Appendix 2 (Delivery Channel Minimum Controls) mapping

| Appendix 2 control area | GIBB control | Implementing reference |
|---|---|---|
| App2-1 Customer registration and onboarding | Documented enrolment via in-person, video KYC, or mailed activation | Section 3.7 |
| App2-2 Customer authentication at login | Risk-based MFA per service tier | Section 3.1 |
| App2-3 Transaction authentication | Transaction signing for transactions above customer-set threshold; first-time-payee step-up | Section 3.1 + Section 3.5 |
| App2-4 Out-of-band confirmation | Mobile-app push with biometric; SMS as fallback only | Section 3.2 |
| App2-5 Device binding | Mobile app device-bound; rebinding requires step-up | Section 3.2 + Section 3.5 |
| App2-6 Session management | 5-min inactivity timeout; 30-min max session; 2-min transaction context | Section 3.4 |
| App2-7 Customer-facing security education | In-app reminders, fraud alerts, awareness messaging | [PLN-07 Section 3](../05-plans/PLN-07-awareness-and-competence-programme.md) (customer-facing channels) |
| App2-8 Fraud monitoring integration | Authentication events feed fraud detection | Section 3.6 |
| App2-9 Account recovery | Multi-channel verification; cool-off period for profile changes | Section 3.1 (profile changes row) |
| App2-10 Logging and forensics | Authentication events logged per [STD-CR-02](STD-CR-02-logging-standard.md); retained per [STD-DG-02](STD-DG-02-data-retention-standard.md) | Cross-ref |

## Appendix B — RMiT Appendix 3 (Authentication Minimum Controls) mapping

| Appendix 3 control area | GIBB control | Implementing reference |
|---|---|---|
| App3-1 Multi-factor authentication for digital banking | MFA mandatory for all digital channels | Section 3.1 |
| App3-2 Phishing-resistant factors for high-value | Device-bound biometric + transaction signing; FIDO2 for premium tier | Section 3.1 + Section 3.2 |
| App3-3 SMS OTP restrictions | Limited use; not sole 2nd factor for high-value; not for password reset where mobile app exists | Section 3.2 + Section 3.3 |
| App3-4 Static credential restrictions | Static PIN prohibited as sole 2nd factor for above-threshold transactions | Section 3.3 |
| App3-5 Step-up triggers | High-value, first-time payee, profile change, new device, geographic anomaly | Section 3.5 |
| App3-6 Customer-set transaction thresholds | Customer-configurable thresholds; defaults set conservatively | Section 3.1 |
| App3-7 Cool-off period for profile changes | Mandatory cool-off; second-channel confirmation | Section 3.1 (profile changes row) |
| App3-8 Strong customer authentication for sensitive functions | Strong authentication mandatory for funds transfer, beneficiary management, profile changes | Section 3.1 |
| App3-9 Credential storage and protection | Hashed (Argon2id / bcrypt); encrypted at rest; biometric data never leaves device-bound secure enclave | [STD-CR-01](STD-CR-01-cryptographic-standard.md) Section 3 |
| App3-10 Accessibility alternative paths | Authorised by DPO + Head of Customer Operations; equivalent assurance maintained | Section 3.8 |

## 4. Exceptions
Per [POL-CI-01](../02-policies/POL-CI-01-customer-data-protection-policy.md). Departures require CISO + DPO + Shariah (if relevant) approval.

## 5. Related documents
[POL-CI-01](../02-policies/POL-CI-01-customer-data-protection-policy.md); [POL-06](../02-policies/POL-06-access-control-policy.md); [STD-AC-01](STD-AC-01-password-and-authentication-standard.md); [STD-CI-01](STD-CI-01-customer-data-classification-standard.md); [SOP-CI-03 Customer Consent Capture SOP](../04-procedures/SOP-CI-03-customer-consent-capture-sop.md)

## 6. References
BNM RMiT 28 Nov 2025 Section 12; Appendix 3; NIST SP 800-63B; FIDO Alliance; PDPA 2010; BNM Shariah Governance Framework.

## 7. Document control
| Version | Date | Author | Approver | Change |
|---|---|---|---|---|
| 1.0 | [Effective] | CISO + DPO | CISO | Initial |
