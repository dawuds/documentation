# Joiner / Mover / Leaver SOP

| | |
|---|---|
| **Document ID** | SOP-AC-01 |
| **Layer** | Procedure (Tier 3) |
| **Owner** | Head of Identity & Access Management |
| **Approver** | Head of Identity & Access Management |
| **Classification** | Internal |
| **Version** | 1.1 |
| **Effective date** | 2026-02-01 |
| **Next review** | 2027-02-01 (annual; immediate on toolchain change) |
| **Implements standard** | [STD-AC-01 Password & Authentication Standard](../03-standards/STD-AC-01-password-and-authentication-standard.md) Section 3.5 |
| **Implements policy** | [POL-06 Access Control Policy](../02-policies/POL-06-access-control-policy.md) Section 4.1, Section 4.4 |

---

## 1. Purpose

To operationalise identity creation, modification, and revocation across the lifecycle of every workforce member (employee, contractor, secondee, third party). This SOP is the **operational delivery** of the Joiner/Mover/Leaver requirements in [POL-06 Section 4.1](../02-policies/POL-06-access-control-policy.md) and the **timing thresholds** in [STD-AC-01 Section 3.5](../03-standards/STD-AC-01-password-and-authentication-standard.md).

## 2. Scope

All workforce identities (human) provisioned, modified, or de-provisioned within GIBB. Non-human / service / machine identities follow a separate SOP (SOP-02-02 Service Account Lifecycle, not included in this repo).

## 3. Trigger

| Trigger | Authoritative source | Event type |
|---|---|---|
| New hire signed contract → start date set | Workday (HR system) | **Joiner** |
| Internal role change confirmed → effective date set | Workday | **Mover** |
| Resignation accepted / termination confirmed → end date set | Workday | **Leaver — standard** |
| Immediate dismissal / for-cause termination | Workday flag `urgent-leaver=true` | **Leaver — urgent** |
| Contractor / third-party engagement start | Supplier Portal | **Joiner — non-employee** |
| Contractor / third-party engagement end | Supplier Portal | **Leaver — non-employee** |

The Workday and Supplier Portal events are the **only** authoritative triggers. Out-of-band requests (email, ticket, verbal) are rejected — the request must be entered into the authoritative source.

## 4. Roles

| Role | Responsibility |
|---|---|
| **HR Business Partner** | Owns the authoritative trigger in Workday; provides accuracy of start date, role, manager, location. |
| **Hiring manager / line manager** | Initiates the role assignment in the workflow; confirms required entitlements; recertifies access. |
| **IAM Service Desk (Tier 1)** | Monitors workflow queue; resolves provisioning exceptions; escalates to Tier 2. |
| **IAM Engineering (Tier 2)** | Maintains IDP, PAM, and JML automation; investigates failures. |
| **Asset Operations** | Provisions and recovers hardware. |
| **Information Security (oversight)** | Monitors compliance metrics; conducts quarterly access reviews. |

## 5. Procedure

### 5.1 Joiner — workforce

| # | Actor | Action | Tool | Output | SLA |
|---|---|---|---|---|---|
| J1 | HR Business Partner | Confirms candidate signed contract; creates `Person` record in Workday with start date, role, manager, location, business unit. | Workday | `personId` issued; integration fires nightly. | Same day as contract signature. |
| J2 | IDP (automation) | Workday `Person` event triggers identity creation in the IDP. Standard role bundle assigned based on `position` mapping. Account in `pre-hire` state until start date. | IDP / IGA | Identity created; SSO entitlements pending. | Within 4 hours of Workday event. |
| J3 | Hiring manager | Receives "approve role mapping" workflow item if `position` has multiple role-bundle candidates. Approves or selects. | IGA workflow | Role bundle assigned. | Within 2 business days. |
| J4 | IDP (automation) | On start date `00:01`, identity transitions from `pre-hire` to `active`. SSO entitlements provisioned. | IDP / IGA | Identity active; user can authenticate. | Automated. |
| J5 | Asset Operations | Hardware (laptop, smart card / FIDO2 key) prepared per role; awaiting first-day handover. | Asset Mgmt | Hardware staged. | By start date. |
| J6 | New joiner | First-day onboarding session: receives hardware, registers FIDO2 / smart card, sets initial password, completes mandatory security awareness module. | Onboarding workflow | First successful authentication; training completion recorded. | Day 1. |
| J7 | New joiner | Completes mandatory security awareness training. | LMS | Training completion. | Within 30 days. |

**SLA target end-to-end (J1 to J4):** identity active on start date with **100%** compliance.

### 5.2 Mover — role change

| # | Actor | Action | Tool | Output | SLA |
|---|---|---|---|---|---|
| M1 | HR Business Partner | Updates `Person` record in Workday with new role, new manager, effective date. | Workday | Event fires to IGA. | Same day as decision. |
| M2 | IGA (automation) | On effective date, **removes** prior role bundle entitlements and **adds** new role bundle entitlements. Entitlements not in either role bundle are flagged for review (potential orphan). | IGA | New entitlements active; orphan-entitlement review list generated. | Within 2 business days of effective date. |
| M3 | New manager | Receives "confirm role and entitlements" workflow item. Confirms or escalates. | IGA workflow | Confirmation recorded. | Within 5 business days. |
| M4 | Old manager | Receives "confirm prior entitlements removed" workflow item. Confirms or flags retained access required during handover (with end date). | IGA workflow | Retained-access exceptions logged. | Within 5 business days. |
| M5 | IAM Service Desk | Reviews orphan entitlements from M2. Removes unless a valid business case is documented. | IGA | Orphan entitlements cleared or exception logged. | Within 10 business days. |

**Anti-pattern explicitly prevented:** the Mover process **removes** prior entitlements rather than only adding new ones. The most common access-creep mode in banks is unintentional accumulation of entitlements across role changes; this SOP makes removal the default and retention the documented exception.

### 5.3 Leaver — standard

| # | Actor | Action | Tool | Output | SLA |
|---|---|---|---|---|---|
| L1 | HR Business Partner | Records termination in Workday with end date. | Workday | Event fires to IGA. | Same day as confirmation. |
| L2 | Line manager | Recovers business-critical knowledge (handover); arranges hardware return. | n/a | Handover completed. | Before end date. |
| L3 | IGA (automation) | On end date at `17:01` (or as set per local cutover time), **disables** all identity accounts (IDP, AD, federated apps where supported); revokes all active sessions. | IGA / IDP | Identity disabled; all sessions revoked. | Within **2 hours** of HR-triggered end-of-day (per STD-AC-01 Section 3.5.3). |
| L4 | Asset Operations | Recovers hardware; sanitises and re-provisions or disposes per [POL-15 Section 3.7](../02-policies/POL-15-physical-and-environmental-security-policy.md). | Asset Mgmt | Hardware recovered or written off. | Within 5 business days. |
| L5 | IGA | After 30 days, **deletes** identity from active directories; retains audit record per records retention. | IGA | Identity removed from active stores. | 30 days from disablement. |

### 5.4 Leaver — urgent (immediate dismissal / for-cause / regulatory)

| # | Actor | Action | Tool | Output | SLA |
|---|---|---|---|---|---|
| U1 | HR Business Partner (or designated authority) | Sets `urgent-leaver=true` flag in Workday. Notifies CISO of urgent leaver event. | Workday + secure channel | Event fires with urgent flag. | Immediate. |
| U2 | IGA (automation) | On `urgent-leaver=true` event, **immediately** disables identity, revokes sessions, and notifies SOC. | IGA / IDP / SIEM | Identity disabled; SOC alerted. | Within **30 minutes** of trigger (per STD-AC-01 Section 3.5.3). |
| U3 | SOC | Reviews recent activity of the disabled identity for indicators of malicious action; opens SEV-3 ticket pending findings (escalates to SEV-2 if anomalies found). | SIEM / SOAR | Triage record. | Within 4 hours. |
| U4 | Asset Operations | Recovers hardware on site or arranges immediate remote recovery. | Asset Mgmt | Hardware recovered or logged as outstanding. | Within 24 hours. |
| U5 | CISO | Reviews case; determines whether further investigation (forensic, fraud, law-enforcement liaison) is required. | n/a | Case decision logged. | Within 24 hours. |

### 5.5 Privileged access provisioning (overlay to 5.1, 5.2)

Where a joiner or mover requires privileged access:

| # | Actor | Action | Tool | Output | SLA |
|---|---|---|---|---|---|
| P1 | Hiring manager / asset owner | Submits privileged access request, citing business justification and the specific role bundle. | IGA + PAM | Request raised. | Per business need. |
| P2 | Asset owner | Approves request. | IGA workflow | Approval recorded. | Within 2 business days. |
| P3 | IAM Service Desk | Provisions privileged account in PAM; assigns dedicated admin workstation (PAW) for Tier-0 access; enrolls phishing-resistant MFA. | PAM | Privileged account active. | Within 2 business days of P2. |
| P4 | New user | First-time check-out: completes privileged access training acknowledgement. | LMS + PAM | Training completion. | Before first use. |

## 6. Exception handling

| Scenario | Path |
|---|---|
| HR trigger not received within expected window | IAM Service Desk creates ticket against HR; escalates to HR lead at 24 hours. |
| Automation failure (IGA → IDP integration down) | IAM Engineering invokes manual provisioning per backup procedure; SLA tracked separately; root cause logged for PIR if recurring. |
| Hardware not recovered within SLA | Escalated to line manager and CISO at 7 days; recorded as outstanding asset until recovered or written off. |
| Identity disablement misses SLA | Logged as control deficiency in the quarterly access review report; root cause analysed; remediation tracked. |

## 7. Evidence and records

| Evidence | Where stored | Retention |
|---|---|---|
| Workday trigger event | Workday audit log | Per HR record retention schedule |
| IGA workflow record (approvals, role assignments) | IGA platform | 7 years minimum |
| Identity disablement log | IDP audit log | 7 years minimum |
| PAM activity (privileged account creation, MFA enrolment) | PAM audit log | 7 years minimum |
| Training completion | LMS | Per HR record retention schedule |
| Hardware recovery | Asset Management system | 5 years minimum |
| Quarterly recertification outputs (consumed by REG-PAR for privileged) | IGA + REG-PAR | 5 years minimum |

## 8. Related documents

- **Parent standard:** [STD-AC-01 Password & Authentication Standard](../03-standards/STD-AC-01-password-and-authentication-standard.md)
- **Parent policy:** [POL-06 Access Control Policy](../02-policies/POL-06-access-control-policy.md)
- **Related registers:** [REG-PAR Privileged Access Review Register](../06-registers/REG-PAR-privileged-access-review-register.md)
- **Related SOPs:** SOP-02-02 Service Account Lifecycle (not included in this repo).

## 9. Document control

| Version | Date | Author | Reviewer | Approver | Change summary |
|---|---|---|---|---|---|
| 1.0 | 2026-01-25 | Head of IAM | IAM team, CISO | Head of IAM | Initial Effective version. |
| 1.1 | 2026-04-10 | Head of IAM | IAM team | Head of IAM | Minor — updated tool reference following IDP migration. Steps unchanged. |

---

## v2 re-anchoring (2026-05-28)

This document was re-anchored as part of the v2 build (Session 5) per [DEC-001](../_context/decisions.md). Substantive content preserved from the v1 snapshot at [`../v1/`](../v1/). Changes applied:

- Document ID updated to v2 numbering convention
- **Parent framework(s)** and **COBIT objective(s)** added to metadata block
- Bank name normalised from "General Bank" to **GIBB** (General Islamic Bank Berhad)
- Internal cross-references migrated from v1 paths to v2 paths
- v1 sister-document references updated to v2 document IDs

Pending formal GIBB approval under v2. The Effective and Next review dates above are inherited from the v1 1.x lifecycle and will be updated when this document is approved under v2 governance.
