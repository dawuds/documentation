# Document lifecycle — draft to retirement

Every document in the suite moves through a defined lifecycle. The lifecycle exists to ensure that (a) the right people see the document before it goes live, (b) the document remains current after it goes live, and (c) when the document is retired, the retirement itself is recorded.

---

## States

| State | Meaning | Visible to | Authority to advance |
|---|---|---|---|
| **Draft** | Document is being written. Not yet authoritative. | Author + drafting team | Author |
| **In Review** | Sent to 2nd line and stakeholders for comment. | Author + reviewers | Author (after comments addressed) |
| **Pending Approval** | Review complete. Awaiting formal approval. | Author + approver | Approver |
| **Approved** | Approved, not yet live. (Useful for staged rollouts.) | Whole organisation (read-only) | Author / publisher |
| **Effective** | Live and authoritative. | Whole organisation | — |
| **Under Revision** | A material update is being prepared while the current version remains Effective. | Author + reviewers | Author |
| **Superseded** | Replaced by a later version. Retained for audit history. | Auditors | — |
| **Retired** | No longer applicable. Retained for audit history. | Auditors | Approver |

---

## State transitions

```
[Draft] ──> [In Review] ──> [Pending Approval] ──> [Approved] ──> [Effective]
                                                                      │
                                                                      ├──> [Under Revision] ──> [In Review] ──> ...
                                                                      │
                                                                      ├──> [Superseded]   (replaced by new version)
                                                                      │
                                                                      └──> [Retired]      (no longer applicable)
```

Every transition is recorded in the document control table at the bottom of the document.

---

## Drafting

| Step | Owner | Output |
|---|---|---|
| Identify need (gap, audit finding, new regulation, technology change) | CISO / function head | Drafting request |
| Identify the layer (policy / standard / procedure / plan / register) | Drafter | Template selection |
| Identify the ISO 27002:2022 controls and BNM RMiT sections implemented | Drafter | Reference list in document |
| Identify the parent document (which policy this standard implements, which standard this procedure implements) | Drafter | "Related documents" section |
| First draft using the relevant template | Drafter | Draft document |

If the document does not clearly trace to a parent and a control, stop and reconsider whether the document should exist.

---

## Review

| Reviewer | What they check |
|---|---|
| **2nd line — Technology Risk** | Risk and regulatory alignment; consistency with risk appetite; cross-document consistency. |
| **2nd line — Compliance** | Alignment with BNM RMiT and other binding regulation; alignment with internal compliance obligations. |
| **Internal Audit** | (Informed, not approver) — confirms the document is testable; flags audit-readiness gaps. |
| **Affected function leads** | Operational feasibility; alignment with current processes and toolchain. |
| **Legal** | (Where applicable) — for documents touching contractual or statutory obligations. |

Review is **time-boxed**. A typical SLA: 10 working days for comment. Silence after the deadline is treated as no objection (with the deadline recorded), but a sign-off in the document control table is always preferable.

---

## Approval

- Approval is **explicit and recorded** — a verbal "looks fine" is not approval. The approver's role is recorded in the document control table along with the date.
- For board- or committee-approved documents, the approval is recorded in the meeting minutes, and the document control table cites the meeting reference.
- For standards (CISO-approved) and procedures (process owner-approved), an email or workflow approval is sufficient, retained as evidence.

---

## Publishing

- Approved documents are published to a **single source-of-truth location** (in this repo, the relevant folder).
- Every document has a stable URL/path. Links from other documents and from operational systems must point to this stable location.
- Older versions are retained in version history but are clearly marked as superseded.

---

## Maintenance

Every document carries a **next-review date** in its metadata. The owner is responsible for:

- Conducting the review by the due date.
- Recording the outcome — even "reviewed, no change" is an outcome.
- Triggering an update cycle if the review identifies material change.

A document past its review date is treated as a control deficiency. The Exception Register is *not* the mechanism for documents that have aged out — the mechanism is review.

---

## Retirement

A document is retired when:

- It has been **superseded** by a replacement (the replacement names what it supersedes).
- The underlying activity has **ceased** (e.g., a procedure for a decommissioned system).
- A **scope change** has placed the activity out of the ISMS scope.

Retirement requires the same approval authority as the original document. Retired documents are retained for at least the period required by the records retention schedule (BNM RMiT and Malaysian record-keeping requirements at minimum), tagged as Retired, and removed from active navigation.

---

## Where the lifecycle is recorded

The lifecycle is operationalised in [`06-document-control/`](../06-document-control/):

- [`master-document-register.md`](../06-document-control/master-document-register.md) — current state of every document.
- [`change-log.md`](../06-document-control/change-log.md) — chronological log of every state transition.
- [`approval-register.md`](../06-document-control/approval-register.md) — every approval event with the authority that approved it.
- [`archive/`](../06-document-control/archive/) — superseded and retired documents retained for audit and forensic reference.

Every document also carries its own document control table at the foot of the document. Those are the *records of control*; the registers in `06-document-control/` are the *cross-document register of control*. Both are required — neither alone is sufficient.

## Why this matters

A documentation suite without lifecycle discipline becomes a graveyard of stale documents within 18 months. Auditors find policies referencing decommissioned systems, procedures referencing tools no longer in use, and plans naming people who have left. The lifecycle is what prevents this — not the templates, not the review checklists, but the explicit, recorded movement of every document through the states above.
