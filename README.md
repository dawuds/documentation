# General Bank — IT Governance Documentation

A worked example of a best-practice IT governance documentation framework for a Malaysian licensed bank, anchored on **ISO/IEC 27001:2022** and **ISO/IEC 27002:2022**, with mapping to **Bank Negara Malaysia's Risk Management in Technology (RMiT)** policy document.

This repo demonstrates *what good looks like* — the structure, the layering, the cascade from principle to operational evidence. It is a teaching artefact, not a certified ISMS.

> **Disclaimer.** This documentation is illustrative. It is not legal, regulatory, or audit advice. Any organisation adopting it must validate every control against its own risk profile, regulatory obligations, and operating environment.

---

## How to use this repo

1. **Start at `00-foundations/`** — it explains the document hierarchy, the maturity tiers, the governance model, and the document lifecycle. Read these first.
2. **Then `01-policies/`** — the policy suite. Two policies are fully drafted as worked examples (Access Control, Incident Management); the rest are first-pass skeletons showing the standard structure.
3. **Then follow the two cascades** — drop from policy → standard → procedure → plan → register to see how a single principle becomes auditable evidence.
4. **Use `_templates/`** when authoring new documents — every document in this repo derives from one of those templates.

---

## The two worked cascades

| Cascade | Policy | Standard | Procedure | Plan | Register | ISO 27002:2022 | BNM RMiT |
|---|---|---|---|---|---|---|---|
| **Access Control** | [02](01-policies/02-access-control-policy.md) | [Password & Auth](02-standards/password-and-authentication-standard.md) | [JML SOP](03-procedures/joiner-mover-leaver-sop.md) | — | [Priv. Access Review](05-registers/privileged-access-review-register.md) | 5.15–5.18, 8.2–8.5 | Appendix 6 |
| **Incident Management** | [08](01-policies/08-incident-management-policy.md) | [Classification & Severity](02-standards/incident-classification-and-severity-standard.md) | [Triage SOP](03-procedures/incident-triage-sop.md) | [IR Plan](04-plans/incident-response-plan.md) | [Incident Register](05-registers/incident-register.md) | 5.24–5.28 | §10.36–10.43 |

---

## Repo map

```
documentation/
├── 00-foundations/        Reference: hierarchy, tiering, governance, lifecycle
├── 01-policies/           Tier 1 — WHAT & WHY (board/exec approved)
├── 02-standards/          Tier 2 — WHAT SPECIFICALLY (CISO approved)
├── 03-procedures/         Tier 3 — HOW (process owner approved)
├── 04-plans/              Time-bound action sets (IRP, BCP, DRP)
├── 05-registers/          Evidence (SoA, risk register, review logs)
├── 06-document-control/   Master register, change log, approvals, archive
├── 99-optional-layers/    When to add Charter / Guideline / Baseline / Manual
└── _templates/            Reusable templates for every document type
```

---

## The maturity-tier recommendation

Most banks should operate at **Maturity 3** — three active tiers (Policy / Standard / Procedure) plus Plans and Registers as evidence. See [`00-foundations/tiering-model.md`](00-foundations/tiering-model.md) for when to expand to Maturity 4.

## Where to find "who approved what, when"

Document control — version history, approvals, supersession, archive — is consolidated in [`06-document-control/`](06-document-control/). Start with the [master document register](06-document-control/master-document-register.md) for current state, the [change log](06-document-control/change-log.md) for history, and the [approval register](06-document-control/approval-register.md) for audit evidence.

---

## References

- **ISO/IEC 27001:2022** — Information security management systems — Requirements.
- **ISO/IEC 27002:2022** — Information security controls (93 controls in 4 themes).
- **Bank Negara Malaysia, *Risk Management in Technology (RMiT)*** — policy document (issued 19 June 2020, applicable to licensed financial institutions).
- **ISO/IEC 27005:2022** — Information security risk management guidance.
- **NIST SP 800-61 Rev. 2** — Computer Security Incident Handling Guide.

Every document in this repo cites the specific clause(s) it implements. Treat every cited clause as a starting point for the authoritative source — read the standard, do not rely on this repo as the authority.
