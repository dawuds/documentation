# _context

Working folder for context decisions. Captures the CRIO (Context / Role / Interview / Outcome) work that scopes and shapes v2.

**Not part of the deliverable.** This folder is for the design team (assistant + user). Refined continuously as we learn.

← [Repo home](../README.md) · [v1 snapshot](../v1/)

---

## Files

| File | Purpose |
|---|---|
| [decisions.md](decisions.md) | ADR log — every context decision with date, rationale, alternatives, status |
| [bank-profile.md](bank-profile.md) | GIBB persona — bank type, tier, NCII status, business lines, governance |
| [framework-stack.md](framework-stack.md) | Layer 0–2 model: regulatory anchors, reference frameworks, bank-authored frameworks |
| [seams.md](seams.md) | The three framework seams (DGF/CIMF, TPRMF/CloudRMF, TRMF/CRMF) and how each is resolved |
| [glossary.md](glossary.md) | Acronyms, framework names, BNM PDs referenced |
| [open-questions.md](open-questions.md) | Decisions not yet locked; revisit list |

---

## Workflow

1. **New decision proposed** — discussed in conversation, captured in [decisions.md](decisions.md) as a new ADR.
2. **Decision superseded** — old ADR marked `Superseded by DEC-NNN`; new ADR added; affected reference files (framework-stack, seams, etc.) updated.
3. **Open question resolved** — moved from [open-questions.md](open-questions.md) into a numbered ADR.
4. **All decisions reflected** — `framework-stack.md` and `seams.md` are derivative views over `decisions.md`. When a decision changes, update both.

A decision in this folder binds the v2 deliverable. Do not deviate without revisiting the ADR.
