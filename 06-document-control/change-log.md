# Change Log

Chronological, cross-document log of every change to a document in the ISMS. Append-only. The most recent change appears at the top.

| | |
|---|---|
| **Owner** | ISMS Manager |
| **Cadence** | Continuous — appended at every document change |
| **Implements** | ISO/IEC 27001:2022 Clause 7.5.3 (control of changes) |

---

## Change-type legend

| Type | Definition | Re-approval required? |
|---|---|---|
| **Major** | Substantive change to mandatory statements (new "shall", removed "shall", scope change, threshold change) | Yes — full review and approval |
| **Minor** | Clarification, editorial, link fix, formatting | No — author + ISMS Manager sign-off only |
| **Status** | Transition between states (Effective → Under Revision, Superseded, Retired) | Per the originating event |

---

## Log

> Most recent first. Worked example for General Bank — dates illustrative.

| Date | Document | From → To | Type | Summary | Author | Approver | Approval evidence |
|---|---|---|---|---|---|---|---|
| 2026-04-22 | STD-02-01 Password & Authentication Standard | 1.0 → 1.1 | Minor | Updated example PAM vendor reference; clarified service-account rotation language. No "shall" changes. | ISMS Manager | CISO | Email 2026-04-22, ref ISMS-CHG-2026-007 |
| 2026-04-10 | SOP-02-01 Joiner/Mover/Leaver SOP | 1.0 → 1.1 | Minor | Updated tool reference following IDP migration from Tool-A to Tool-B. Steps unchanged. | Head of IAM | Head of IAM | Workflow ID JML-CHG-2026-002 |
| 2026-03-18 | REG-PAR Privileged Access Review Register | — | Status | Q1 2026 review completed. 412 privileged accounts reviewed; 7 access removals; 0 escalations. | Head of IAM | Head of IAM | Q1-2026-PAR.xlsx archived in evidence repository |
| 2026-03-05 | REG-INC Incident Register | — | Status | Incident INC-2026-014 closed (severity SEV-3, phishing campaign, contained within 4 hours of detection). Post-incident review filed. | CISO | CISO | PIR-INC-2026-014 |
| 2026-02-01 | All Tier 1 policies (POL-00 through POL-14) | — | Status | Initial ISMS suite went Effective following RMC approval on 2026-01-15 and Board approval of POL-00 on 2026-01-15. | CISO | Board / RMC | Board minutes 2026-01-15; RMC minutes 2026-01-15 |
| 2026-01-25 | All Tier 3 SOPs (SOP-02-01, SOP-08-01) | — | Status | Initial SOPs approved by respective process owners. | Process owners | Process owners | Workflow approvals retained |
| 2026-01-20 | All Tier 2 standards (STD-02-01, STD-08-01) | — | Status | Initial standards approved by CISO. | CISO | CISO | Email approval 2026-01-20 |
| 2026-01-15 | POL-00 Information Security Policy | Draft → Effective (1.0) | Major | Initial Board-approved version of the master policy. | CISO | Board of Directors | Board minutes 2026-01-15, agenda item 4.2 |
| 2026-01-15 | POL-01 through POL-14 (supporting policies) | Draft → Effective (1.0) | Major | Initial RMC-approved versions of the supporting policy suite. | CISO + function heads | Risk Management Committee | RMC minutes 2026-01-15, agenda item 6.1 |
| 2025-12-10 | All Tier 1 policies | In Review → Pending Approval | Status | 2nd-line review complete (Technology Risk, Compliance). 14 comments resolved. | CISO | — | Review pack TR-2025-Q4-ISMS |
| 2025-11-20 | All Tier 1 policies | Draft → In Review | Status | First-pass drafts complete. Issued for 2nd-line review. | CISO + function heads | — | Drafting pack DR-2025-ISMS-v0.9 |

---

## Maintenance

Every change to a document **must** generate a row in this log on the same business day as the change. The ISMS Manager spot-checks the log monthly against the master register and the individual document control tables to detect drift.

For audit purposes, this log is the **forensic source** for "what changed and when" questions. Individual documents carry their own change history at the foot of the document, but only this log is cross-document and date-ordered.
