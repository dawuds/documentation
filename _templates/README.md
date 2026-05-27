# _templates

Skeletons for v2 documents. One template per layer.

← [Repo home](../README.md) · [Architecture](../00-architecture/) ↑

---

## Templates

| Template | Layer | When to use |
|---|---|---|
| [framework-template.md](framework-template.md) | Layer 2 | New bank-authored framework document (TRMF, CRMF, etc.) — 17-section anatomy |
| [policy-template.md](policy-template.md) | Layer 3 | New policy document — 10-section anatomy |
| [standard-template.md](standard-template.md) | Layer 4 | New standard — 7-section anatomy |
| [procedure-template.md](procedure-template.md) | Layer 5 | New procedure / SOP — 9-section anatomy with actor/action/tool/output/SLA per step |
| [plan-template.md](plan-template.md) | Plans | New plan (IRP, BCP, DRP) — 9-section anatomy |
| [register-template.md](register-template.md) | Layer 6 | New register — 5-section anatomy with schema and worked example |

---

## Authoring workflow

1. Identify the layer.
2. Start from the matching template.
3. Identify the regulatory anchor (RMiT clause + COBIT objective + practice standard) using [`../_context/framework-stack.md`](../_context/framework-stack.md).
4. Wire the new document into:
   - The parent framework's "Implementation requirements" section (Section 9 of any Layer 2 framework)
   - `../07-document-control/master-document-register.md` once that suite is in place
5. Voice and discipline per [`../_context/role.md`](../_context/role.md).
