# Reading paths

Five suggested reading orders, by audience. Pick the path that matches your reason for reading this repo.

← [Back to _learning](README.md) · [Repo home](../README.md)

---

## Path A — "I'm new to ISMS and want to understand the structure" (~60 min)

1. [`00-foundations/README.md`](../00-foundations/README.md) — orientation (2 min)
2. [`00-foundations/document-hierarchy.md`](../00-foundations/document-hierarchy.md) — the 9-layer pyramid (10 min)
3. [`00-foundations/tiering-model.md`](../00-foundations/tiering-model.md) — M1→M4, why M3 is the target (8 min)
4. [`00-foundations/governance-model.md`](../00-foundations/governance-model.md) — three-line model, approval authority (10 min)
5. [`00-foundations/document-lifecycle.md`](../00-foundations/document-lifecycle.md) — states and gates (8 min)
6. [`01-policies/00-information-security-policy.md`](../01-policies/00-information-security-policy.md) — see the structure in action (15 min)
7. [`05-registers/statement-of-applicability.md`](../05-registers/statement-of-applicability.md) — see how ISO 27002 controls map (skim, 7 min)

## Path B — "I'm an auditor / inspector preparing to review this ISMS" (~50 min)

1. [`06-document-control/README.md`](../06-document-control/README.md) — how this ISMS proves what it operates (5 min)
2. [`06-document-control/master-document-register.md`](../06-document-control/master-document-register.md) — current state, all documents (10 min)
3. [`06-document-control/approval-register.md`](../06-document-control/approval-register.md) — evidence of board / RMC / CISO approvals (5 min)
4. [`05-registers/statement-of-applicability.md`](../05-registers/statement-of-applicability.md) — all 93 Annex A controls mapped (15 min)
5. [`01-policies/00-information-security-policy.md`](../01-policies/00-information-security-policy.md) — the master (15 min)
6. Spot-check any individual policy / standard / SOP from the two cascades.

## Path C — "I'm a CISO setting up my own org's ISMS, using this as a template" (~90 min, plus adaptation)

1. [`00-foundations/`](../00-foundations/) — all five documents (45 min)
2. [`01-policies/00-information-security-policy.md`](../01-policies/00-information-security-policy.md) — adapt to your governance (15 min)
3. **The Access Control cascade** end-to-end — POL-02 → STD-02-01 → SOP-02-01 → REG-PAR (15 min) — this is the cascade pattern your other policies should follow
4. [`_templates/`](../_templates/) — the skeletons for authoring your own (5 min)
5. [`06-document-control/`](../06-document-control/) — set up your version-control discipline from day one (10 min)

## Path D — "I'm learning Malaysian FS / BNM RMiT compliance via ISO 27001" (~75 min)

1. [`00-foundations/regulatory-mapping-reference.md`](../00-foundations/regulatory-mapping-reference.md) — the canonical mapping (15 min)
2. [`01-policies/08-incident-management-policy.md`](../01-policies/08-incident-management-policy.md) — Cyber Resilience Framework anchored on RMiT §11 (15 min)
3. [`02-standards/incident-classification-and-severity-standard.md`](../02-standards/incident-classification-and-severity-standard.md) — including the 4-hour BNM notification citation chain (10 min)
4. [`04-plans/incident-response-plan.md`](../04-plans/incident-response-plan.md) — IRP implementing RMiT §11.13 with §11.12 crisis management overlay (15 min)
5. [`05-registers/statement-of-applicability.md`](../05-registers/statement-of-applicability.md) — ISO 27002 / RMiT cross-mapping per control (20 min)

## Path E — "I'm building the cascade pattern for a different control domain" (~30 min)

1. [`00-foundations/document-hierarchy.md`](../00-foundations/document-hierarchy.md) §"The cascade" (5 min)
2. **Access Control cascade** in full:
   - [POL-02](../01-policies/02-access-control-policy.md) (10 min)
   - [STD-02-01](../02-standards/password-and-authentication-standard.md) (5 min)
   - [SOP-02-01](../03-procedures/joiner-mover-leaver-sop.md) (5 min)
   - [REG-PAR](../05-registers/privileged-access-review-register.md) (3 min)
3. Build your own cascade using the same shape — one policy, one or more standards, one or more SOPs, one register.
