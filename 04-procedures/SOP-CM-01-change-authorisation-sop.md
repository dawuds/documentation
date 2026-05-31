# SOP-CM-01 — Change Authorisation SOP

| | |
|---|---|
| **Document ID** | SOP-CM-01 |
| **Layer** | Procedure (Tier 3) |
| **Version** | 1.0 |
| **Owner** | Head of IT Operations |
| **Approver** | Head of IT Operations |
| **Classification** | Internal |
| **Effective** | [Effective] |
| **Next review** | Annual or on toolchain change |
| **Parent standard** | [STD-CM-01](../03-standards/STD-CM-01-change-management-standard.md) |
| **Parent policy** | [POL-07](../02-policies/POL-07-change-management-policy.md) |

---

## 1. Purpose

To operationalise the change authorisation requirements in [STD-CM-01 Section 3.2](../03-standards/STD-CM-01-change-management-standard.md) — how a change moves from submission through CAB approval to ready-for-deployment.

## 2. Scope

All Normal and Major changes. Standard changes follow pre-authorised templates (no SOP needed). Emergency changes follow SOP-CM-02 (separate).

## 3. Trigger

Change ticket submission in the change management tool (e.g., ServiceNow Change module).

## 4. Roles

| Role | Responsibility |
|---|---|
| Change Initiator | Submit change with required fields |
| Change Coordinator | Review submission for completeness; triage to CAB or back to Initiator |
| CAB Chair (Head of IT Ops or delegate) | Convene CAB; record decisions |
| CAB members (CIO delegate, CISO delegate, Application Owners, Network, Operations, Security, Data, Shariah Compliance where relevant) | Review, challenge, approve / defer / reject |
| Independent Reviewer | Per RMiT 10.11 — competent person not involved in development |
| Business Sponsor (Major only) | Sign off business risk acceptance |

## 5. Procedure

### Step 1 — Submission

- **Actor:** Change Initiator
- **Action:** Complete change ticket with categorisation, risk assessment, test results, rollback plan, deployment plan, communication plan, dependencies
- **Tool:** Change management tool
- **Output:** Change ticket in `Submitted` status
- **SLA:** Per Initiator schedule

### Step 2 — Completeness triage

- **Actor:** Change Coordinator
- **Action:** Verify all mandatory fields per STD-CM-01 Section 3.2; categorisation appropriate; risk assessment material; test results adequate
- **Tool:** Change management tool
- **Output:** Ticket advanced to `Ready for CAB` or returned with comments
- **SLA:** 1 business day from Step 1

### Step 3 — Pre-CAB security review

- **Actor:** CISO delegate
- **Action:** For internet-facing or Confidential+ data changes, security review per STD-CM-01 Section 3.3.2
- **Tool:** Change management tool
- **Output:** Security sign-off recorded
- **SLA:** 2 business days

### Step 4 — Pre-CAB Shariah review (where applicable)

- **Actor:** Shariah Compliance
- **Action:** For changes affecting Islamic product systems' Shariah logic, Shariah Committee approval per STD-CM-01 Section 3.3.3
- **Tool:** Change management tool + Shariah Committee submission
- **Output:** Shariah approval recorded
- **SLA:** Per Shariah Committee cycle (typically monthly)

### Step 5 — Independent review (RMiT 10.11)

- **Actor:** Independent Reviewer (named, not involved in change development)
- **Action:** Review change design, risk assessment, test results; sign off or return
- **Tool:** Change management tool
- **Output:** Independent review sign-off
- **SLA:** 3 business days

### Step 6 — CAB review and decision

- **Actor:** CAB Chair + CAB members
- **Action:** Discuss; challenge; decide approve / defer / reject; record decision and conditions
- **Tool:** CAB meeting + change management tool
- **Output:** CAB decision; ticket advanced to `Approved` / `Deferred` / `Rejected`
- **SLA:** Within scheduled CAB cycle (weekly cadence for Normal; on-demand for Major within 10 business days)

### Step 7 — Business sponsor sign-off (Major only)

- **Actor:** Business Sponsor
- **Action:** Confirm business acceptance of residual risk; sign off
- **Tool:** Change management tool
- **Output:** Business sponsor sign-off
- **SLA:** 2 business days post-CAB

### Step 8 — Scheduling

- **Actor:** Change Coordinator
- **Action:** Schedule per Forward Schedule of Changes; communicate per STD-CM-01 Section 3.6
- **Tool:** Change management tool + FSC publication
- **Output:** Change scheduled; affected parties notified
- **SLA:** Per STD-CM-01 Section 3.6.1 notice requirements

### Step 9 — Deployment readiness

- **Actor:** Change Initiator
- **Action:** Confirm rollback plan validated; tested; deployment crew on standby
- **Tool:** Change management tool
- **Output:** Ticket in `Ready for Deployment`
- **SLA:** Per scheduled deployment

## 6. Exception handling

| Scenario | Path |
|---|---|
| CAB cannot reach quorum | Defer; CAB Chair authority to approve low-risk Normal changes solo with retrospective CAB notation |
| Independent Reviewer unavailable | Alternate Reviewer per CIO-maintained list |
| Shariah Committee timing incompatible with business need | Escalate to CRO + Shariah Committee Chair for expedited review |
| Disagreement within CAB | CAB Chair decides; documented dissent recorded |
| Rejected change re-submission | New change ticket required; reference prior; address rejection reasons explicitly |

## 7. Evidence and records

| Evidence | Where stored | Retention |
|---|---|---|
| Change ticket (complete lifecycle) | Change management tool | 7 years |
| CAB meeting minutes | Document repository | 7 years |
| Independent review sign-off | Change ticket attachment | 7 years |
| Shariah approval (where applicable) | Change ticket attachment + Shariah Committee record | Permanent |
| Business sponsor sign-off (Major) | Change ticket attachment | 7 years |
| Post-implementation review (Major) | Document repository | 7 years |

## 8. Related documents

- **Parent standard:** [STD-CM-01](../03-standards/STD-CM-01-change-management-standard.md)
- **Parent policy:** [POL-07](../02-policies/POL-07-change-management-policy.md)
- **Related SOPs:** SOP-CM-02 Emergency Change SOP; SOP-CM-03 Post-Implementation Review SOP (future)

## 9. Document control

| Version | Date | Author | Reviewer | Approver | Change summary |
|---|---|---|---|---|---|
| 1.0 | [Effective] | Head of IT Operations | CAB members | Head of IT Operations | Initial Effective |
