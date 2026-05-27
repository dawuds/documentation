# SOP-CI-01 — Data Subject Access Request (DSAR) SOP

| | |
|---|---|
| **Document ID** | SOP-CI-01 | **Version** | 1.0 |
| **Owner / Approver** | DPO |
| **Parent policy** | [POL-CI-01 §4.4](../02-policies/POL-CI-01-customer-data-protection-policy.md) | **Parent framework** | [CIMF](../01-frameworks/CIMF.md) |
| **Implements** | PDPA 2010 Sections 30–37 |

## 1. Purpose
Respond to customer DSARs (access, correction, consent withdrawal) within PDPA statutory timeframes.

## 2. Trigger
DSAR received via any channel — branch, online form, email, letter, telephone.

## 3. Procedure

| # | Actor | Action | SLA |
|---|---|---|---|
| 1 | Customer-facing channel | Receive DSAR; route to DPO inbox | Same business day |
| 2 | DPO Operations | Log in [REG-DSR](../06-registers/REG-DSR-data-subject-request-register.md) with received date | Same day |
| 3 | DPO Operations | Verify customer identity per agreed verification protocol (more rigorous than routine service identification) | ≤ 5 business days |
| 4 | DPO Operations | Classify request type: Access / Correction / Consent withdrawal / Other | At identification |
| 5 | DPO Operations | For Access: collect data from all relevant systems per [REG-DA](../06-registers/REG-DA-data-asset-register.md) and [REG-ROPA](../06-registers/REG-ROPA-records-of-processing-activity.md) | ≤ 14 business days |
| 6 | DPO Operations | For Correction: validate proposed correction; effect across systems | ≤ 14 business days |
| 7 | DPO Operations | For Consent withdrawal: update consent registers; cascade to marketing and other systems | ≤ 7 business days |
| 8 | DPO | Review response before issue; identify any redactions or refusals with statutory basis | Pre-issue |
| 9 | DPO Operations | Issue response to customer through verified channel | Within statutory deadline (typically 21 days for access) |
| 10 | DPO Operations | Update [REG-DSR](../06-registers/REG-DSR-data-subject-request-register.md) with outcome and SLA met flag | At closure |

## 4. Refusal handling
Refusal must have statutory basis under PDPA. Customer informed of basis + right to escalate to PDPA Commissioner. Refusal recorded in REG-DSR.

## 5. Complex requests
Complex DSARs may extend timeline up to additional 14 days with customer notification within original deadline. Complexity determination by DPO; documented.

## 6. Exception handling
Customer-identity-verification failure: do not process; notify customer of verification requirement. Multiple repeat requests (potential abuse): consult Legal.

## 7. Evidence
REG-DSR entry; response copy; statutory basis documentation if refusal. Retained 3 years post-closure per [STD-CI-02](../03-standards/STD-CI-02-customer-data-retention-standard.md).

## 8. Document control
| Version | Date | Author | Approver | Change |
|---|---|---|---|---|
| 1.0 | [Effective] | DPO | DPO | Initial |
