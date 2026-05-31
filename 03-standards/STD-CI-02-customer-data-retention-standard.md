# STD-CI-02 — Customer Data Retention Standard

| | |
|---|---|
| **Document ID** | STD-CI-02 | **Version** | 1.0 |
| **Owner / Approver** | DPO + Legal / DPO |
| **Parent policy** | [POL-CI-01](../02-policies/POL-CI-01-customer-data-protection-policy.md) | **Parent framework** | [CIMF](../01-frameworks/CIMF.md) |
| **Additional anchors** | BNM MCIPD; PDPA Section 10; BNM record-keeping requirements; AMLA |

## 1. Purpose
Specify retention periods for customer data by category, with regulatory basis.

## 2. Scope
All customer data held by GIBB.

## 3. Retention schedule

| Data category | Retention period | Regulatory basis |
|---|---|---|
| Customer identity / KYC documentation | 7 years post-relationship closure | AMLA + BNM AML/CFT PD |
| Account opening records | 7 years post-account closure | BNM record-keeping; AMLA |
| Account transaction records | 7 years per transaction | BNM record-keeping; FSA/IFSA 2013 |
| Customer financial statements / reports issued | 7 years | BNM record-keeping |
| Customer correspondence (formal disputes) | 7 years post-resolution | BNM record-keeping + legal |
| Customer correspondence (general) | 3 years | Operational + dispute window |
| Customer authentication data (passwords hashed; MFA factor metadata) | 7 years post-change | Audit + forensic |
| Customer call recordings | 90 days default; 7 years if regulatory / dispute flag | Customer consent + dispute window |
| Customer behavioural / analytics data | 7 years if linked to transactions; 3 years otherwise | Per use case |
| Marketing consent records | Until withdrawal + 2 years (dormancy) | PDPA consent record retention |
| Shariah Committee deliberation records (touching customer) | Permanent | BNM SGF |
| Customer biometric templates | Per consent + 7 years post-relationship | PDPA + BNM authentication-related |
| Personal data subject to data subject access request | Per response retention; 3 years post-DSR | PDPA Section 30-37 audit |
| AML/CFT alerts (raised on customer) | Per AML/CFT PD (typically 7 years) | AMLA |

## 4. Destruction
Per [POL-15 Section 3.7](../02-policies/POL-15-physical-and-environmental-security-policy.md); secure destruction at end of retention; certificate of destruction retained.

## 5. Legal hold
Where data is under legal hold (litigation, regulator demand), retention extended until release of hold per General Counsel.

## 6. Exceptions
Reduced retention requires DPO + CCO + Legal joint approval; never below statutory minimum.

## 7. Related documents
[POL-CI-01](../02-policies/POL-CI-01-customer-data-protection-policy.md); [STD-CI-01](STD-CI-01-customer-data-classification-standard.md); [POL-11](../02-policies/POL-11-data-classification-policy.md); [REG-ROPA](../06-registers/REG-ROPA-records-of-processing-activity.md); SOP-DG-03 Data Destruction SOP

## 8. References
PDPA 2010 Section 10; AMLA 2001; FSA 2013; IFSA 2013; BNM MCIPD; BNM AML/CFT PD; BNM record-keeping requirements; BNM SGF.

## 9. Document control
| Version | Date | Author | Approver | Change |
|---|---|---|---|---|
| 1.0 | [Effective] | DPO + Legal | DPO | Initial |
