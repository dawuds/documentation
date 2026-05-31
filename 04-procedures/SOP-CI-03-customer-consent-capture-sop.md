# SOP-CI-03 — Customer Consent Capture SOP

| | |
|---|---|
| **Document ID** | SOP-CI-03 | **Version** | 1.0 |
| **Owner / Approver** | DPO |
| **Parent policy** | [POL-CI-01 Section 4.1](../02-policies/POL-CI-01-customer-data-protection-policy.md) | **Parent framework** | [CIMF](../01-frameworks/CIMF.md) |
| **Implements** | PDPA 2010 consent requirements |

## 1. Purpose
Operationalise PDPA-compliant consent capture, storage, and withdrawal across GIBB customer touchpoints.

## 2. Trigger
- New customer onboarding
- New product or service requiring additional consent
- Customer consent withdrawal request
- Periodic consent refresh (where required)

## 3. Procedure — new consent capture

| # | Actor | Action | Output |
|---|---|---|---|
| 1 | Customer-facing system | Present consent notice with: purpose, data categories, recipients, retention, withdrawal mechanism | Notice display logged |
| 2 | Customer | Provide consent (active opt-in for non-essential processing) | Consent record |
| 3 | System | Record in consent register with timestamp, version of notice, customer ID, channel, consent items granted | Persistent record |
| 4 | System | Cascade consent to dependent systems (CRM, marketing, analytics) | Cascade confirmation |

## 4. Procedure — consent refresh
For long-term consent-based processing, customer offered refresh periodically (e.g., every 2-3 years) per notice. Refresh treated as new consent capture.

## 5. Procedure — consent withdrawal
Per [SOP-CI-01 DSAR](SOP-CI-01-dsar-sop.md) — consent withdrawal is a DSAR type. Cascade to all dependent systems within 7 business days.

## 6. Procedure — sensitive personal data
For sensitive personal data per PDPA, additional explicit consent required with enhanced notice; recorded separately.

## 7. Procedure — Shariah-compliant product consent
Islamic finance product consent includes Shariah-product-acceptance affirmation per Shariah Committee approved language. Recorded alongside PDPA consent.

## 8. Evidence
Consent register entries; notice version archive; cascade confirmations. Retained per [STD-CI-02 Section 3](../03-standards/STD-CI-02-customer-data-retention-standard.md) marketing-consent row.

## 9. Document control
| Version | Date | Author | Approver | Change |
|---|---|---|---|---|
| 1.0 | [Effective] | DPO | DPO | Initial |
