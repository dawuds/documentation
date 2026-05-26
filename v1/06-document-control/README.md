# 06 — Document Control

This section is the **single source of truth** for the state of every document in the ISMS. ISO/IEC 27001:2022 Clause 7.5 requires control of documented information — creation, identification, format, review, distribution, access, retrieval, retention, and disposition. This folder is where that control is operationalised at the suite level (each document also carries its own control metadata, but those are *records* of control; this is the *register* of control).

It exists as a separate section — rather than being scattered across individual documents — so that an auditor, a new ISMS manager, or an inspector can answer the following questions from a **single place**:

- What documents make up the ISMS?
- What is the current status of each?
- Who approved each, and when?
- What changes have been made, by whom, and when?
- Where do superseded versions live, and what replaced them?

---

## Contents

| File | Purpose |
|---|---|
| [`master-document-register.md`](master-document-register.md) | One row per **document**. Current status, version, owner, approver, effective date, next review. The "what exists right now". |
| [`change-log.md`](change-log.md) | One row per **change**. Chronological, cross-document. Every version bump, status transition, retirement. The "what has happened over time". |
| [`approval-register.md`](approval-register.md) | One row per **approval event**. Who approved which version of which document, when, and under what authority. The audit-grade evidence trail. |
| [`archive/`](archive/) | Retained superseded and retired documents. Read-only. Tagged with supersession reason. |

---

## How the three registers relate

The same change shows up in three different views, by design:

```
A change to "Access Control Policy v1.0 → v1.1" creates:

  master-document-register.md      ← single row updated (version 1.0 → 1.1, dates refreshed)
  change-log.md                    ← new row appended (date, change summary)
  approval-register.md             ← new row appended (approver, date, authority)
  archive/access-control-policy-v1.0.md   ← prior version copied here
```

The master register answers *"what is the document right now?"*
The change log answers *"how did we get here?"*
The approval register answers *"who blessed each step, under what authority?"*
The archive answers *"what did the document look like before?"*

You could combine these into one register. The reason not to is that each view serves a different reader: the operator wants the master register, the internal auditor wants the change log, the external auditor or regulator wants the approval register, and the forensic investigator wants the archive.

---

## How updates flow through

When a document changes:

1. The author updates the document itself (new version number, new content, document control table updated at the bottom of the document).
2. The author appends a row to **`change-log.md`**.
3. The approver appends a row to **`approval-register.md`** at the point of approval.
4. The author or document-control owner updates the **`master-document-register.md`** row for that document.
5. If the change is a **major version** (or supersession), the previous version is moved (copied) into **`archive/`** with the supersession metadata at the top of the archived file.

For minor versions (editorial, clarification, link fix), step 5 is optional but recommended for documents under audit.

---

## Ownership

The **document-control owner** is the ISMS Manager (reporting to the CISO). They are not the author of any individual document, but they are accountable for ensuring that every document is properly registered, versioned, reviewed on time, and archived correctly. In smaller organisations this role can be combined with another role; it should not be left unassigned.

---

## Why versioning matters more than people think

Three failure modes that document control prevents:

1. **The phantom policy.** Operators reference a policy version that no longer exists or has been materially changed. Decisions get made against stale rules. Document control means there is one current version, and the path to it is stable.
2. **The unapproved live document.** A document is updated in place without re-approval. An auditor finds a "shall" statement that nobody approved. Document control means every effective version has a named approver and an approval date.
3. **The forensic gap.** After an incident, the question is "what did the policy say at the time of the incident?" Without an archive, that question is unanswerable. Document control means every superseded version is retained for the records-retention period.
