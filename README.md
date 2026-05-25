# General Bank — IT Governance Documentation

A worked example of a best-practice IT governance documentation framework for a Malaysian licensed bank, anchored on **ISO/IEC 27001:2022** and **ISO/IEC 27002:2022**, with mapping to **Bank Negara Malaysia's Risk Management in Technology (RMiT)** policy document.

This repo demonstrates *what good looks like* — the structure, the layering, the cascade from principle to operational evidence. It is a teaching artefact, not a certified ISMS.

> **Disclaimer.** This documentation is illustrative. It is not legal, regulatory, or audit advice. Any organisation adopting it must validate every control against its own risk profile, regulatory obligations, and operating environment.

---

## How to use this repo

Every folder has a `README.md` that orients you to its contents. Start at [`00-foundations/`](00-foundations/), then pick a learning path below.

1. **Start at [`00-foundations/`](00-foundations/)** — document hierarchy, maturity tiers, governance model, document lifecycle, and the regulatory mapping reference (the canonical citation source).
2. **Then [`01-policies/`](01-policies/)** — the policy suite. Two policies fully drafted (Access Control, Incident Management); 12 supporting policies as first-pass skeletons.
3. **Follow the two cascades** — drop from policy → standard → procedure → plan → register to see how a single principle becomes auditable evidence.
4. **Use [`_templates/`](_templates/)** when authoring new documents.

## Learning paths

Pick the path matching your reason for reading. Each path lists the documents in suggested order, with rough time-to-read.

### Path A — "I'm new to ISMS and want to understand the structure" (~60 min)

1. [`00-foundations/README.md`](00-foundations/README.md) — orientation (2 min)
2. [`00-foundations/document-hierarchy.md`](00-foundations/document-hierarchy.md) — the 9-layer pyramid (10 min)
3. [`00-foundations/tiering-model.md`](00-foundations/tiering-model.md) — M1→M4, why M3 is the target (8 min)
4. [`00-foundations/governance-model.md`](00-foundations/governance-model.md) — three-line model, approval authority (10 min)
5. [`00-foundations/document-lifecycle.md`](00-foundations/document-lifecycle.md) — states and gates (8 min)
6. [`01-policies/00-information-security-policy.md`](01-policies/00-information-security-policy.md) — see the structure in action (15 min)
7. [`05-registers/statement-of-applicability.md`](05-registers/statement-of-applicability.md) — see how ISO 27002 controls map (skim, 7 min)

### Path B — "I'm an auditor / inspector preparing to review this ISMS" (~50 min)

1. [`06-document-control/README.md`](06-document-control/README.md) — how this ISMS proves what it operates (5 min)
2. [`06-document-control/master-document-register.md`](06-document-control/master-document-register.md) — current state, all documents (10 min)
3. [`06-document-control/approval-register.md`](06-document-control/approval-register.md) — evidence of board/RMC/CISO approvals (5 min)
4. [`05-registers/statement-of-applicability.md`](05-registers/statement-of-applicability.md) — all 93 Annex A controls mapped (15 min)
5. [`01-policies/00-information-security-policy.md`](01-policies/00-information-security-policy.md) — the master (15 min)
6. Spot-check any individual policy/standard/SOP from the cascades.

### Path C — "I'm a CISO setting up my own org's ISMS, using this as a template" (~90 min, plus adaptation)

1. [`00-foundations/`](00-foundations/) — all five documents (45 min)
2. [`01-policies/00-information-security-policy.md`](01-policies/00-information-security-policy.md) — adapt to your governance (15 min)
3. **The Access Control cascade** end-to-end — POL-02 → STD-02-01 → SOP-02-01 → REG-PAR (15 min) — this is the cascade pattern your other policies should follow
4. [`_templates/`](_templates/) — the skeletons for authoring your own (5 min)
5. [`06-document-control/`](06-document-control/) — set up your version-control discipline from day one (10 min)

### Path D — "I'm learning Malaysian FS / BNM RMiT compliance via ISO 27001" (~75 min)

1. [`00-foundations/regulatory-mapping-reference.md`](00-foundations/regulatory-mapping-reference.md) — the canonical mapping (15 min)
2. [`01-policies/08-incident-management-policy.md`](01-policies/08-incident-management-policy.md) — Cyber Resilience Framework anchored on RMiT §11 (15 min)
3. [`02-standards/incident-classification-and-severity-standard.md`](02-standards/incident-classification-and-severity-standard.md) — including the 4-hour BNM notification citation chain (10 min)
4. [`04-plans/incident-response-plan.md`](04-plans/incident-response-plan.md) — IRP implementing RMiT §11.13 with §11.12 crisis management overlay (15 min)
5. [`05-registers/statement-of-applicability.md`](05-registers/statement-of-applicability.md) — ISO 27002 / RMiT cross-mapping per control (20 min)

### Path E — "I'm building the cascade pattern for a different control domain" (~30 min)

1. [`00-foundations/document-hierarchy.md`](00-foundations/document-hierarchy.md) §"The cascade" (5 min)
2. **Access Control cascade** in full:
   - [POL-02](01-policies/02-access-control-policy.md) (10 min)
   - [STD-02-01](02-standards/password-and-authentication-standard.md) (5 min)
   - [SOP-02-01](03-procedures/joiner-mover-leaver-sop.md) (5 min)
   - [REG-PAR](05-registers/privileged-access-review-register.md) (3 min)
3. Build your own cascade using the same shape — one policy, one or more standards, one or more SOPs, one register.

---

## The two worked cascades

| Cascade | Policy | Standard | Procedure | Plan | Register | ISO 27002:2022 | BNM RMiT (28 Nov 2025) |
|---|---|---|---|---|---|---|---|
| **Access Control** | [02](01-policies/02-access-control-policy.md) | [Password & Auth](02-standards/password-and-authentication-standard.md) | [JML SOP](03-procedures/joiner-mover-leaver-sop.md) | — | [Priv. Access Review](05-registers/privileged-access-review-register.md) | 5.15–5.18, 8.2–8.5 | §10.53–10.57 |
| **Incident Management** | [08](01-policies/08-incident-management-policy.md) | [Classification & Severity](02-standards/incident-classification-and-severity-standard.md) | [Triage SOP](03-procedures/incident-triage-sop.md) | [IR Plan](04-plans/incident-response-plan.md) | [Incident Register](05-registers/incident-register.md) | 5.24–5.28 | §11.12–11.20 (CRF §11.2–11.3) |

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
- **Bank Negara Malaysia, *Risk Management in Technology (RMiT)*** — policy document **issued 28 November 2025** (BNM/RH/PD 028-100); applicable to licensed financial institutions. Supersedes the June 2020 issuance.
- **Cyber Security Act 2024 (Malaysia)** — National Critical Information Infrastructure (NCII) designation regime; NACSA directives.
- **ISO/IEC 27005:2022** — Information security risk management guidance.
- **NIST SP 800-61 Rev. 2** — Computer Security Incident Handling Guide.

See [`00-foundations/regulatory-mapping-reference.md`](00-foundations/regulatory-mapping-reference.md) for the canonical mapping used by every document in this repo when citing BNM RMiT, ISO, and adjacent Malaysian regulation.

Every document in this repo cites the specific clause(s) it implements. Treat every cited clause as a starting point for the authoritative source — read the standard, do not rely on this repo as the authority.
