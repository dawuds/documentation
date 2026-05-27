# Archive — superseded and retired documents

Retained for audit, forensic, and regulatory record-keeping purposes.

| | |
|---|---|
| **Owner** | ISMS Manager |
| **Access** | Read-only |
| **Retention** | Minimum 7 years from supersession or retirement (subject to records retention schedule). BNM-licensed Islamic institutions: align with the BNM record-keeping requirements for documents that evidence regulatory obligations. |

---

## What goes here

| Trigger | Action |
|---|---|
| A document is **superseded** by a new major version | The prior version is copied here, renamed `<document-id>-v<old-version>.md`, with a supersession block prepended (see below). |
| A document is **retired** (activity ceased, scope change, replacement reorganisation) | The final effective version is copied here, with a retirement block prepended. |

Minor-version supersessions (1.0 → 1.1) are not required to be archived, but for documents under audit scrutiny it is good practice.

---

## Supersession / retirement metadata block

Every archived document carries this block at the very top, **before** the original content:

```markdown
> ## ARCHIVED — SUPERSEDED / RETIRED
>
> **Document:** [ID + Title]
> **Archived version:** [version]
> **Status:** Superseded | Retired
> **Effective period:** [YYYY-MM-DD] to [YYYY-MM-DD]
> **Superseded by:** [link to successor, or "N/A — retired"]
> **Reason:** [why this version was retired or replaced]
> **Approved retirement by:** [authority + role]
> **Archived on:** [YYYY-MM-DD]
> **Archived by:** [role]
>
> This document is retained for audit and forensic reference only. It is **not** authoritative.
> Do not rely on this document for current obligations — consult the current effective version.
```

This block makes it unambiguous to any later reader that the document is no longer authoritative, why it was archived, and where to find what replaced it.

---

## Naming convention

`<DOC-ID>-v<MAJOR.MINOR>-<superseded|retired>-<YYYY-MM-DD>.md`

Examples:
- `TRMF-v1.0-superseded-2027-03-15.md` — TRMF v1.0, superseded by v2.0
- `SOP-decommissioned-system-X-v2.3-retired-2026-09-30.md` — SOP retired with the system it documented

---

## Worked example

See [`../../v1/06-document-control/archive/example-superseded-document.md`](../../v1/06-document-control/archive/example-superseded-document.md) for a worked example of an archived document with the supersession block in place (from v1).

---

## Why retention matters

Three scenarios that an archive answers:

1. **Forensic.** "On the date of incident X, what did our policy say?" The current document does not answer this if it has been revised since. The archive does.
2. **Regulatory.** A BNM or NACSA inspection may request the version of a policy that was in force during the inspection period. The archive provides this verbatim.
3. **Litigation.** A dispute about an action taken under a then-current policy may require the version of that policy at the time of the action. The archive preserves it intact.

Without an archive, all three scenarios fail — and the failure is irrecoverable, because the information has been overwritten in the live document.
