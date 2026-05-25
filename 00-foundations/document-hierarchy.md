# Document hierarchy — the governance pyramid

The hierarchy of governance documents runs from **stable, abstract, board-level** at the top to **volatile, operational, team-level** at the bottom. Each layer has a distinct purpose, audience, voice, and approval authority. Confusing the layers — typically by mixing policy and procedure — is the single most common failure mode in real ISMS suites.

This page is the **reference model**. Most banks do not operate all nine layers; see [`tiering-model.md`](tiering-model.md) for the maturity-tier guidance and the recommended operating mode.

---

## The nine-layer reference model

| # | Layer | Purpose | Audience | Approver | Change cadence | Voice |
|---|---|---|---|---|---|---|
| 1 | **Charter / Mandate** | Why the function exists, scope, authority | Board | Board | Years | "is established" |
| 2 | **Policy** | *What* and *why* — principles, intent | Everyone | Board / Exec | 1–3 yrs | "shall" |
| 3 | **Standard** | *What specifically* — mandatory, measurable | Implementers, auditors | CISO / function head | Annual | "shall" |
| 4 | **Procedure / SOP** | *How* — step-by-step, role-by-role | Operators | Process owner | As needed | "do this, then this" |
| 5 | **Guideline** | *Recommended approach* — advisory | Implementers | Function head | As needed | "should", "consider" |
| 6 | **Baseline** | Minimum technical configuration | Engineers | Tech lead | As tech evolves | machine-readable |
| 7 | **Plan** | Time-bound action set (IRP, BCP, DRP) | Responders | Function head | Annual + post-event | scenario-driven |
| 8 | **Manual** | Aggregator — bundles SOPs for a function | Function staff | Function head | Continuous | reference |
| 9 | **Register / Record** | Evidence (risk, asset, SoA, training log) | Auditors, regulators | Process owner | Continuous | data |

---

## What each layer looks like in practice

### Charter / Mandate

Establishes a function (e.g., the ISMS, the SOC, the Risk Function). Names the sponsor, scope, decision authority, escalation path, and dissolution conditions. **Stable** — a charter that changes annually is not doing its job.

> *Example:* "The Information Security Management System is established by the Board, sponsored by the CEO, and led by the CISO. Its scope covers all information assets owned, processed, or transmitted by General Bank."

### Policy

States the **principle** and the **why**. Mandatory. Board- or executive-approved. Written so a non-technical reader can understand the intent.

> *Example:* "All access to information systems shall be granted on a least-privilege basis, role-based, and reviewed at least quarterly."

A policy does not say *how*. The moment a policy says "click here", "use Okta", or "the script is at \\\\share\\onboarding\\", it has become a procedure dressed as a policy.

### Standard

Operationalises the policy into **specific, measurable, mandatory** requirements. CISO-approved. Audit-testable.

> *Example:* "Privileged accounts shall require multi-factor authentication using a phishing-resistant factor (FIDO2/WebAuthn or smart card). Passwords for privileged accounts shall be at least 16 characters, machine-generated, and stored in a privileged access management vault."

Standards quantify what policies leave abstract. "Strong password" is policy. "16 characters, machine-generated, stored in PAM vault" is standard.

### Procedure / SOP

The **step-by-step**, role-by-role, tool-by-tool operational sequence. Process owner-approved.

> *Example:* "When HR sets an employee's status to *Terminated* in Workday, the integration job triggers within 15 minutes and: (1) disables the AD account, (2) revokes all Okta sessions, (3) removes the user from all SaaS groups, (4) creates a ticket assigned to the Identity team to recover hardware."

### Guideline

**Advisory** — what to do when there is no single right answer. Not auditable as compliance; useful for consistency and onboarding.

> *Example:* "When designing a quarterly privileged access review, consider grouping reviewers by application owner rather than by access type, to reduce reviewer fatigue and improve recertification quality."

If a guideline starts using "shall", it is no longer a guideline — promote it to a standard or rewrite it.

### Baseline

**Minimum technical configuration** — typically a hardening configuration for a class of system (server OS, database, container, network device). Often expressed as a CIS Benchmark profile, an SCAP/STIG content reference, or a configuration-as-code manifest.

> *Example:* "All Linux servers shall meet CIS Ubuntu 22.04 LTS Benchmark Level 1 (Server profile), assessed via Ansible-based scanning weekly."

### Plan

A **time-bound action set** for a defined scenario. Lives between standard and procedure: it has structure (phases, decision gates, RACI) but is scenario-driven, not steady-state.

The big three: **Incident Response Plan**, **Business Continuity Plan**, **Disaster Recovery Plan**. Each has its own activation trigger and authority.

### Manual

An **aggregator** — bundles related SOPs into a single navigable document for a function (e.g., a Security Operations Manual, a Change Management Manual). Useful for handover, training, and inspection. Not a governance layer in its own right — do not put policy-grade statements inside a manual.

### Register / Record

The **evidence layer**. Risk register, asset register, Statement of Applicability, exception register, training log, incident register, access review register. These are *outputs* of the procedures, and they are what auditors and regulators actually inspect.

If you cannot point to a register that proves a control is operating, the control is theoretical.

---

## The three confusions worth killing on day one

### 1. Policy ≠ Procedure

| | Policy | Procedure |
|---|---|---|
| Says | *What* and *why* | *How*, step-by-step |
| Approver | Board / Exec | Process owner |
| Voice | "shall" | "do this, then this" |
| Stability | Years | Changes with toolchain |
| Reader | Everyone | The operator |

Mixing them means: (a) the policy becomes obsolete every time a tool changes, forcing board re-approval for trivial reasons, and (b) operators read a document full of "shall" statements but cannot find the instructions, so they invent their own.

### 2. Standard ≠ Guideline

If it uses **shall / must**, it is a standard — mandatory, auditable.
If it uses **should / recommended / consider**, it is a guideline — advisory.

If a single document mixes both, every reader will guess differently about which clauses are enforceable. Split.

### 3. Manual is an aggregator, not a layer

A "Security Operations Manual" that bundles 30 SOPs is useful. A "Security Operations Manual" that contains policy statements, standards, SOPs, and guidelines all in one document is unreadable, unmaintainable, and will not survive an audit. If you need a manual, build it as a *navigation layer over the SOPs*, not a replacement for the underlying documents.

---

## The cascade — how one principle flows down

A single principle should be traceable from policy to evidence. Worked example (Access Control):

```
Policy:    "Access shall be least-privilege, role-based, reviewed quarterly."
   ↓
Standard:  "Privileged accounts shall use FIDO2 MFA; passwords ≥ 16 chars in PAM vault;
            quarterly reviews shall cover 100% of privileged accounts."
   ↓
Procedure: "Joiner/Mover/Leaver SOP: HR trigger → AD/Okta provisioning → role assignment →
            ticket to manager for verification."
   ↓
Guideline: "Group quarterly review by application owner to reduce reviewer fatigue."
   ↓
Register:  "Privileged Access Review Register — Q1 2026: 412 accounts reviewed,
            7 removals, 0 escalations."
```

That single chain is what an auditor follows. The chain is also how *you* know your policy suite is real: if any link is missing or broken, the principle is not actually enforced.

See the two fully drafted cascades in this repo:
- [Access Control cascade](../README.md#the-two-worked-cascades)
- [Incident Management cascade](../README.md#the-two-worked-cascades)
