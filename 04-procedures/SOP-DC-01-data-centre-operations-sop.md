# SOP-DC-01 — Data Centre Operations SOP

| | |
|---|---|
| **Document ID** | SOP-DC-01 | **Version** | 1.0 |
| **Owner / Approver** | Head of Data Centre Operations / CIO |
| **Parent standard** | [STD-NW-01 Network Segmentation Standard](../03-standards/STD-NW-01-network-segmentation-standard.md); [STD-AM-01](../03-standards/STD-AM-01-it-asset-management-standard.md); [STD-BC-02 Backup and Restoration](../03-standards/STD-BC-02-backup-and-restoration-standard.md) | **Parent policy** | [POL-15 Physical and Environmental Security](../02-policies/POL-15-physical-and-environmental-security-policy.md); [POL-16 Operations Security](../02-policies/POL-16-operations-security-policy.md) |
| **Parent framework(s)** | [TRMF](../01-frameworks/TRMF.md); [BCMF](../01-frameworks/BCMF.md); [CRMF](../01-frameworks/CRMF.md) |

## 1. Purpose

To define the day-to-day operating procedures for GIBB's primary and DR on-premise data centres — physical access control, environmental monitoring, asset movement, change windows, maintenance, and incident response handoffs.

Closes the on-premise operations gap surfaced in the v2 multi-agent review.

## 2. Scope

GIBB primary data centre (head-office co-located or dedicated) and DR data centre (out-of-region per [BCMF](../01-frameworks/BCMF.md) Section 8). Out of scope: cloud-hosted environments (see [SOP-CL-01](SOP-CL-01-cloud-service-onboarding-sop.md), [SOP-CL-02](SOP-CL-02-cspm-operations-sop.md), [SOP-CL-03](SOP-CL-03-cloud-exit-validation-sop.md)).

## 3. Procedure — physical access management

| # | Actor | Action | Tool | Output | SLA |
|---|---|---|---|---|---|
| P1 | DC Access Coordinator | Receive access request via ticket (named individual + reason + duration + escort requirement) | Access mgmt system | Request logged | Same day |
| P2 | Approver (Head of DC Ops for routine; CISO for non-routine including vendor + after-hours) | Approve / reject; for vendor approve with mandatory escort | Access mgmt system | Decision logged | Within SLA per request type |
| P3 | DC Security | Verify identity on arrival (photo ID + biometric where in place); issue badge per approved scope | Access mgmt + badging | Access granted | Per arrival |
| P4 | DC Security | Escort if required; log entry, escort time, departure | Access mgmt | Movement log | Continuous |
| P5 | DC Access Coordinator | Weekly access log review for anomalies; quarterly access entitlement review for routine-access holders | Access mgmt | Review record | Weekly + Quarterly |

## 4. Procedure — environmental monitoring

| # | Actor | Action | Tool | Output | SLA |
|---|---|---|---|---|---|
| E1 | BMS (Building Management System) | Continuous monitoring of temperature, humidity, water leak, smoke, fire suppression, UPS state, generator state, power-feed health | BMS | Alarms | Continuous |
| E2 | DC Operations | Respond to environmental alarm per playbook; engage Facilities for HVAC / power / cooling; escalate to Head of DC Ops if response > 30 min | Alarm console | Incident log | Per alarm severity |
| E3 | DC Operations | Monthly preventive maintenance review with Facilities (UPS battery health, generator fuel + test, cooling efficiency, fire-suppression test) | Maintenance log | PM record | Monthly |
| E4 | Head of DC Ops | Quarterly environmental posture review; report to CIO | Dashboard | Quarterly report | Quarterly |

## 5. Procedure — asset movement (in / out)

| # | Actor | Action | Tool | Output | SLA |
|---|---|---|---|---|---|
| A1 | Requestor | Submit asset movement request — asset ID, owner, destination, reason, sanitisation requirement | Asset mgmt + ticket | Request logged | Per move |
| A2 | DC Access Coordinator + Asset Ops | Verify against [REG-DA](../06-registers/REG-DA-data-asset-register.md); confirm sanitisation per [SOP-DG-03](SOP-DG-03-data-destruction-sop.md) where data-bearing | Asset mgmt | Approval | Per request |
| A3 | DC Security | Verify physical asset against request at gate; escort to / from DC | Movement log | Movement record | Per movement |
| A4 | Asset Ops | Update [REG-DA](../06-registers/REG-DA-data-asset-register.md) and CMDB with new location / status | Asset mgmt | Records updated | Within 1 business day |

## 6. Procedure — change windows + maintenance

| # | Actor | Action | Tool | Output | SLA |
|---|---|---|---|---|---|
| C1 | Change Coordinator | Schedule physical / facilities work in approved change windows per [STD-CM-01](../03-standards/STD-CM-01-change-management-standard.md) | Change system | Schedule | Per window |
| C2 | DC Operations | Pre-change checklist (notifications sent, redundancy validated, rollback ready) | Checklist | Pre-change record | Before window |
| C3 | DC Operations + Facilities | Execute work; monitor systems throughout | Tooling | Execution log | During window |
| C4 | DC Operations | Post-change verification (systems healthy, no degraded state, rollback unwound) | Tooling | Post-change record | Within 1 hour of completion |

## 7. Procedure — incident handoff

| # | Actor | Action | Tool | Output |
|---|---|---|---|---|
| I1 | DC Operations | Detect or receive notification of incident affecting DC (environmental, physical, network, hardware) | Alarm console / SIEM | Initial detection |
| I2 | DC Operations | Triage; if SEV-3+ open per [SOP-IR-01](SOP-IR-01-incident-triage-sop.md) and notify SOC | Ticketing | Handoff ticket |
| I3 | SOC + DC Operations | Joint response per [PLN-01](../05-plans/PLN-01-incident-response-plan.md); for facilities-only events follow facilities playbook | Bridge | Response record |

## 8. Document control

| Version | Date | Author | Reviewer | Approver | Change summary |
|---|---|---|---|---|---|
| 1.0 | 2026-05-30 | Head of DC Ops | CIO + CISO | CIO | Initial version. Closes on-premise DC operations gap identified in v2 multi-agent review. |
