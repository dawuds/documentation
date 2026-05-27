# CLAUDE.md — `documentation/` (v2)

Working rules for the assistant operating on v2 of this repo.

## Repo state

The repo holds two versions:

- **v1** — locked snapshot at [`v1/`](v1/). Tagged `v1.0` in git. Do not edit.
- **v2** — active build at the root. The bank is **General Islamic Bank Berhad (GIBB)**, a Tier-2 Malaysian licensed Islamic bank designated as an NCII entity under the Cyber Security Act 2024.

## Binding context

Every v2 working session begins by consuming the context locked in [`_context/`](_context/). The binding documents are:

| File | What it binds |
|---|---|
| [`_context/decisions.md`](_context/decisions.md) | 13 ADRs covering scope, persona, framework stack, role, outcome |
| [`_context/role.md`](_context/role.md) | The role string — Senior IT Governance and Technology Risk Consultant — including voice and discipline rules |
| [`_context/framework-stack.md`](_context/framework-stack.md) | Layer 0 (regulatory) / Layer 1 (reference) / Layer 2 (9 bank-authored frameworks) |
| [`_context/seams.md`](_context/seams.md) | DGF/CIMF, TPRMF/CloudRMF, TRMF/CRMF resolutions |
| [`_context/outcome.md`](_context/outcome.md) | Phase 1 deliverable spec; 17-section framework anatomy |
| [`_context/glossary.md`](_context/glossary.md) | Terminology |

## Component model

| Layer | Folder | Voice | Approver |
|---|---|---|---|
| Architecture | `00-architecture/` | Authoritative current state, picture-first | Board Risk Management Committee |
| Layer 2 frameworks | `01-frameworks/` | Authoritative bank-authored framework — 17-section anatomy | Board Risk Management Committee |
| Layer 3 policies | `02-policies/` | "shall" — principle-level | RMC (suite); Board (master) |
| Layer 4 standards | `03-standards/` | "shall" — measurable | CISO / function head |
| Layer 5 procedures | `04-procedures/` | "do this, then this" | Process owner |
| Plans | `05-plans/` | Scenario-driven | RMC |
| Layer 6 registers | `06-registers/` | Data + evidence | Process owner |
| Document control | `07-document-control/` | Meta — register / log / approval / archive | ISMS Manager |
| Templates | `_templates/` | Skeleton | — |
| Context (design) | `_context/` | Design material, not deliverable | Design team |

## Voice and discipline (per [_context/role.md](_context/role.md))

- **Hard marker.** Push back on weak reasoning; ask "why" before "how".
- Distinguish **mandatory** ("shall") from **advisory** ("should") in every sentence.
- Cite **specific clauses with issuance dates** ("RMiT Section 11.18, 28 Nov 2025"), not document names.
- Use **source-chain caveats** for derivative claims (e.g., the 4-hour BNM notification clock).
- Distinguish **bank-authored frameworks (Layer 2)** from **external reference frameworks (Layer 1)** explicitly.
- Acknowledge the **Shariah Governance overlay** where it applies (product-system Build-Acquire-Implement scope).
- Output uses **RMiT-led headings, COBIT taxonomy tags, ISO/ITIL as practice depth** per [framework-stack.md](_context/framework-stack.md).
- Material on regulation is illustrative, not legal / regulatory advice.

## File-creation discipline

- Every new framework document follows [`_templates/framework-template.md`](_templates/framework-template.md) — 17 sections, no deviation.
- Every new document opens with the standard metadata block (Document ID, Version, Owner, Approver, Effective, Next review, RMiT clauses, COBIT objectives, Practice standards, Additional anchors).
- Cross-references between frameworks per [seams.md](_context/seams.md).
- No "TODO" or "TBC" content in committed documents. Use stubs only where explicitly part of the Phase 1 scope (e.g., the eight pending frameworks listed in [01-frameworks/README.md](01-frameworks/README.md) before their full draft).

## Sanitisation rules

This is a public repo. No real client data, no real personnel names, no real IP addresses or hostnames.

- Organisation name: **General Islamic Bank Berhad (GIBB)** (fictional).
- Personnel: role titles only — never names.
- Systems: generic identifiers; never product names tied to a specific vendor unless that vendor's name is the example point.
- Network addresses: RFC 5737 / RFC 3849 documentation ranges only.

## Common pitfalls (lessons from v1)

1. **Citation drift** — every RMiT citation must be against the **28 November 2025 issuance**. Do not import 2020 RMiT numbering. When in doubt, consult [`_context/glossary.md`](_context/glossary.md) and the architecture document.
2. **Voice drift** — folder READMEs and top-level documents read as authoritative current state, **not** as training material or consulting deliverables. Learning / teaching content goes in `_learning/` (currently absent in v2; will be added only if explicitly required).
3. **Framework wish-lists in committed documents** — wish-lists belong in `_context/open-questions.md`, not in framework documents themselves. A bank's framework does not advertise incomplete coverage.
4. **Symbol clarity** — use the word "Section" instead of the §  character. Use the word "Clause" for ISO references.

## Workflow

When asked to add a new document:

1. Confirm the layer (Layer 2 framework, Layer 3 policy, etc.).
2. Identify the parent framework (which Layer 2 framework cascades into this).
3. Identify the regulatory anchor (RMiT clause + COBIT objective + practice standard).
4. Start from the matching template.
5. Wire it into the parent framework's Section 9 (Implementation requirements).
6. Once approved, register in [07-document-control/master-document-register.md](07-document-control/) (when that suite is built).
