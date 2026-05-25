# When to add standalone Guidelines

A Guideline is an **advisory** document — what to do when there is no single right answer. Voice: "should", "recommended", "consider". Not auditable as compliance; useful for consistency and onboarding.

General Bank in this worked example does **not** maintain standalone Guidelines as a folder. Instead, advisory content sits in the introductory sections of relevant standards or SOPs (e.g., "considerations for grouping quarterly access reviews by application owner" might appear as a note in the JML SOP rather than as a separate guideline document). This is appropriate for a Maturity-3 bank.

---

## When standalone Guidelines earn their keep

Add Guidelines as a first-class layer when **at least one** of the following is true:

| Trigger | Why Guidelines help |
|---|---|
| Multiple teams implement the same standard inconsistently, and the variation is causing pain | E.g., 12 engineering teams each interpret "secure code review" differently. A Secure Code Review Guideline gives them a shared starting point without forcing premature standardisation. |
| There is **no single right answer** — only well- and badly-thought-through choices | E.g., guidance for picking between two valid cryptographic algorithms in a specific context. Mandating one would be wrong; leaving teams without guidance produces poor choices. |
| Onboarding new staff into a discipline is slow because tacit knowledge dominates | E.g., a Threat Modelling Guideline for engineering teams captures the tacit knowledge that would otherwise be passed only by shoulder-surfing senior security engineers. |
| You want to capture "how we think about X" without making it mandatory | E.g., a guideline on naming privileged roles in the IDP. Useful, not enforceable as a control. |

## When Guidelines do **not** earn their keep

- When you are tempted to write "should" where you actually mean "shall" — promote to standard.
- When the variation isn't causing real pain — Guidelines that solve no problem are read by nobody and rot.
- When the underlying standard or SOP can hold the advisory content as a note (the General Bank approach).
- When you have not yet got your standards layer in shape — Guidelines built on weak standards just confuse the picture.

## Common failure modes

1. **Guideline → de facto standard drift.** Teams treat the guideline as mandatory. Auditors find inconsistency, ask "is this enforced?", and the Guideline gets rewritten as a Standard — but only after a control deficiency finding.
2. **Standard → de facto guideline drift.** A standard is so widely exception'd that it becomes advisory. Either fix the standard (relax the thresholds) or fix the exceptions (enforce). Don't let it drift into a quasi-guideline.
3. **Guideline graveyard.** Add five guidelines, none of them maintained. Standard sign of premature M4 ambition without M3 foundations.

## If you add one

Recommended structure:

1. **Purpose** — what advice this gives, and to whom.
2. **Scope** — situations the advice applies to.
3. **Principles** — the *why* behind the recommendations (so readers can extrapolate to cases the guideline doesn't cover).
4. **Recommendations** — "should" statements, with rationale for each.
5. **Alternatives** — where the guideline acknowledges multiple valid approaches, name them and the trade-offs.
6. **Examples** — concrete, sanitised illustrations.
7. **Related documents** — link to mandatory standards/SOPs that the guideline supplements.

Voice rule: if any single "should" in the document is something readers will be **disciplined for not doing**, it is not a guideline — it is a standard.
