# REG-NCN — NACSA Notification Register

| | |
|---|---|
| **Document ID** | REG-NCN |
| **Layer** | Register (Layer 6) |
| **Owner** | Chief Compliance Officer (CISO operates in coordination) |
| **Classification** | Internal — restricted |
| **Cadence** | Per event |
| **Parent framework(s)** | [NCIIF](../01-frameworks/NCIIF.md) |
| **Parent policy** | [POL-23](../02-policies/POL-23-ncii-operational-policy.md) |
| **Source procedure** | SOP-NC-01 NACSA Incident Notification SOP (future) |

---

## Purpose

The authoritative record of every NACSA notification made by GIBB — incidents, scope changes, periodic reports, directive acknowledgements. The audit-grade evidence of GIBB's compliance with NACSA notification obligations under the Cyber Security Act 2024.

## Schema

| Field | Type | Description |
|---|---|---|
| `ncn_id` | string | `NCN-YYYY-NNN` |
| `notification_type` | enum | Incident / Scope change / Periodic report / Directive acknowledgement / Audit response / Other |
| `subject` | string | Short subject line |
| `originating_incident_id` | reference | If notification relates to an incident, link to REG-INC entry |
| `trigger_date` | datetime | When the event triggering notification occurred |
| `notification_due_date` | datetime | Per NACSA-specified timeline |
| `notification_submitted_date` | datetime | When notification submitted to NACSA |
| `sla_met` | bool | Submitted within NACSA-specified window |
| `nacsa_acknowledgement_received` | bool | NACSA receipt confirmation |
| `nacsa_response_date` | date | NACSA response (if any) |
| `follow_up_actions` | text | Actions NACSA required of GIBB |
| `follow_up_status` | enum | Open / In progress / Closed |
| `internal_owner` | role | CCO / CISO / other |
| `evidence_link` | reference | Submitted notification document; NACSA acknowledgement |
| `notes` | text | |

## Worked example — first entries (illustrative)

| ncn_id | type | subject | trigger | submitted | sla_met | ack | follow_up | status |
|---|---|---|---|---|---|---|---|---|
| NCN-2026-001 | Directive acknowledgement | NACSA Code of Practice v2.1 issuance | 2026-02-15 | 2026-02-22 | Yes | Yes | Implementation gap analysis due 2026-04-30 | Closed |
| NCN-2026-002 | Periodic report | Q1 2026 NCII posture report | 2026-04-15 | 2026-04-10 | Yes | Yes | No | Closed |
| NCN-2026-003 | Incident | Phishing campaign targeting bank staff (linked INC-2026-014; sub-threshold for BNM material but reportable as NCII pattern) | 2026-03-04 | 2026-03-04 | Yes | Yes | NACSA requested IOC sharing — completed | Closed |
| NCN-2026-004 | Periodic report | Q2 2026 NCII posture report | 2026-07-15 | (pending) | — | — | — | Open (due) |

> Real entries carry full submitted-notification text, NACSA-specified timeline citation, acknowledgement evidence.

## Maintenance

- Every NACSA notification creates an entry; entry created at the same time as the notification is submitted (or earlier if pre-staged).
- CCO reviews monthly for overdue entries.
- NACSA-imposed remediation actions tracked through follow-up status field; closed only when NACSA confirms or GIBB confirms remediation per directive.
- Quarterly summary to RMC.

## Related documents

- **Parent framework:** [NCIIF](../01-frameworks/NCIIF.md)
- **Parent policy:** [POL-23](../02-policies/POL-23-ncii-operational-policy.md)
- **Related registers:** REG-NC NACSA Directive Tracker (future); REG-NCA NCII Audit Findings Register (future); [REG-INC Incident Register](REG-INC-incident-register.md) (cross-reference for incident-triggered notifications)
