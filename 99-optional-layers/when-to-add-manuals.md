# When to add Manuals

A Manual is an **aggregator** — it bundles related SOPs (and sometimes standards) into a single navigable document for a function. Examples: Security Operations Manual, Identity & Access Management Manual, Change Management Manual.

General Bank in this worked example would maintain a **Security Operations Manual** as the SOC's SOPs grow past ~15–20 documents (today the SOC has a handful of SOPs, so a manual is not yet justified).

---

## When Manuals earn their keep

Add a Manual when **at least one** of the following is true:

| Trigger | Why a Manual helps |
|---|---|
| A function has **15+ SOPs** and operators cannot find what they need quickly | The Manual provides navigation, cross-references, and an at-a-glance view. |
| A function has a **handover-heavy** workforce (shift work, rotation, on-call) | The Manual becomes the on-shift reference. |
| **Auditors and inspectors** repeatedly ask for "everything you do in operations" | A Manual reduces audit prep time materially. |
| A function is being **outsourced or insourced** | The Manual is the artefact handed over. |

## When Manuals do **not** earn their keep

- When the function has fewer than ~10 SOPs — a folder of SOPs with a README is enough.
- When the SOPs change weekly — a Manual will rot. Keep navigation lightweight.
- When you would put policy statements inside the Manual — see the anti-pattern below.

## Anti-pattern — Manual as policy aggregator

The single biggest failure mode for Manuals is mixing **policy-grade statements** with **operational SOPs** in the same document. Symptom: a 200-page "Security Operations Manual" that contains a policy chapter, several standards chapters, twenty SOPs, and a few plans, all jumbled.

- Operators can't find the SOP they need.
- Auditors can't tell what is mandatory.
- The document becomes the single point of failure for the entire ISMS.
- Updates require re-approval of policy authority, slowing the SOPs.

**Rule:** a Manual aggregates documents of the **same layer**. A Security Operations Manual aggregates SOPs. If you need to reference a policy from within the Manual, link to it — don't copy it.

## What good Manuals look like

| Property | Reason |
|---|---|
| **Navigable** | TOC, cross-references, search-friendly headings. Operators land in the right SOP in seconds. |
| **Aggregator, not author** | Each SOP within the Manual has its own owner, version, approval. The Manual itself wraps them. |
| **Versioned at the SOP level, not the Manual level** | When one SOP changes, only that SOP gets a version bump. The Manual's TOC may update, but the Manual is not a single document with a single version. |
| **Owned by the function head** | E.g., the Head of SOC owns the Security Operations Manual. |
| **Linked from the master policy and the function's policy chapter** | So readers know where to go for "how this is done". |

## A worked example — Security Operations Manual contents

| Section | Contents |
|---|---|
| 0. Introduction | Purpose, scope, navigation, ownership. |
| 1. Detection & monitoring | SOC SIEM/EDR/DLP operations SOPs. |
| 2. Triage & response | [SOP-08-01 Incident Triage](../03-procedures/incident-triage-sop.md), escalation SOPs, on-call SOPs. |
| 3. Threat intelligence | TI ingest, TI sharing, TI-driven hunting SOPs. |
| 4. Vulnerability operations | Scanning operations, prioritisation, exception handling. |
| 5. Detection engineering | Use-case lifecycle, detection-tuning, false-positive management. |
| 6. Reporting & metrics | Monthly metrics, RMC pack production, regulator reporting support. |
| 7. Tools & access | SOC tool inventory, access management for SOC personnel, on-call mechanics. |
| Appendices | Forensic procedures, contact lists (cross-reference to IRP). |

Each numbered SOP within the Manual remains a free-standing document in the repo with its own document-control lifecycle. The Manual is a navigation overlay.
