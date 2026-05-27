# SOP-NC-01 — NACSA Incident Notification SOP

| | |
|---|---|
| **Document ID** | SOP-NC-01 | **Version** | 1.0 |
| **Owner / Approver** | CCO + CISO |
| **Parent standard** | [STD-NC-01](../03-standards/STD-NC-01-nacsa-notification-standard.md) | **Parent policy** | [POL-23](../02-policies/POL-23-ncii-operational-policy.md) |

## 1. Purpose
Operationalise NACSA incident notification for NCII-scope cyber incidents.

## 2. Trigger
Cyber incident affecting GIBB systems within NCII scope, classified per [STD-IR-01](../03-standards/STD-IR-01-incident-classification-and-severity-standard.md), passing the NACSA notification threshold per [STD-NC-01](../03-standards/STD-NC-01-nacsa-notification-standard.md).

## 3. Procedure

| # | Actor | Action | Tool | Output | SLA |
|---|---|---|---|---|---|
| 1 | Incident Commander (from [SOP-IR-01](SOP-IR-01-incident-triage-sop.md)) | Flag NCII-scope at incident declaration | Incident system | NCII flag set | At declaration |
| 2 | CISO | Engage CCO; confirm NCII scope | Secure channel | CCO engaged | Within 30 min of declaration |
| 3 | CCO | Determine NACSA notification per [STD-NC-01 §3.1](../03-standards/STD-NC-01-nacsa-notification-standard.md) | Triage decision | Notification go/no-go | Within 1 hour of engagement |
| 4 | CCO + CISO | Prepare notification per [STD-NC-01 §3.3](../03-standards/STD-NC-01-nacsa-notification-standard.md) content requirements | Notification template | Draft notification | Within timeline |
| 5 | CCO (delegate during off-hours) | Approve notification | Sign-off | Approval | ≤ 30 min from draft |
| 6 | CCO | Submit via NACSA-prescribed channel per [STD-NC-01 §3.4](../03-standards/STD-NC-01-nacsa-notification-standard.md) | NACSA portal/channel | Submission with timestamp | Per NACSA SLA |
| 7 | CCO | Record in [REG-NCN](../06-registers/REG-NCN-nacsa-notification-register.md); attach acknowledgement when received | REG-NCN | Entry created | Within 30 min of submission |
| 8 | CCO + CISO | If NACSA requests additional info: respond per timeline | Per NACSA channel | Response | Per request |
| 9 | CCO | Coordinate parallel BNM notification per [POL-13 §4.4.3](../02-policies/POL-13-incident-management-policy.md) — independent of NACSA submission | Per BNM channel | BNM notification | Per BNM SLA |

## 4. Exception handling
Primary channel outage: use backup channel per [STD-NC-01 §3.4.2](../03-standards/STD-NC-01-nacsa-notification-standard.md). CCO unavailable: Deputy CCO; thereafter CISO with retrospective CCO sign-off.

## 5. Evidence
Notification content; NACSA acknowledgement; REG-NCN entry; any subsequent NACSA correspondence. Retained per [STD-NC-01 §3.4.3](../03-standards/STD-NC-01-nacsa-notification-standard.md).

## 6. Document control
| Version | Date | Author | Approver | Change |
|---|---|---|---|---|
| 1.0 | [Effective] | CCO + CISO | CCO | Initial |
