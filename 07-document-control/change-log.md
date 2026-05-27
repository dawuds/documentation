# Change Log

Chronological, cross-document log of every change. Append-only. Most recent first.

| | |
|---|---|
| **Owner** | ISMS Manager |
| **Cadence** | Continuous |
| **Implements** | ISO/IEC 27001:2022 Clause 7.5.3 (control of changes) |

---

## Change-type legend

| Type | Definition | Re-approval required |
|---|---|---|
| Major | Substantive change to mandatory statements | Yes |
| Minor | Clarification, editorial, link fix | No |
| Status | State transition (Draft → Effective, Superseded, Retired) | Per event |
| Create | New document | Yes — initial approval |

---

## Log

| Date | Document | From → To | Type | Summary | Author | Approver | Evidence |
|---|---|---|---|---|---|---|---|
| 2026-05-28 | CRMF cascade — 7 policies, 2 standards, 2 SOPs, 1 plan, 3 registers (15 documents) | v1 1.x → v2 1.0 | Create (re-anchor) | Re-anchored v1 InfoSec content under CRMF per [DEC-001](../_context/decisions.md). Documents: POL-04 Information Security Policy (master under CRMF), POL-05 Acceptable Use, POL-06 Access Control, POL-12 Cryptography, POL-13 Incident Management, POL-18 Vulnerability Management, POL-19 Supplier Security; STD-AC-01 Password & Authentication, STD-IR-01 Incident Classification & Severity; SOP-AC-01 JML, SOP-IR-01 Incident Triage; PLN-01 Incident Response Plan; REG-INC, REG-PAR, REG-SOA. Substantive content preserved from v1 (including the source-chain caveated 4-hour BNM notification clock per RMiT 11.18). Metadata: Parent framework(s) and COBIT objective(s) added; bank normalised to GIBB; internal references migrated to v2 paths and v2 document IDs. | Design team | (Pending GIBB approval per document) | Repository commit; v2 Session 5 |
| 2026-05-27 | 07-document-control suite (all four files) | n/a → v1.0 | Create | Established document control suite for v2 build — master register, change log, approval register, archive structure. | Design team | (Pending GIBB ISMS Manager assignment) | Repository commit; v2 Session 4 |
| 2026-05-27 | 06-registers: REG-TR | n/a → 1.0 | Create | Technology Risk Register established under TRMF, with full schema, acceptance authority matrix, review cadence by rating, 10-row worked example. | Design team | (Pending CRO sign-off) | Repository commit; v2 Session 3 |
| 2026-05-27 | 04-procedures: SOP-CM-01 | n/a → 1.0 | Create | Change Authorisation SOP — 9-step procedure operationalising STD-CM-01 §3.2 with Shariah review step for Islamic product systems. | Design team | (Pending Head of IT Operations sign-off) | Repository commit; v2 Session 3 |
| 2026-05-27 | 03-standards: STD-CM-01, STD-AM-01 | n/a → 1.0 | Create | Change Management Standard and IT Asset Management Standard — first standards under TRMF cascade. | Design team | (Pending CIO sign-off) | Repository commit; v2 Session 3 |
| 2026-05-27 | 02-policies: POL-01 through POL-22 (10 policies) | n/a → 1.0 | Create | TRMF-origin Layer 3 policies — IT Governance, Tech Risk Management, Risk Appetite, Change Management, Capacity, IT Asset, Physical Security, Operations Security, Secure Development, IT Compliance. | Design team | (Pending Board / RMC sign-off per document) | Repository commit; v2 Session 3 |
| 2026-05-27 | _templates: policy / standard / procedure / plan / register templates | n/a → 1.0 | Create | Layer 3-6 document templates established. | Design team | Design team | Repository commit; v2 Session 3 |
| 2026-05-27 | 01-frameworks: CRMF, BCMF, TPRMF, CIMF, NCIIF, CloudRMF, DGF, AIGF | n/a → 1.0 | Create | Eight remaining Layer 2 framework documents drafted following 17-section anatomy established in TRMF (Session 1). | Design team | (Pending Board RMC sign-off per document) | Repository commit; v2 Session 2 |
| 2026-05-27 | 01-frameworks: TRMF | n/a → 1.0 | Create | Technology Risk Management Framework — canonical Layer 2 worked example, ~950 lines implementing RMiT Section 9 (9.1-9.5) with COBIT EDM03/APO12/APO01 and ISO 31000:2018 anchors. | Design team | (Pending Board RMC sign-off) | Repository commit; v2 Session 1 |
| 2026-05-27 | _templates: framework-template.md | n/a → 1.0 | Create | 17-section anatomy spec for every Layer 2 framework document. | Design team | Design team | Repository commit; v2 Session 1 |
| 2026-05-27 | 00-architecture: ARCH-001 | n/a → 1.0 | Create | GIBB IT Governance Architecture — picture-first opener with Layer 0/1/2 model, framework relationships, conventions, Shariah and NCII overlays. | Design team | (Pending Board RMC sign-off) | Repository commit; v2 Session 1 |
| 2026-05-27 | _context: outcome.md, role.md | n/a → 1.0 | Create | Phase 1 outcome spec (DEC-013) and role string (DEC-012) locked. | Design team | Design team | Repository commit |
| 2026-05-26 | v1 entire suite | Active → Snapshot at v1.0 | Status | v1 ISMS snapshotted into `v1/`; tagged `v1.0` in git. New v2 build commenced at root with broader IT-governance scope. | Design team | Design team | Repository commit; git tag v1.0 |
| 2026-05-26 | _context (initial six files) | n/a → 1.0 | Create | Design context locked for v2 — 11 ADRs covering scope, persona, framework taxonomy, 9-framework Layer 2 set, three seams, DGF/AIGF, output format. | Design team | Design team | Repository commit |
| 2026-05-26 | v1 documents (all) | Various → +0.1 (minor sweep) | Minor (Regulatory update) | Re-aligned every BNM RMiT citation to the 28 November 2025 issuance from the June 2020 issuance previously cited. Added Cyber Resilience Framework structure to v1 POL-08. Added Cyber Security Act 2024 + NACSA references to v1 POL-00 and POL-14. Pinned 4-hour BNM notification with source-chain caveat. | Design team | (v1 retrospective; locked snapshot) | Pre-v1.0 tag commits |

---

## Maintenance

Every change to a document **must** generate a row here on the same business day as the change. The ISMS Manager spot-checks this log monthly against the master register and individual document control tables.

For audit purposes, this log is the **forensic source** for "what changed and when." Individual documents carry their own change history at the foot of the document; only this log is cross-document and date-ordered.
