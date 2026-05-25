# Tiering model — which tiers a real bank should actually run

The nine-layer pyramid in [`document-hierarchy.md`](document-hierarchy.md) is the **reference ceiling**. Almost no organisation operates all nine layers, and trying to before the foundations are in place produces documents that nobody reads and auditors do not ask for.

This page maps maturity to active tiers and gives the recommended operating mode for a Malaysian licensed bank.

---

## Maturity-to-tiering map

| Maturity | Tiers in active use | Typical organisation | What it looks like |
|---|---|---|---|
| **M1 — minimal** | 1 tier | Startup, small business | A single "IT Policy" PDF that mixes principle, procedure, and tool references. Useful for one inspector visit; collapses under any real audit. |
| **M2 — emerging** | 2 tiers: Policy + Procedure | Mid-market, pre-certification | Recognisable policy suite, with SOPs for major operations (onboarding, backup, patching). Standard layer is implicit — embedded in policy. Works until an auditor asks "where is the password length defined?" and the policy says "strong passwords". |
| **M3 — ISO-aligned ★** | **3 tiers: Policy / Standard / Procedure** + Plans + Registers as evidence | Most ISO 27001 certified organisations, including most Malaysian licensed banks | The sweet spot. Standards layer makes policies testable. Plans cover IR/BC/DR. Registers (SoA, risk, exceptions, training) provide audit evidence. |
| **M4 — regulated enterprise** | Full pyramid: Charter → Policy → Standard → Procedure → Guideline → Baseline → Plan → Manual → Register | Tier-1 banks, telcos, regulated utilities, large financial groups | Adds Charter (board-level governance documents), Guidelines (advisory for consistency at scale), Baselines (machine-readable hardening), and Manuals (aggregated handover documents per function). |

★ = recommended for General Bank and similar.

---

## Why M3 is the right target for most banks

**M3 is the lowest maturity at which an ISMS is sustainably audit-defensible.**

- ISO/IEC 27001:2022 requires documented information for the management system (Clauses 4–10) and a Statement of Applicability for Annex A controls (Clause 6.1.3 d). At M2 you can produce this paperwork; at M3 you can defend it under audit because every policy statement is operationalised in a standard and every standard is implemented in a procedure, with registers as evidence.
- BNM RMiT (28 Nov 2025) is structured the same way — it issues principle-level requirements (e.g., §11.13 on the Cyber Incident Response Plan; §10.54 on access control principles) and supporting detail (e.g., the nine mandatory CRF elements at §11.3, the cybersecurity control measures at §11.5 implementing Appendix 5). M3 lets you trace each RMiT requirement into your own documents in a way an inspector can follow. See [`regulatory-mapping-reference.md`](regulatory-mapping-reference.md) for the canonical mapping.
- Adding M4 layers before M3 is fully in place is a classic over-engineering trap. Guidelines without working standards do not get used. Baselines without working procedures do not get applied. Charters without working policies are decorative.

---

## When to expand from M3 to M4

Add each M4 layer **only** when there is a concrete reason — a regulatory ask, a scale problem the existing layers do not solve, or an audit finding that points to a missing layer.

| Add this layer | When |
|---|---|
| **Charter** | When the function has board-level visibility and the board asks for explicit terms of reference (typical at IPO, post-merger, or after a regulatory escalation). |
| **Guideline** | When you have multiple teams implementing the same standard inconsistently, and the variation is causing operational pain (e.g., 12 teams each interpreting "secure code review" differently). |
| **Baseline** | When you can express minimum technical configuration as code (Ansible, Terraform, SCAP, CIS-CAT) and you have the engineering capacity to maintain and assess it. |
| **Manual** | When a function's SOPs have grown past ~15–20 documents and operators cannot find what they need quickly — bundle them under a navigable manual. |

See [`../99-optional-layers/`](../99-optional-layers/) for the long-form guidance on each.

---

## Anti-patterns to avoid

1. **Jumping straight to M4.** Most consulting deliverables that promise "a full governance suite" are M4 templates dropped onto an M1 organisation. They generate paperwork, not control.
2. **Calling everything a policy.** If you have 60 "policies", you are at M1 or M2 with marketing. Real policies are stable principle-level documents — there should be 10–20, not 60.
3. **Skipping the Standard layer.** Going from policy directly to SOP forces SOPs to define their own thresholds, which means every SOP author makes their own security decisions. Standards prevent this.
4. **No registers.** If your auditor cannot point to a register that proves a control is operating, the control is theoretical, no matter how good the policy reads.

---

## What General Bank operates (in this repo)

General Bank operates at **M3** with two M4 elements introduced where they earn their keep:

- **Active tiers:** Policy, Standard, Procedure, Plan, Register. ✅
- **Optional layers used selectively:** Baselines (for the technology operations stack), Manuals (Security Operations Manual aggregating SOC procedures). The Charter is held at the master Information Security Policy level rather than as a separate document.
- **Optional layers not used:** Stand-alone Guidelines — instead, advisory content is captured in the introductory sections of the relevant standard or SOP.

This is a deliberate choice. Fewer layers, well-maintained, beats more layers, half-maintained.
