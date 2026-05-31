# SOP-CM-02 — Emergency Change SOP

| | |
|---|---|
| **Document ID** | SOP-CM-02 | **Version** | 1.0 |
| **Owner / Approver** | Head of IT Operations |
| **Parent standard** | [STD-CM-01 Section 3.9](../03-standards/STD-CM-01-change-management-standard.md) | **Parent policy** | [POL-07](../02-policies/POL-07-change-management-policy.md) |

## 1. Purpose
Operationalise emergency change authorisation for genuine emergencies — incident remediation, critical vulnerability response, regulatory directive with insufficient lead time.

## 2. Trigger
Active SEV-1 or SEV-2 incident requiring change; CISA KEV vulnerability on internet-facing system; regulatory directive with < 5 business days lead time.

## 3. Procedure

| # | Actor | Action | Tool | Output | SLA |
|---|---|---|---|---|---|
| 1 | Change Initiator | Submit emergency change with justification, change content, rollback, blast radius assessment | Change tool | Emergency change ticket | Immediate |
| 2 | On-call Authority (Head of IT Ops / CISO / CIO delegate) | Review; approve / deny with comment | Change tool | Approval recorded | ≤ 1 hour |
| 3 | Change Initiator | Deploy with deployment crew on standby | Change tool + deployment tooling | Deployment log entry | Per approved window |
| 4 | Change Initiator | Validate deployment outcome | Per service | Post-deploy validation | Within 1 hour of deploy |
| 5 | Change Coordinator | Schedule retrospective CAB within 5 business days | CAB calendar | Retro CAB item | Within 5 business days |
| 6 | CAB | Review retrospectively; document lessons; backfill to change process if needed | CAB minute | Retrospective record | At CAB meeting |

## 4. Exception handling
On-call authority unavailable: escalate to CIO or CISO (cross-coverage). Rollback failure: invoke [PLN-01 IRP](../05-plans/PLN-01-incident-response-plan.md) if service impacted.

## 5. Evidence
Change ticket; deployment log; post-deploy validation; retro CAB minute. Retained 7 years per [STD-CR-02 Section 3.6](../03-standards/STD-CR-02-logging-standard.md).

## 6. Document control
| Version | Date | Author | Approver | Change |
|---|---|---|---|---|
| 1.0 | [Effective] | Head of IT Ops | Head of IT Ops | Initial |
