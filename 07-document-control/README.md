# 07 — Document Control

Single source of truth for the state of every document in the v2 ISMS / IT governance suite. Implements ISO/IEC 27001:2022 Clause 7.5 (Control of documented information) and BNM RMiT Section 9.2(h) (effective information system) at the document-control level.

← [Repo home](../README.md)

---

## Contents

| File | Purpose |
|---|---|
| [master-document-register.md](master-document-register.md) | One row per **document**. Current status, version, owner, approver, dates. "What exists now." |
| [change-log.md](change-log.md) | One row per **change event**. Chronological, cross-document. "What has happened over time." |
| [approval-register.md](approval-register.md) | One row per **approval event**. Audit-grade evidence of who approved which version of which document, when, under what authority. |
| [archive/README.md](archive/README.md) | Retained superseded and retired documents. Read-only. |

---

## How updates flow

When a document changes:

1. Update the document itself (new version, content, document-control table at the foot).
2. Append a row to [`change-log.md`](change-log.md).
3. Append a row to [`approval-register.md`](approval-register.md) at approval.
4. Update the corresponding row in [`master-document-register.md`](master-document-register.md).
5. For major-version supersession, copy the prior version to [`archive/`](archive/) with the supersession metadata block prepended.

---

## Ownership

The **ISMS Manager** (under the CISO) is accountable for the document-control suite. They do not author individual documents; they are accountable that every document is properly registered, versioned, reviewed on time, and archived correctly.

For v2 in active build, the design team (assistant + user) maintains the suite. Once the build stabilises and an ISMS Manager is named at GIBB, accountability transfers.

---

## Status

This suite is established as part of v2 Phase 1 Session 4. As Layer 2 / 3 / 4 / 5 / 6 documents are added or revised in subsequent sessions, the suite is updated.
