# _templates

Skeletons for authoring new documents. One template per document type.

← [Back to repo home](../README.md) · [Foundations](../00-foundations/) ↑

---

## Why templates matter

Every document in this repo derives from one of these templates. The reason is single-template economy: a reader learns one structure, not fifteen.

When authoring a new document:

1. Identify the **layer** (policy / standard / procedure / plan / register).
2. Start from the matching template.
3. Identify the ISO/IEC 27002:2022 controls and BNM RMiT clauses (use [`../00-foundations/regulatory-mapping-reference.md`](../00-foundations/regulatory-mapping-reference.md)) it implements.
4. Wire it into the parent document's "Related documents" section.
5. Register it in [`../06-document-control/master-document-register.md`](../06-document-control/master-document-register.md).
6. Append a row to [`../06-document-control/change-log.md`](../06-document-control/change-log.md).
7. Append a row to [`../06-document-control/approval-register.md`](../06-document-control/approval-register.md) once approved.

---

## Templates

| Template | Use when authoring… | Approval authority | Sections |
|---|---|---|---|
| [policy-template.md](policy-template.md) | A Tier 1 policy (principle, mandatory, board/exec approved) | Board (POL-00); RMC (POL-01–14) | 10 |
| [standard-template.md](standard-template.md) | A Tier 2 standard (quantified, mandatory, CISO approved) | CISO | 7 |
| [procedure-template.md](procedure-template.md) | A Tier 3 SOP (operational, process-owner approved) | Process owner | 9 |
| [plan-template.md](plan-template.md) | A scenario-driven plan (IRP, BCP, DRP) | RMC | 9 |
| [register-template.md](register-template.md) | An evidence register (continuous, operational) | Process owner | 5 |

---

## Rules

- **Do not edit a template to change the structure for a single document.** If you find yourself wanting to deviate, the template is wrong — propose a template change first.
- **Do not invent a new template** without explicit reason. The fewer templates, the more navigable the suite.
- **The document control table** at the foot of every document is mandatory. The register entries in `06-document-control/` are the cross-document register; the in-document table is the per-document record.

---

## Cross-links

- ↑ [Foundations](../00-foundations/) — the document model these templates implement
- → [Document control](../06-document-control/) — where every new document gets registered
