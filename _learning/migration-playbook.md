# GIBB Migration Playbook — from accreted current state to v2 target

How a real bank with the GIBB profile (Tier-2 Malaysian licensed Islamic bank, NCII-designated, federated GRC, **unstructured / bloat** current state) transitions from its existing accreted policies to the v2 target architecture.

← [_learning home](README.md) · [Repo home](../README.md)

> **Source.** This playbook addresses [DEC-004](../_context/decisions.md) (current-state voice: reorganisation programme). It is part of the `_learning/` overlay — not part of the ISMS itself. It is a consulting / implementation artefact that supports a bank's adoption of the v2 structure.

---

## 1. Pre-migration baseline assessment

Before any migration, GIBB needs to know what it currently has.

### 1.1 Document inventory

| Activity | Owner | Output |
|---|---|---|
| Inventory all existing policies, standards, procedures, plans, registers in the IT / cyber / risk / compliance domain | ISMS Manager + functional heads | Current-state document catalogue |
| Tag each document with: current owner, current approver, current effective date, last review date, current status | ISMS Manager | Catalogue enriched |
| Identify orphaned documents (no current owner, past review date, status unclear) | ISMS Manager | Orphan list |
| Identify duplicate or contradictory documents | ISMS Manager + 2nd line | Conflict list |
| Identify documents containing mixed layers (policy + procedure in same document — the "bloat" anti-pattern) | ISMS Manager | Mixed-layer list |

### 1.2 Gap analysis against v2 target

| Activity | Output |
|---|---|
| Map every current document to a v2 target document (POL-XX, STD-XX, etc.) | Current → Target mapping |
| Identify v2 targets with no current source — these are gaps to author | Gap list |
| Identify current documents with no v2 home — these are either obsolete or pointing to gaps in v2 design | Reverse gap list |

### 1.3 Regulatory currency check

| Activity | Output |
|---|---|
| For each current document: which RMiT issuance does it cite? | Currency status |
| Identify documents citing pre-Nov 2025 RMiT — must be refreshed | Refresh list |
| Identify documents citing Cyber Security Act 2024 / NACSA — if NCII-designated post-CSA 2024, these may be missing | NCII gap list |

---

## 2. Migration approach

Two valid paths:

| Approach | Pros | Cons |
|---|---|---|
| **Big-bang** — replace entire current suite with v2 in single cutover | Clean break; consistent end state; clear governance | High change risk; large effort concentrated; v2 must be fully ready |
| **Incremental** (Recommended) | Lower risk; controlled change; can sequence by criticality | Longer in-flight period; dual maintenance for transition; possible inconsistency window |

GIBB's federated GRC + bloat starting state argues for **incremental migration over 12–18 months**.

---

## 3. Recommended sequence

### 3.1 Phase 1 — Foundation (months 1–2)

| Action | Owner | Why first |
|---|---|---|
| Adopt v2 architecture document (ARCH-001) | Board RMC | Establishes the target structure |
| Adopt v2 TRMF (umbrella framework) | Board RMC | Sets the technology risk governance backbone |
| Adopt v2 CRMF (cyber/CRF per RMiT 11.2) | Board RMC | Regulator-mandated; most critical |
| Establish v2 document control suite | ISMS Manager | Versioning and approval discipline before mass migration |
| Communicate the migration plan to all stakeholders | CISO + CRO | Change management |

### 3.2 Phase 2 — CRMF cascade (months 3–4)

Migrate InfoSec-domain policies under CRMF first — these are the most regulator-watched and typically the best-maintained in the current state.

| Action | Sequencing |
|---|---|
| Migrate POL-04 Information Security Policy | First — Board approval |
| Migrate POL-06 Access Control, STD-AC-01, SOP-AC-01, REG-PAR | Second wave |
| Migrate POL-13 Incident Management, STD-IR-01, SOP-IR-01, PLN-01, REG-INC | Third wave |
| Migrate POL-12, POL-18, POL-19 | Fourth wave |
| Migrate POL-05 Acceptable Use | After above |

For each: copy current content into v2 template; reconcile against v2 anatomy; update RMiT citations to Nov 2025; obtain re-approval; supersede current document via [archive](../07-document-control/archive/) procedure.

### 3.3 Phase 3 — Critical operational cascades (months 5–7)

| Cascade | Priority rationale |
|---|---|
| **BCMF** — POL-14, PLN-02 BCP, PLN-03 DRP, REG-BIA, REG-BCT, REG-DRR | Operational resilience — regulator-watched |
| **TPRMF** — POL-10, POL-19 (already under CRMF), STD-TP-01, SOP-TP-01, REG-TPS, REG-OUT | Material outsourcing — BNM Outsourcing PD |
| **CIMF** — POL-CI-01, STD-CI-01, SOP-CI-02, REG-ROPA, REG-DSR, REG-CDB | Customer data + PDPA + MCIPD |

### 3.4 Phase 4 — Strategic and emerging cascades (months 8–10)

| Cascade |
|---|
| **NCIIF** — POL-23, STD-NC-01, SOP-NC-01, REG-NCN |
| **CloudRMF** — POL-20, STD-CL-01, SOP-CL-01, REG-CL |
| **DGF** — POL-11, STD-DG-01, REG-DA |
| **AIGF** — POL-21, STD-AI-01, SOP-AI-01, REG-AIU, REG-AIM |

### 3.5 Phase 5 — Operational cascade and cross-references (months 11–13)

| Action |
|---|
| Migrate POL-07 Change Mgmt, STD-CM-01, SOP-CM-01, SOP-CM-02 |
| Migrate POL-09 IT Asset Mgmt, STD-AM-01 |
| Migrate POL-15 Physical Security, POL-16 Operations Security |
| Migrate POL-17 Secure Development |
| Cross-reference reconciliation — every framework's Section 14 (Related frameworks) and seams.md alignment |
| Migrate cross-cutting registers — REG-EXC, REG-CAP, REG-VUL, REG-DRL |

### 3.6 Phase 6 — Governance and continuous improvement (months 14–18)

| Action |
|---|
| Migrate POL-01 IT Governance, POL-02 TRM, POL-03 Risk Appetite — Board approval cycle |
| Migrate POL-22 IT Compliance |
| Establish v2 review cycle (annual policy review per Section 6 of every framework) |
| First annual cyber drill under v2 (RMiT 11.16) |
| First full BNM examination under v2 structure |
| First Internal Audit cycle under v2 |
| Retirement of all current-state documents superseded by v2; archive per [07-document-control/archive](../07-document-control/archive/) |

---

## 4. Handling the bloat problem

The "bloat" pattern in the current state — single documents mixing policy + procedure + sometimes plans + sometimes registers — requires **structured deconstruction**.

### 4.1 Identification

For each bloated current document:
- Identify policy-grade statements ("shall" at principle level) → migrate to relevant v2 POL-XX
- Identify standard-grade statements ("shall" with quantification) → migrate to relevant v2 STD-XX
- Identify procedure steps ("do this, then this") → migrate to relevant v2 SOP-XX
- Identify scenario-driven content (activation triggers, response phases) → migrate to relevant v2 PLN-XX
- Identify schemas / data structures → migrate to relevant v2 REG-XX

### 4.2 Avoiding loss

For each statement extracted: confirm it has a destination in v2. If not, either (a) place in v2 target document as a new requirement, or (b) flag as candidate for retirement (with explicit owner sign-off).

### 4.3 Reconciliation

After deconstruction, sample-test by selecting a current operational scenario and walking it through the v2 structure — does every step still have an authoritative document? If not, the migration left a gap.

---

## 5. Stakeholder management

### 5.1 Governance bodies

| Body | Engagement |
|---|---|
| Board | Phase 1 + Phase 6 approval moments; quarterly progress noting |
| Risk Management Committee | Monthly progress + approval of each policy migration |
| Audit Committee | Quarterly progress; first audit under v2 in Phase 6 |
| Shariah Committee | Engagement on Shariah-relevant migrations (POL-17, POL-21, BAI-domain documents) |

### 5.2 First-line operations

| Group | Engagement |
|---|---|
| IT Operations | Heavy engagement on POL-07, POL-08, POL-09, POL-15, POL-16, POL-18 cascade |
| Security Operations | Heavy engagement on CRMF cascade |
| BC team | Heavy engagement on BCMF cascade |
| Procurement + Vendor Mgmt | Heavy engagement on TPRMF cascade |
| Data Office | Heavy engagement on DGF + CIMF cascade |
| AI/Data Science | Heavy engagement on AIGF cascade |

### 5.3 Second line

| Function | Engagement |
|---|---|
| Technology Risk | Champion + reviewer throughout |
| Compliance | Regulatory mapping; BNM / NACSA notifications about structural change |
| DPO | CIMF cascade |
| Shariah Compliance | Shariah overlays |

### 5.4 Third line

| Function | Engagement |
|---|---|
| Internal Audit | Observer through migration; first audit under v2 in Phase 6 |

---

## 6. Regulatory engagement

| Regulator | Engagement |
|---|---|
| **BNM** | Notification of material structural change to ISMS / TRMF / outsourcing documents per applicable BNM PD; engagement at major milestones |
| **NACSA** | Notification of NCII-relevant changes per Code of Practice; revised NCII Operational Policy (POL-23) submitted |
| **PDPA Commissioner** | No formal notification required; updated [REG-ROPA](../06-registers/REG-ROPA-records-of-processing-activity.md) reflects v2 structure |

---

## 7. Success criteria

The migration is complete when:

- Every v2 document is at Effective status with named approver and approval evidence
- No current-state document remains in active circulation (all superseded or retired)
- The master document register at [`../07-document-control/master-document-register.md`](../07-document-control/master-document-register.md) is the single source of truth
- First Internal Audit cycle under v2 produces an audit-ready picture
- First annual cyber drill (RMiT 11.16) is conducted under v2 governance with documented outcomes in [REG-DRL](../06-registers/REG-DRL-cyber-drill-register.md)

---

## 8. Common failure modes (warnings)

| Failure mode | Prevention |
|---|---|
| Big-bang attempted; under-resourced; abandoned half-done | Stick to incremental; don't compress timeline |
| Current documents not retired after migration; two versions in circulation | Strict archive discipline; gating control |
| Specific document migrated without re-approval; treated as v2 by reference only | Every migrated document requires fresh approval under v2 governance |
| Cascade references broken (link rot) | Pre-migration link inventory; post-migration link verification |
| Owner role-changes mid-migration | Track ownership transitions in [REG-CAP](../06-registers/REG-CAP-corrective-action-register.md); reconcile per phase |
| Shariah review skipped on relevant migrations | Shariah Compliance sign-off as gating control for Shariah-relevant cascades |

---

## 9. Timeline summary

```
Month   Phase
1-2     Foundation (architecture, TRMF, CRMF, document control)
3-4     CRMF cascade
5-7     BCMF + TPRMF + CIMF
8-10    NCIIF + CloudRMF + DGF + AIGF
11-13   Operational cascade + cross-references + cross-cutting registers
14-18   IT Governance cascade + first cycles (audit, drill, examination) under v2
```

12–18 month migration is typical for an unstructured / bloat starting state.
