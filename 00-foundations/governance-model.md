# Governance model — who owns, approves, and reviews

A document is only as good as the governance that produces and maintains it. This page sets out the operating model for the documentation suite: who owns what, who approves what, and how documents move through the lifecycle.

---

## Three-line governance model

General Bank operates a standard three-line model for information security and technology risk:

| Line | Function | Role in the documentation suite |
|---|---|---|
| **1st line — operations** | IT, Information Security, Business units | Authors procedures and standards; operates controls; produces evidence (registers). |
| **2nd line — risk & compliance** | Technology Risk, Compliance, Operational Risk | Reviews policies and standards for risk and regulatory alignment; challenges 1st line. |
| **3rd line — internal audit** | Internal Audit | Independently tests whether the documented controls are operating. Does not author documents. |

**Why this matters for documentation.** A document drafted, reviewed, and approved entirely within the 1st line carries no independent challenge. A document never seen by 3rd line carries no independent assurance. The governance flow below threads each document through both.

---

## Approval authority by document type

| Document type | Drafter | Reviewer (2nd line) | Approver | Cadence |
|---|---|---|---|---|
| **Master Information Security Policy** | CISO | Chief Risk Officer | **Board of Directors** | Annual |
| **Supporting policy** | CISO / function head | Chief Risk Officer | **Risk Management Committee** (delegated by Board) | Annual |
| **Standard** | CISO + relevant tech lead | Technology Risk | **CISO** | Annual or technology-driven |
| **Procedure / SOP** | Process owner | (peer review within function) | **Process owner** (e.g., Head of Identity) | As needed |
| **Plan** (IRP / BCP / DRP) | CISO / COO | Chief Risk Officer | **Risk Management Committee** | Annual + post-event |
| **Register** | Process owner | n/a (operational record) | Process owner | Continuous |

For Malaysian licensed banks, BNM RMiT §6.6 requires the **Board** to approve the Technology Risk Management Framework, and the **Board Risk Committee** to oversee technology risk on an ongoing basis. The master Information Security Policy in this repo is positioned as a board-approved document accordingly.

---

## RACI for the documentation suite as a whole

| Activity | Board | RMC | CRO | CISO | Function head | Process owner | Internal Audit |
|---|---|---|---|---|---|---|---|
| Approve master IS Policy | A | C | C | R | I | I | I |
| Approve supporting policies | I | A | C | R | C | I | I |
| Approve standards | I | I | C | A/R | C | I | I |
| Approve procedures | I | I | I | I | C | A/R | I |
| Approve plans (IR/BC/DR) | I | A | C | R (IR) / C (BC) | R (BC) | I | I |
| Maintain registers | I | I | I | I | A | R | I |
| Independent test of controls | I | I | I | C | C | C | A/R |
| Drive remediation of audit findings | I | I | A | R | R | R | C |

A = Accountable · R = Responsible · C = Consulted · I = Informed.
RMC = Risk Management Committee. CRO = Chief Risk Officer.

---

## Review cadence

| Trigger | Action |
|---|---|
| **Annual** | Every policy, standard, and plan reviewed for currency. Even if no change, an explicit "reviewed, no change" entry is recorded in the document control table. |
| **Material organisational change** (acquisition, divestment, restructure) | Re-review affected policies and standards within 60 days. |
| **Material technology change** (new core system, new cloud tenancy, new authentication platform) | Re-review affected standards and procedures within 30 days; baselines updated immediately. |
| **Regulatory change** (new or revised BNM circular, new ISO version) | Gap analysis within 30 days; documents updated within 90 days unless the change requires longer transition. |
| **Material incident** | Post-incident review identifies which documents (policy, standard, procedure, plan) contributed to or failed to prevent the incident. Updates within 60 days. |
| **Audit finding** | Document update timeline agreed with internal audit, typically within the audit response window (60–90 days). |

---

## Exception management

No policy or standard can anticipate every situation. A documented **exception** records a deliberate, time-bound deviation.

- Every exception is **logged in the Exception Register**.
- Every exception has an **approver** at or above the document's own approval authority (e.g., a policy exception requires RMC approval).
- Every exception is **time-bound** — typical maximum 12 months, renewable once with re-justification.
- Every exception has a **compensating control** — what reduces the residual risk during the exception period.

An organisation accumulating exceptions in the same area should treat that as a signal to revise the underlying policy or standard, not to keep renewing exceptions indefinitely.

---

## Document version control

- **Semantic versioning** in the document metadata: `MAJOR.MINOR` (e.g., 1.0, 1.1, 2.0). Major = reapproval required (substantive change). Minor = update without reapproval (clarification, editorial, link fix).
- **Document control table** at the bottom of every document records every version, change author, change summary, and approver.
- **One source of truth.** No document exists in more than one location. If a document is referenced from multiple places, the reference is a link, not a copy.
- **Supersession is explicit.** Every new version names the version it supersedes.
