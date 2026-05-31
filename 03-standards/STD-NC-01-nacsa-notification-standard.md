# STD-NC-01 — NACSA Notification Standard

| | |
|---|---|
| **Document ID** | STD-NC-01 | **Version** | 1.0 |
| **Owner / Approver** | CCO + CISO / CCO |
| **Parent policy** | [POL-23](../02-policies/POL-23-ncii-operational-policy.md) | **Parent framework** | [NCIIF](../01-frameworks/NCIIF.md) |
| **Additional anchors** | Cyber Security Act 2024; NACSA Code of Practice |

## 1. Purpose
Specify the NACSA notification requirements for GIBB as a designated NCII entity — what triggers notification, on what timeline, in what form, through what channel.

## 2. Scope
All notifications from GIBB to NACSA under the Cyber Security Act 2024 — incident notifications, periodic reports, directive acknowledgements, scope change notifications.

## 3. Requirements

### 3.1 Trigger types

| Trigger | NACSA notification basis |
|---|---|
| NCII-scope cyber incident (per NACSA Code definition) | Code of Practice incident reporting |
| Material change to NCII scope (system additions/removals, M&A) | Code of Practice scope-change notification |
| Annual / periodic compliance reporting | Per NACSA-specified cadence |
| NACSA directive issuance | Acknowledgement within NACSA-specified period |
| Audit finding requiring NACSA visibility | Per NACSA reporting expectations |

### 3.2 Notification timelines

| Notification class | Submission window |
|---|---|
| NCII-scope material cyber incident | Per current NACSA directives — ⚠ verify with current NACSA Code; embed in operational reference maintained by CCO |
| Scope change | Per NACSA Code (typically prior notification for major scope additions) |
| Periodic compliance reports | Per NACSA prescribed cadence (annual / semi-annual) |
| Directive acknowledgement | Within period specified in the directive |

> ⚠ Specific numeric timelines for NACSA NCII notifications are subject to NACSA Code of Practice as issued. CCO maintains the authoritative current timelines in an operational reference. This standard intentionally does not embed timelines that may change with NACSA directive updates.

### 3.3 Notification content (incident)

NCII incident notification shall include:

- Incident identifier (correlated with [REG-INC](../06-registers/REG-INC-incident-register.md))
- Detection date/time, declaration date/time
- Incident summary (sanitised for any inter-NCII sharing)
- Affected NCII assets / scope
- Initial severity assessment
- Detection mechanism
- Containment status at notification
- Indicators of Compromise (where shareable)
- GIBB contact point for follow-up

### 3.4 Channel and submission

| Ref | Requirement |
|---|---|
| 3.4.1 | NACSA-prescribed channels (current portal / secure email / secure messaging per Code). |
| 3.4.2 | Backup channel maintained for primary-channel outage. |
| 3.4.3 | Submission acknowledgement from NACSA shall be retained as evidence in [REG-NCN](../06-registers/REG-NCN-nacsa-notification-register.md). |

### 3.5 Coordination with BNM notification

| Ref | Requirement |
|---|---|
| 3.5.1 | NACSA notification is **in addition to** BNM notification under RMiT 11.18; CCO coordinates parallel submissions. |
| 3.5.2 | Submission to NACSA does not relieve obligation to submit to BNM and vice versa. |

### 3.6 Confidentiality of submissions

| Ref | Requirement |
|---|---|
| 3.6.1 | Notifications shall be classified Internal — restricted; access limited to CCO, CISO, designated NACSA liaison, and audit. |
| 3.6.2 | Notifications shall not contain personal data beyond what is necessary; minimisation per PDPA. |

### 3.7 Internal escalation prior to submission

| Ref | Requirement |
|---|---|
| 3.7.1 | NACSA notification approval by CCO (CCO delegate during off-hours) before submission. |
| 3.7.2 | CISO informed of every notification. |
| 3.7.3 | CEO informed for material NCII-scope incidents. |

## 4. Exceptions
NACSA Code of Practice notification obligations are **not** subject to exception within GIBB authority.

## 5. Related documents
[POL-23](../02-policies/POL-23-ncii-operational-policy.md); [POL-13](../02-policies/POL-13-incident-management-policy.md); [REG-NCN](../06-registers/REG-NCN-nacsa-notification-register.md); [SOP-NC-01 NACSA Incident Notification SOP](../04-procedures/SOP-NC-01-nacsa-incident-notification-sop.md); [NCIIF](../01-frameworks/NCIIF.md)

## 6. References
Cyber Security Act 2024 (Malaysia); NACSA Code of Practice (current edition); NACSA sector-lead directives for financial services NCII; BNM RMiT 28 Nov 2025 Section 11.4.

## 7. Document control
| Version | Date | Author | Approver | Change |
|---|---|---|---|---|
| 1.0 | [Effective] | CCO + CISO | CCO | Initial |
