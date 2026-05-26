# CLAUDE.md — `documentation/`

Repo working rules. This file is for the assistant working in this repo, not for the client reading the documentation.

## Repo purpose

A worked example of a best-practice IT governance documentation suite for a Malaysian licensed bank ("General Bank"), anchored on ISO/IEC 27001:2022 + ISO/IEC 27002:2022, with BNM RMiT mapping. It is a *teaching and demo* artefact, not a certified ISMS.

## Audience

Two audiences. Keep both in mind:
1. **A consulting client** evaluating "what good looks like" for their own documentation suite.
2. **A practitioner** (CISO, ISMS manager, internal auditor) learning the cascade pattern.

## Component model

| Layer | Folder | Voice | Approver in the worked example |
|---|---|---|---|
| Foundations (meta) | `00-foundations/` | Explanatory | — |
| Policy | `01-policies/` | "shall" — principle-level | Board (master) / Risk Committee (suite) |
| Standard | `02-standards/` | "shall" — measurable | CISO |
| Procedure / SOP | `03-procedures/` | "do this, then this" | Process owner |
| Plan | `04-plans/` | scenario-driven | CISO (IR), COO (BC/DR) |
| Register | `05-registers/` | data + first-row worked example | Process owner |
| Document control | `06-document-control/` | meta — register/log/approval/archive | ISMS Manager |
| Optional | `99-optional-layers/` | Explanatory | — |
| Template | `_templates/` | skeleton | — |
| Learning overlay | `_learning/` | **Not part of the ISMS.** Reading paths and extension roadmap for practitioners/clients learning from the suite. | — |

## Citation discipline

- Every "shall" statement that implements an ISO 27002:2022 control must cite the control number (e.g., "(implements ISO/IEC 27002:2022 control 8.2)").
- Every claim about a BNM RMiT requirement must cite the section or appendix.
- **Never assert a regulatory clock or threshold without citation.** If a clock is approximate or needs verification, flag it inline ("⚠ Verify with current RMiT issuance — clock not pinned in this repo").
- Material on regulation is illustrative only — never legal/regulatory advice. The README disclaimer covers the repo; individual documents should also include this caveat where the risk of misreading is high.

## Sanitisation rules

This is a public repo. No real client data, no real personnel names, no real IP addresses or hostnames. Use:
- Organisation name: **General Bank** (fictional).
- Personnel: role titles only ("CISO", "Head of IT Operations") — never names.
- Systems: generic identifiers ("Core Banking System", "Internet Banking Portal") — never product names tied to a specific vendor unless that vendor's name is the example point.
- Network addresses: RFC 5737 / RFC 3849 documentation ranges only.

## Document style

- **Headings**: every document starts with `# Title` then a metadata block (see template).
- **"Shall" vs "should"**: shall = mandatory (policy/standard). should = recommended (guideline). Never mix in the same document.
- **No emojis** in document content. The repo serves a regulated-FS audience.
- **Tables over prose** where the content is comparative or enumerable.
- **Link liberally** between layers — every policy should link to its supporting standards; every standard should link to its SOPs.

## File-creation discipline

- Do not create new top-level folders without updating the README repo map and the foundations explainer.
- Do not create documents outside the established templates without explicit reason.
- Every new policy added to `01-policies/` must be referenced from the master Information Security Policy.
- Every new document **also** requires: a row added to `06-document-control/master-document-register.md`, a row in `06-document-control/change-log.md`, and a row in `06-document-control/approval-register.md` once approved. This is the rule that prevents document-control drift.
- **Voice discipline.** The ISMS proper (folders 00 through 99 and `_templates`) reads as authoritative current state — no audience matrices, time estimates, or reading orders. Teaching content (paths, extension wish-lists, audience-tailored navigation) goes in `_learning/`, not in folder READMEs. Folder READMEs are short, factual, and structural: purpose, document list, anatomy, cross-links.

## Common pitfalls (things the assistant has tripped on before)

1. **Mixing policy and procedure in the same document.** Catch yourself if a document says both "access shall be least-privilege" AND "click the green button in Okta". Split.
2. **Citing ISO 27001 when you mean ISO 27002.** 27001 is the management system; 27002 is the controls. Most "shall" statements implement 27002 controls, not 27001 clauses.
3. **Inventing BNM RMiT clock thresholds.** If unsure, write the rule and flag the clock for verification rather than asserting a number.
4. **Drifting into guideline voice ("should") inside a policy.** Policies are mandatory. Move advisory content to `99-optional-layers/` or rewrite as "shall".

## Workflow

When asked to add a new document:
1. Identify the layer (policy / standard / procedure / plan / register).
2. Start from the matching template in `_templates/`.
3. Identify the ISO 27002:2022 control(s) and BNM RMiT section(s) it implements.
4. Wire it into the parent document's "Related documents" section.
5. Update the README cascade table if it joins one of the two worked cascades.
