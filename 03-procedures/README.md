# 03 — Procedures / SOPs (Tier 3)

The **operational** layer. Process-owner approved. Step-by-step, role-by-role, tool-by-tool. Changes as the toolchain changes.

← [Back to repo home](../README.md) · [Foundations](../00-foundations/) ↑ · [Standards](../02-standards/) ↑

---

## What procedures are for

A standard says *what specifically* is required (e.g., "identity disablement on termination shall complete within 2 hours of HR trigger; 30 minutes for high-risk leavers"). A procedure says *how the operator delivers that*: "When HR sets `status=Terminated` in Workday, the integration job fires within 15 minutes and (1) disables the AD account, (2) revokes Okta sessions, (3) removes the user from SaaS groups, (4) creates a ticket assigned to the Identity team to recover hardware."

Procedures change when tools change. Policies and standards stay stable.

---

## Procedures in this repo

Two SOPs fully drafted as worked examples — one per cascade. A real M3 SOC and IAM function would have ~20–40 SOPs each.

| ID | Document | Parent standard | Parent policy | Owner |
|---|---|---|---|---|
| **SOP-02-01** | [Joiner / Mover / Leaver SOP](joiner-mover-leaver-sop.md) | [STD-02-01 §3.5](../02-standards/password-and-authentication-standard.md) | [POL-02](../01-policies/02-access-control-policy.md) | Head of IAM |
| **SOP-08-01** | [Incident Triage SOP](incident-triage-sop.md) | [STD-08-01](../02-standards/incident-classification-and-severity-standard.md) | [POL-08](../01-policies/08-incident-management-policy.md) | Head of SOC |

---

## SOPs General Bank would add

(Not yet drafted — natural extensions.)

| SOP | Function | Why |
|---|---|---|
| Service Account Lifecycle SOP | IAM | Non-human identity management — distinct from human JML |
| Privileged Access Review SOP | IAM | The quarterly review that populates [REG-PAR](../05-registers/privileged-access-review-register.md) |
| Exception Approval SOP | ISMS Manager | The workflow behind every documented exception |
| Vulnerability Scan Operation SOP | Vulnerability Mgmt | Operational running of the scanning toolchain |
| Patch Deployment SOP | IT Ops | The change-management overlay for patching |
| Backup Operation SOP | IT Ops | Daily/weekly running and restorability testing |
| SOC Detection Tuning SOP | SOC | False-positive management, detection-engineering backlog |
| Cyber Drill Exercise SOP | SOC + CISO | The annual cyber drill required by RMiT §11.16 |
| Forensic Evidence Handling SOP | SOC | Chain-of-custody operations for incident evidence |

---

## Document anatomy

Every SOP in this folder follows the same nine-section structure:

1. **Purpose** — operational outcome
2. **Scope** — process, performers, systems
3. **Trigger** — exact event that starts the procedure
4. **Roles** — who does what
5. **Procedure** — step-by-step with actor / action / tool / output / SLA
6. **Exception handling** — what to do when the procedure cannot complete normally
7. **Evidence and records** — what gets logged, where, for how long
8. **Related documents** — parent standard, parent policy, related registers
9. **Document control**

See [`../_templates/procedure-template.md`](../_templates/procedure-template.md).

---

## Cross-links

- ↑ [Standards (Tier 2)](../02-standards/) — the quantified requirements SOPs implement
- ↑ [Policies (Tier 1)](../01-policies/) — the principles standards implement
- → [Registers](../05-registers/) — the evidence outputs SOPs produce
- → [Plans](../04-plans/) — for incident-driven SOPs, the IRP wraps the IR-related SOPs
- → [Document control](../06-document-control/)
