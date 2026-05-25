# 00 — Foundations

The **conceptual base** of the documentation suite. Everything else in this repo assumes you have read these. Start here.

← [Back to repo home](../README.md)

---

## Why this section exists

A documentation suite without a shared mental model of *what each layer is for*, *who approves what*, and *how documents move through their lifecycle* will accumulate inconsistencies within months. This section establishes that mental model.

For a working ISMS, a regulator or auditor will expect to find this material either as a stand-alone preamble (as in this repo) or as the introductory chapter of the master policy. We keep it separate so the master policy remains focused on mandatory **shall** statements.

---

## Read in this order

1. **[document-hierarchy.md](document-hierarchy.md)** — the nine-layer reference pyramid (Charter → Policy → Standard → Procedure → Guideline → Baseline → Plan → Manual → Register). What each layer is, who approves it, how stable it is.
2. **[tiering-model.md](tiering-model.md)** — what real banks actually run (M1 through M4). General Bank operates at M3. Why M3 is the audit-defensible minimum and when to expand.
3. **[governance-model.md](governance-model.md)** — three-line model, approval authority per document type, review cadence, exception management, version control.
4. **[document-lifecycle.md](document-lifecycle.md)** — the states a document moves through (Draft → In Review → Pending Approval → Approved → Effective → Under Revision → Superseded / Retired) and the gates between them.
5. **[regulatory-mapping-reference.md](regulatory-mapping-reference.md)** — the canonical mapping every document uses when citing BNM RMiT (28 Nov 2025), ISO/IEC 27001/27002, and adjacent Malaysian regulation. **Binding on all other documents.**

---

## How to use this section

| You are… | Read… |
|---|---|
| A practitioner new to ISMS suites | All five in order. ~45 minutes. |
| A consulting client evaluating "what good looks like" | The hierarchy + the tiering model + the lifecycle. ~25 minutes. |
| An auditor preparing an ISMS inspection | The hierarchy + the governance model + the regulatory mapping reference. ~30 minutes. |
| A CISO adapting this repo for your own org | All five, then go straight to [`01-policies/00-information-security-policy.md`](../01-policies/00-information-security-policy.md). |

---

## What this section is **not**

It is not the ISMS itself. None of the documents here are board-approved policy — they are explanatory material. The board-approved master is [`POL-00 Information Security Policy`](../01-policies/00-information-security-policy.md). Read this section first to understand the structure, then read POL-00 to see the structure in operation.

---

## Cross-links

- The next section down the cascade: [`01-policies/`](../01-policies/) — the policy layer (Tier 1).
- The registers that operationalise this section's governance: [`06-document-control/`](../06-document-control/) — master register, change log, approvals, archive.
- The templates that implement the structures defined here: [`_templates/`](../_templates/) — one template per document type.
