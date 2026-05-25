# Incident Triage SOP

| | |
|---|---|
| **Document ID** | SOP-08-01 |
| **Layer** | Procedure (Tier 3) |
| **Owner** | Head of SOC |
| **Approver** | Head of SOC |
| **Classification** | Internal — restricted |
| **Version** | 1.0 |
| **Effective date** | 2026-02-01 |
| **Next review** | 2027-02-01 (annual; immediate on toolchain change or post-SEV-1 incident) |
| **Implements standard** | [STD-08-01 Incident Classification & Severity Standard](../02-standards/incident-classification-and-severity-standard.md) |
| **Implements policy** | [POL-08 Incident Management Policy](../01-policies/08-incident-management-policy.md) |

---

## 1. Purpose

To define the operational steps the Security Operations Centre takes from the moment a security event is detected or reported through to: (a) classification per [STD-08-01](../02-standards/incident-classification-and-severity-standard.md), (b) initial containment decision, (c) handover to incident response if severity warrants, or (d) closure if benign.

This SOP is the **first 60 minutes** of incident response. The [Incident Response Plan](../04-plans/incident-response-plan.md) covers what happens after triage handoff.

## 2. Scope

All security events received by the SOC, from all detection sources:

- SIEM alerts
- EDR alerts
- DLP alerts
- Email security alerts
- Network detection alerts
- Threat-intelligence-driven hunting findings
- User reports (via published phishing-report button, IT Service Desk, or direct contact)
- External notifications (regulator, threat-sharing community, researcher, vendor advisory)
- Cloud security posture management alerts

## 3. Trigger

Any security event arriving in the SOC queue or by exception channel.

## 4. Roles

| Role | Responsibility in triage |
|---|---|
| **SOC Tier 1 Analyst** | Initial triage of all queued events; closure of SEV-4 within own authority; escalation of suspected SEV-3+ to Tier 2. |
| **SOC Tier 2 Analyst** | In-depth analysis of SEV-3 and complex SEV-4; classification proposal for SEV-2+. |
| **SOC Shift Lead** | Severity confirmation for SEV-3 and SEV-2 (proposed); decision to engage Incident Commander; channel-up for SEV-1. |
| **Head of SOC / on-call** | SEV-2 IC by default; SEV-1 IC handover to CISO. |
| **CISO / on-call** | SEV-1 IC; SEV-2 IC where reputational/regulatory exposure warrants. |
| **IT Service Desk** | First point of receipt for user-reported events outside SOC channels; forwards to SOC queue. |

## 5. Procedure

### 5.1 Receipt and initial logging (within 5 min)

| # | Actor | Action | Tool | Output | SLA |
|---|---|---|---|---|---|
| T1 | SOC Tier 1 | Acknowledge event in SOAR queue; assign to self. | SOAR | Event marked `IN-PROGRESS`; assignee set. | Within 5 min of arrival in queue (within 15 min for off-hours queue depth). |
| T2 | SOC Tier 1 | Capture initial facts: source of detection, affected asset (IP/hostname/user), timestamp, raw alert content. | SOAR + SIEM | Initial facts logged. | Same step. |

### 5.2 Initial classification (within 15 min)

| # | Actor | Action | Tool | Output | SLA |
|---|---|---|---|---|---|
| T3 | SOC Tier 1 | Apply the **decision tree** below to propose an initial severity. | SOAR (decision-tree macro) | Proposed severity (SEV-1, SEV-2, SEV-3, or SEV-4). | Within 15 min of T1. |
| T4 | SOC Tier 1 | If proposed severity is SEV-3 or higher, immediately notify SOC Shift Lead via SOC channel and escalate the SOAR ticket. | SOC channel + SOAR | Shift Lead engaged. | Same step. |

**Decision tree — propose initial severity:**

```
Is the affected asset Tier 0 (domain admin, PAM,
core banking admin, payment system admin)?
  ├─ YES → propose SEV-1; engage CISO on-call.
  └─ NO ↓

Is there confirmed indicator of compromise on a
production system (malicious file executed,
unauthorised lateral movement, data exfiltration
artefact)?
  ├─ YES → propose SEV-2; engage Head of SOC on-call.
  └─ NO ↓

Does the event affect a customer-facing critical
service (internet banking, mobile banking, payment
processing) AND show active operational impact?
  ├─ YES → propose SEV-2; engage Head of SOC on-call.
  └─ NO ↓

Is there an active human adversary signal
(targeted phishing reaching multiple users,
hands-on-keyboard activity, credential abuse
in progress)?
  ├─ YES → propose SEV-2 or SEV-3 (Tier 2 to
  │        determine); engage Shift Lead.
  └─ NO ↓

Is the event a localised security event with
no confirmed compromise of Confidential+ data?
  ├─ YES → propose SEV-3; SOC continues triage.
  └─ NO ↓

Is the event a routine SOC-handleable event
(generic phishing blocked, EDR-contained
malware, policy violation requiring user
follow-up)?
  ├─ YES → propose SEV-4; SOC closes after handling.
  └─ NO → propose SEV-3 by default; Shift Lead reviews.
```

### 5.3 Triage analysis (within MTTA per severity)

| # | Actor | Action | Tool | Output | SLA |
|---|---|---|---|---|---|
| T5 | SOC analyst (per assignment) | Pivot from initial event: query SIEM/EDR/network for related activity, affected user(s) recent activity, lateral movement indicators, persistence indicators, data movement indicators. | SIEM, EDR, network detection, DNS, proxy, DLP, threat intel | Triage narrative; updated severity if facts change. | Per MTTA target in STD-08-01 §3.3. |
| T6 | SOC analyst | Determine whether containment action is needed in the triage window (e.g., disable user account, isolate endpoint, block IoC at perimeter). | SOAR + EDR + IDP + firewall | Containment actions taken; logged. | As warranted; do **not** delay containment for documentation. |

### 5.4 Containment decision in triage

**Pre-authorised containment actions** (SOC may execute without further approval — log immediately):

| Action | Conditions |
|---|---|
| Isolate single endpoint via EDR | Confirmed IoC on endpoint |
| Disable single user account | Confirmed credential compromise; align with [POL-02 §4.8](../01-policies/02-access-control-policy.md) |
| Block single IoC (file hash, IP, domain) at perimeter | Confirmed malicious IoC |
| Quarantine single email at gateway | Confirmed phishing |

**Containment requiring Incident Commander or higher approval** (do not execute in triage):

| Action | Required approver |
|---|---|
| Isolate multiple endpoints (>10) | Incident Commander |
| Disable multiple user accounts (>5) | Incident Commander |
| Block large IP / domain range | Incident Commander |
| Take down customer-facing service | CEO or designated delegate (defined in IRP) |
| Disable cross-network segment | Incident Commander + Head of IT Ops |

### 5.5 Escalation and handover

| # | Actor | Action | Tool | Output | SLA |
|---|---|---|---|---|---|
| T7 | SOC Shift Lead | Confirm or revise severity. If SEV-3 — SOC continues to handle. If SEV-2 — engage Head of SOC as Incident Commander. If SEV-1 — engage CISO on-call as Incident Commander and follow IRP activation. | SOC channel + SOAR + bridge | IC assigned; IRP activated for SEV-1/SEV-2. | Per MTTA target. |
| T8 | SOC Shift Lead (or IC, once assigned) | Create entry in [Incident Register](../05-registers/incident-register.md) with assigned `INC-YYYY-NNN` identifier. | Incident Register | Incident recorded. | Within 30 min of severity confirmation. |
| T9 | IC | For SEV-1 and SEV-2, convene response team per IRP; declare incident bridge open. | IRP | Bridge open; team engaged. | Per IRP timings. |

### 5.6 SEV-4 closure (within SOC authority)

| # | Actor | Action | Tool | Output | SLA |
|---|---|---|---|---|---|
| C1 | SOC Tier 1/2 | Complete remediation per standard handling (block IoCs, follow up with affected user, etc.). | SOAR | Actions completed. | Per SOC standard handling. |
| C2 | SOC Tier 1/2 | Close SOAR ticket with closure category from STD-08-01 §3.6, brief narrative, and lessons-learned tag if applicable. | SOAR | Ticket closed. | Same step. |
| C3 | SOC Shift Lead | Sample-review closed SEV-4 tickets (target 10% per shift) for classification accuracy. | SOAR | Sample review note. | Per shift. |

### 5.7 SEV-3 closure (within SOC authority unless materiality criteria met)

| # | Actor | Action | Tool | Output | SLA |
|---|---|---|---|---|---|
| C4 | SOC Tier 2 (designated IC for SEV-3) | Confirm containment, recovery, root cause; assess against materiality criteria (STD-08-01 §3.2); if material, escalate to SEV-2 retrospectively and notify CISO. | SOAR + Incident Register | Closure narrative; materiality assessment. | Per MTTC target. |
| C5 | SOC Shift Lead | Approve closure; ensure Incident Register entry complete; flag for Q-PIR sample if pattern noted. | Incident Register | Approved closure. | Same shift. |

## 6. Exception handling

| Scenario | Path |
|---|---|
| SIEM / SOAR outage during triage | Manual triage process — SOC voice bridge open; manual log book; classify and act per memory; backfill SOAR on recovery. |
| User report cannot be validated (no evidence in tooling) | Treat as SEV-4 user report; capture for trend analysis; respond to reporter regardless. |
| Conflicting severity opinions within SOC | Shift Lead decides; CISO is final arbiter; document the disagreement in the ticket for post-incident learning. |
| Detected event matches a known false-positive pattern | Close as SEV-4 false positive; **do not silently suppress** — capture for detection-tuning backlog. |

## 7. Evidence and records

| Evidence | Where stored | Retention |
|---|---|---|
| SOAR ticket (full history) | SOAR | 7 years |
| SIEM raw events and queries | SIEM | Per logging retention standard |
| Containment actions (EDR isolation, account disablement, firewall blocks) | EDR / IDP / firewall logs | 7 years |
| Incident Register entry | [REG-INC](../05-registers/incident-register.md) | Permanent (lifetime of bank) |
| Bridge recording (for SEV-1/SEV-2 once IRP activated) | Conferencing platform | 7 years |

## 8. Related documents

- **Parent standard:** [STD-08-01 Incident Classification & Severity Standard](../02-standards/incident-classification-and-severity-standard.md)
- **Parent policy:** [POL-08 Incident Management Policy](../01-policies/08-incident-management-policy.md)
- **Plan:** [PLN-08-01 Incident Response Plan](../04-plans/incident-response-plan.md)
- **Related registers:** [REG-INC Incident Register](../05-registers/incident-register.md)

## 9. Document control

| Version | Date | Author | Reviewer | Approver | Change summary |
|---|---|---|---|---|---|
| 1.0 | 2026-01-25 | Head of SOC | SOC team, CISO | Head of SOC | Initial Effective version. |
