# Architecture Decision Records (ADRs)

Append-only log of context decisions binding the v2 deliverable.

| | |
|---|---|
| **Owner** | Design team (assistant + user) |
| **Updated** | 2026-05-27 |

---

## Decision summary

| ID | Decision | Status |
|---|---|---|
| DEC-001 | v2 supersedes v1 in structure; v1 InfoSec content reusable | Locked |
| DEC-002 | Bank persona: General Islamic Bank Berhad (GIBB) | Locked |
| DEC-003 | GRC structure: federated | Locked |
| DEC-004 | Current state voice: unstructured / bloat (reorganisation programme) | Locked |
| DEC-005 | Framework taxonomy: RMiT-led, COBIT taxonomy, ITIL + ISO as practice depth | Locked |
| DEC-006 | Layer 2 bank-authored framework documents: nine | Locked |
| DEC-007 | CRMF naming convention with explicit CRF per RMiT Section 11.2 | Locked |
| DEC-008 | Three framework seams (DGF/CIMF, TPRMF/CloudRMF, TRMF/CRMF) defined | Locked |
| DEC-009 | DGF stands alone (not folded into CIMF) | Locked |
| DEC-010 | AIGF built in full now; re-anchor when BNM publishes AI PD | Locked |
| DEC-011 | Output format: document suite + structured tables; picture-first | Locked |
| DEC-012 | Role: Senior IT Governance and Technology Risk Consultant — see [role.md](role.md) | Locked |
| DEC-013 | Outcome: Phase 1 = 00-architecture + 9 frameworks + TRMF cascade; canonical first framework is TRMF; cascade is from TRMF — see [outcome.md](outcome.md) | Locked |

---

## DEC-001 — v1 → v2 relationship

**Decision:** v2 supersedes v1 in **structure**. v1's Information Security content (14 policies, 2 standards, 2 SOPs, IR Plan, registers) is **reusable** for the Information Security Policy sitting under CRMF as a Layer 3 document.

**Reason:** The v1 ISMS is too narrow to anchor IT governance for a Tier-2 Islamic NCII bank. A broader spine is needed. But the v1 investment in InfoSec specifically remains valid.

**Alternatives considered:** (a) v2 contains v1 — rejected, v1's voice is consulting deliverable not internal blueprint; (b) v2 parallel to v1 — rejected, duplication.

---

## DEC-002 — Bank persona

**Decision:** Bank is **General Islamic Bank Berhad (GIBB)**.

**Reason:** Continuity with v1's "General Bank" naming. Adds "Islamic Berhad" to signal Islamic banking license and NCII designation under Malaysian law.

**Attributes:**
- Tier-2 Malaysian licensed Islamic bank (BNM-licensed under IFSA 2013)
- NCII-designated under Cyber Security Act 2024
- Single-Malaysia geography
- Federated GRC function

---

## DEC-003 — GRC function structure

**Decision:** **Federated GRC** — Tech Risk under CRO, Compliance under CCO, Internal Audit under Audit Committee. Coordinated but distinct.

**Reason:** Most common shape for Tier-2 Malaysian banks. Matches the three-line model expectation in BNM RMiT.

**Implication for blueprint:** Must show seams and coordination mechanisms; multiple owners per cross-cutting concern.

---

## DEC-004 — Current state voice

**Decision:** Blueprint voice is **reorganisation programme** — GIBB has existing IT/cyber/risk policies and procedures, accreted over years, mixed and unstructured. v2 maps existing artefacts to the target architecture; it does not pretend greenfield.

**Reason:** Matches a realistic Tier-2 Malaysian bank starting position. Avoids the "aspirational target state with no migration path" failure mode.

---

## DEC-005 — Framework taxonomy and anchor

**Decision:** **RMiT-led overall, COBIT 2019 as structural taxonomy, ITIL 4 + ISO standards as practice depth.**

- Document headings open with **RMiT clause(s)** — primary regulatory mandate
- Each document **tagged with COBIT objective(s)** — international taxonomy
- Practice frameworks plug into specific COBIT objectives (ITIL 4 into DSS, ISO 27001 into APO13, ISO 22301 into DSS04)

**Reason:** RMiT is binding. COBIT is the recognised IT governance taxonomy. ITIL and ISO provide operational depth where the framework structure alone is insufficient.

---

## DEC-006 — Layer 2 bank-authored framework documents

**Decision:** Nine Layer 2 framework documents authored by GIBB.

| # | Framework | Acronym | Source / mandate |
|---|---|---|---|
| 1 | Technology Risk Management Framework | TRMF | RMiT Section 9.2 |
| 2 | Cyber Risk Management Framework | CRMF | RMiT Section 11.2 (containing CRF) |
| 3 | Business Continuity Management Framework | BCMF | BNM BCM PD + RMiT 10.24–10.45 |
| 4 | Third Party Risk Management Framework | TPRMF | BNM Outsourcing PD + RMiT 10.46–10.49 + Section 14 |
| 5 | Customer Information Management Framework | CIMF | BNM MCIPD + PDPA 2010 |
| 6 | NCII Compliance Framework | NCIIF | Cyber Security Act 2024 + NACSA Code of Practice |
| 7 | Cloud Risk Management Framework | CloudRMF | RMiT 10.50–10.52 + Appendix 10 + BNM Cloud TRAG |
| 8 | Data Governance Framework | DGF | Industry practice; emerging BNM signal |
| 9 | AI Governance Framework | AIGF | NIST AI RMF + EU AI Act + BNM Discussion Paper on Responsible AI |

**Reason:** NCII + Islamic + forward-looking AI/data posture justifies the breadth. Defensible to BNM and NACSA examiners.

**Alternatives considered:** Five-core only (rejected, under-emphasises NCII and cloud); seven (rejected, under-equipped on data and AI).

**Hard-marker note:** Nine framework documents is on the upper end for a Tier-2 bank. Be ready to defend against "framework proliferation" critique.

---

## DEC-007 — CRMF naming

**Decision:** **CRMF (Cyber Risk Management Framework)** as the document title, with an explicit statement at the front: *"This is GIBB's Cyber Resilience Framework (CRF) for the purpose of BNM RMiT Section 11.2; the nine mandatory CRF elements at Section 11.3 are addressed in this CRMF."*

**Reason:** CRMF is the industry-common naming and is broader in scope (risk + resilience). The explicit RMiT statement preserves regulatory pinning.

---

## DEC-008 — Three framework seams

**Decision:** Three seams resolved as follows:

| Seam | Resolution |
|---|---|
| **DGF / CIMF** | DGF owns enterprise-wide data principles for all data assets. CIMF owns customer data specifically + MCIPD + PDPA regulatory layer. Both documents state: "Customer data is governed by DGF principles AND additionally subject to CIMF customer-specific requirements." |
| **TPRMF / CloudRMF** | TPRMF owns the third-party relationship lifecycle (selection, contract, monitoring, exit). CloudRMF owns the cloud-specific risk content (shared-responsibility, residency, exit complexity). A cloud provider engagement triggers BOTH. |
| **TRMF / CRMF** | Peer-level, cross-referenced. TRMF covers RMiT Section 9.2 + broader IT governance. CRMF covers RMiT Section 11.2 cyber resilience capabilities. |

---

## DEC-009 — DGF stands alone

**Decision:** Data Governance Framework is a peer Layer 2 document, **not** folded into CIMF.

**Reason:** Data governance scope (all data assets) is broader than customer data alone. Folding loses the architecture/lineage/AI-training-data lens.

**Trade-off accepted:** Overlap with CIMF on customer data — resolved by seam in DEC-008.

---

## DEC-010 — AIGF built in full, re-anchor on BNM AI PD

**Decision:** AIGF authored as a complete framework now, anchored on NIST AI RMF + EU AI Act + BNM Discussion Paper. Document states: *"This AIGF will be re-anchored when BNM issues a formal AI policy document."*

**Anchor stack:**
- NIST AI Risk Management Framework 1.0 (January 2023) + Generative AI Profile (July 2024)
- EU AI Act (2024) — risk-classification taxonomy
- BNM Discussion Paper on Responsible AI (informative)
- MAS FEAT principles (Singapore cross-jurisdictional reference)
- ISO/IEC 42001:2023 — AI Management System

**Reason:** Forward-looking posture matches NCII designation. Stub-only risks gap visible to forward-looking auditors.

---

## DEC-011 — Output format

**Decision:** **Document suite + structured tables, picture-first.** Top-level opens with framework diagram. Tables for controls library, RACI, KPI catalogue, regulatory mapping matrix. Stay in markdown; do not optimise for any specific GRC tool.

**Reason:** Continues v1 format (markdown, navigable folder structure) which works for the federated GRC audience.

---

## DEC-012 — Role

**Decision:** Role for the v2 build is **Senior IT Governance and Technology Risk Consultant** with Malaysian Islamic NCII bank experience. Full role string in [role.md](role.md). Binds tone, expertise, audience awareness, and discipline (eight rules including mandatory-vs-advisory, clause-level citation with issuance dates, source-chain caveats, Shariah overlay acknowledgement).

**Reason:** A role string is the most reliable way to bind voice and discipline across a multi-document build. Without it, drift across documents is the most common failure mode.

---

## DEC-013 — Outcome

**Decision:** Phase 1 v2 deliverable comprises `00-architecture/`, 9 Layer 2 framework documents (TRMF, CRMF, BCMF, TPRMF, CIMF, NCIIF, CloudRMF, DGF, AIGF), and one full cascade **from TRMF** down to registers. Full spec in [outcome.md](outcome.md).

- Canonical worked example: **TRMF** (drafted first to lock the 17-section anatomy)
- Cascade exemplar: **TRMF** (broader scope than CRMF would be; covers tech-risk + IT governance content)
- Build sequence: 4 sessions; tonight = Session 1 (architecture + framework template + TRMF only)

**Reason:** TRMF is the foundational tech risk framework; cascading from it demonstrates the IT governance breadth. Choice of TRMF-as-cascade-root over CRMF accepted with the trade-off that TRMF cascade is heavier than CRMF cascade would be. v1 InfoSec content remains reusable for CRMF in subsequent sessions.

**Alternatives considered:** CRMF cascade (would reuse v1 content directly; rejected in favour of TRMF cascade for IT-governance breadth); pause and start tomorrow (rejected — user committed to tonight start).
