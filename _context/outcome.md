# Outcome — v2 deliverable definition

What "done" means for v2.

← [_context home](README.md) · [decisions.md](decisions.md) (see DEC-013)

---

## Folder structure (v2)

```
documentation/
├── README.md                   ISMS-index voice; opens with framework picture
├── CLAUDE.md                   Working rules
├── _context/                   Design decisions (this folder)
├── _templates/                 Templates for v2 document types
├── v1/                         Snapshot (locked)
│
├── 00-architecture/            The picture + narrative (Layer 0–2 model)
├── 01-frameworks/              Layer 2 — the 9 bank-authored framework docs
├── 02-policies/                Layer 3 — cascade from frameworks
├── 03-standards/               Layer 4 — measurable, mandatory
├── 04-procedures/              Layer 5 — operational SOPs
├── 05-plans/                   Scenario-driven (IRP, BCP, DRP)
├── 06-registers/               Layer 6 — evidence
└── 07-document-control/        Master register, change log, approvals, archive
```

---

## Anatomy of a Layer 2 framework document (the "done" spec)

Every Layer 2 framework (TRMF, CRMF, BCMF, TPRMF, CIMF, NCIIF, CloudRMF, DGF, AIGF) follows the same 17-section anatomy. Length target: 600–1,200 lines.

| # | Section | Purpose |
|---|---|---|
| — | Metadata block | Document ID, version, owner, approver, dates, regulatory anchors (RMiT / COBIT / practice standards) |
| 1 | Foreword | Short Board / RMC sign-off statement |
| 2 | Purpose | Why this framework exists |
| 3 | Scope | In / out |
| 4 | Definitions | Framework-specific terms |
| 5 | Governance | Three-line model, RACI, approval authorities |
| 6 | Framework principles | 6–10 **shall** principles |
| 7 | Framework structure | The model (diagram + narrative) |
| 8 | Lifecycle / operating model | How the framework operates |
| 9 | Implementation requirements | What cascades (policies, standards, SOPs, registers) |
| 10 | Performance measurement | KPIs / KRIs / KGIs |
| 11 | Reporting and escalation | Who reports what, when, to whom |
| 12 | Exceptions | Documented deviation process |
| 13 | Independent review | Internal audit + external assurance |
| 14 | Related frameworks | Cross-references (per [seams.md](seams.md)) |
| 15 | References | Regulatory and standards citations |
| 16 | Document control | Version history |

---

## Phase 1 scope

**Deliverables:**
- `00-architecture/` — the picture-first opener (Layer 0/1/2 model, framework relationships, conventions)
- `_templates/framework-template.md` — the 17-section spec
- `01-frameworks/` — all 9 Layer 2 framework documents
- **One cascade from TRMF down to registers** — ~5–10 policies + standards + SOPs + 1 plan + registers under TRMF, re-anchored from v1 content where applicable
- Updated root `README.md` and `CLAUDE.md`

**Sizing.** Realistically 10,000–15,000 lines of markdown. Multi-session build.

**Out of scope for Phase 1:**
- Cascades for the other 8 Layer 2 frameworks (CRMF, BCMF, etc.) — future work
- GRC-tool ingestion format (markdown only)
- Migration playbook from existing GIBB documents to v2 structure — separately scoped

---

## Build sequence

| Session | Output |
|---|---|
| **Session 1 (tonight)** | `00-architecture/` + `_templates/framework-template.md` + `01-frameworks/README.md` + **TRMF.md (canonical worked example, full draft)** |
| Session 2 | Remaining 8 Layer 2 frameworks (CRMF, BCMF, TPRMF, CIMF, NCIIF, CloudRMF, DGF, AIGF) |
| Session 3 | TRMF cascade — policies, standards, SOPs, plan, registers |
| Session 4 | Document control suite for v2; reconciliation; final README polish |

Each session ends with a commit-and-push checkpoint.

---

## Quality bar

- Every framework document satisfies the 17-section anatomy with substantive content (no skeletons).
- Every "shall" statement carries an anchor citation (RMiT clause + COBIT objective + practice standard where applicable).
- Every framework cross-references the others it interacts with per [seams.md](seams.md).
- Voice and discipline per [role.md](role.md) — including source-chain caveats on derivative claims and Shariah overlay acknowledgement where applicable.
- Document control discipline: every document carries metadata block + change history; document-control suite tracks all docs.

---

## Definition of done — Phase 1

Phase 1 is **done** when:
- `00-architecture/` is complete and readable as a stand-alone "what is the GIBB IT governance architecture" briefing
- All 9 Layer 2 framework documents are drafted to the 17-section anatomy with content depth appropriate to each framework's regulatory weight
- The TRMF cascade is complete — at least one cascade is fully visible from policy to register
- All documents are registered in `07-document-control/master-document-register.md`
- All commits pushed; v2 visible alongside v1 at the GitHub repo