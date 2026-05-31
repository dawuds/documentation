# RMiT Gap Analysis Register

| | |
|---|---|
| **Document ID** | REG-GAP |
| **Layer** | Register |
| **Owner** | CRO + CCO (joint); 2nd-line Technology Risk team operates |
| **Cadence** | Initial baseline on regulatory issuance; refresh annually; immediate on RMiT amendment, BNM PD change, NACSA directive, or material change to GIBB scope |
| **Implements** | BNM RMiT (28 Nov 2025) Section 18 (Assessment and Gap Analysis); ISO/IEC 27001:2022 Clause 9.1 (Monitoring, measurement, analysis and evaluation); aligned with the 1st-line / 2nd-line / 3rd-line model |
| **Source procedure** | CRMF Section 11; TRMF Section 11; [POL-22 IT Compliance Policy](../02-policies/POL-22-it-compliance-policy.md) Section 3 |
| **Parent framework(s)** | [TRMF](../01-frameworks/TRMF.md); [CRMF](../01-frameworks/CRMF.md) |
| **COBIT objective(s)** | MEA03 Managed Compliance with External Requirements; MEA04 Managed Assurance |

---

## Purpose

The **mandatory record** of GIBB's gap analysis against BNM RMiT (28 November 2025 issuance), as required by **RMiT Section 18 (Assessment and Gap Analysis)**. Every RMiT clause that imposes a requirement on the bank is assessed at one of three states — **Compliant**, **Partial**, or **Non-compliant** — with evidence of compliance, owner, and remediation plan where applicable.

This register is the **first artefact a BNM examiner will ask for** at any RMiT-themed examination. It is also the structured-data source for the GRC platform per [`_learning/grc-platform-format.md`](../_learning/grc-platform-format.md).

The same approach is used for NACSA Code of Practice (a separate sheet within this register) and other applicable supervisory frameworks.

## Schema

| Field | Type | Description |
|---|---|---|
| `gap_id` | string | `GAP-RMiT-{SECTION}.{SUB}-{NN}` |
| `regulation` | enum | `RMiT 28 Nov 2025` / `NACSA CoP` / `MCIPD` / `PDPA` / `BNM Outsourcing PD` / `BNM BCM PD` / `Other` |
| `clause` | string | Exact clause/section/paragraph reference |
| `clause_text_summary` | text | One-line summary of the requirement |
| `applicability` | enum | `Applicable` / `Not applicable (with basis)` / `Conditionally applicable` |
| `state` | enum | `Compliant` / `Partial` / `Non-compliant` / `Pending implementation` |
| `evidence_documents` | array | Links to policies, standards, SOPs, registers that evidence compliance |
| `evidence_operational` | text | What is the operating evidence (e.g., "see REG-PAR FY2026 quarterly entries") |
| `gap_description` | text | If Partial / Non-compliant: what is missing |
| `risk_rating` | enum | `Critical` / `High` / `Medium` / `Low` |
| `remediation_plan` | text | What will close the gap |
| `remediation_owner` | role | Accountable role |
| `target_completion_date` | date | |
| `linked_corrective_action` | reference | [REG-CAP](REG-CAP-corrective-action-register.md) ID |
| `linked_risk` | reference | [REG-TR](REG-TR-technology-risk-register.md) ID where the gap is accepted as residual risk |
| `last_reviewed` | date | |
| `next_review` | date | |
| `notes` | text | Examiner-readable commentary |

## Worked example — first entries (illustrative)

| gap_id | clause | summary | state | evidence | gap | owner | target | risk |
|---|---|---|---|---|---|---|---|---|
| GAP-RMiT-8.2-01 | RMiT Section 8.2 (Board responsibilities — technology risk oversight) | Board approves the technology risk strategy and reviews its effectiveness at least annually | Compliant | [POL-01](../02-policies/POL-01-it-governance-policy.md); [TRMF](../01-frameworks/TRMF.md) Section 11; [REG-MR](REG-MR-management-review-register.md) MR-2026-01 minutes | n/a | CRO | n/a | n/a |
| GAP-RMiT-9.2-01 | RMiT Section 9.2 (TRMF mandatory elements (a)–(k)) | TRMF must address 11 mandatory elements | Compliant | [TRMF](../01-frameworks/TRMF.md) Section 6 (renumbered 1:1 with 9.2(a)–(k)) | n/a | CRO | n/a | n/a |
| GAP-RMiT-10.11-01 | RMiT Section 10.11 (Independent review of changes) | Material changes subject to independent review | Compliant | [STD-CM-01](../03-standards/STD-CM-01-change-management-standard.md); [REG-CHG](REG-CHG-change-register.md) `independent_reviewer` field mandatory | n/a | CIO | n/a | n/a |
| GAP-RMiT-10.17-01 | RMiT Section 10.17 (Vulnerability and EOL management) | Patch and EOL framework with risk-based remediation timelines | Compliant | [POL-18](../02-policies/POL-18-vulnerability-management-policy.md) Section 3.3; [STD-CR-03](../03-standards/STD-CR-03-vulnerability-triage-standard.md); [REG-VUL](REG-VUL-vulnerability-register.md) | n/a | CISO | n/a | n/a |
| GAP-RMiT-11.3-01 | RMiT Section 11.3 ((a)–(i) CRF mandatory elements) | CRF must address 9 mandatory elements | Compliant | [CRMF](../01-frameworks/CRMF.md) Section 6 (renumbered 1:1 with 11.3(a)–(i)) | n/a | CISO | n/a | n/a |
| GAP-RMiT-11.6-01 | RMiT Section 11.6 (Red team simulation attacks) | Cadence per RMiT requirement | Partial | [POL-18](../02-policies/POL-18-vulnerability-management-policy.md) Section 3.6.2; [STD-CR-03](../03-standards/STD-CR-03-vulnerability-triage-standard.md) | Last red team Oct 2025; next cycle scoped but not yet contracted | Gap CAP-2026-0019 | CISO | 2026-09-30 | Medium |
| GAP-RMiT-11.13-01 | RMiT Section 11.13 (Cyber Incident Response Plan) | Maintained and reviewed at least annually and after every material incident | Compliant | [PLN-01](../05-plans/PLN-01-incident-response-plan.md); [POL-13](../02-policies/POL-13-incident-management-policy.md) Section 4.3 | n/a | CISO | n/a | n/a |
| GAP-RMiT-11.16-01 | RMiT Section 11.16 (Annual Cyber Drill Exercise) | Annual cyber drill mandatory | Partial | [PLN-05](../05-plans/PLN-05-cyber-drill-exercise-plan.md); [SOP-CR-01](../04-procedures/SOP-CR-01-cyber-drill-exercise-sop.md); [REG-DRL](REG-DRL-cyber-drill-register.md) | Drill scheduled 2026-09-15; not yet executed in FY2026 | CAP-2026-0030 | CISO + CEO | 2026-09-15 | Medium |
| GAP-RMiT-11.18-01 | RMiT Section 11.18 (Cyber Incident Notification to BNM) | Notification clock per upstream BNM policy chain | Compliant — with source-chain caveat | [POL-13](../02-policies/POL-13-incident-management-policy.md) Section 4.4.3; [STD-IR-01](../03-standards/STD-IR-01-incident-classification-and-severity-standard.md) Section 3.5.1; [PLN-01](../05-plans/PLN-01-incident-response-plan.md) Section 6 | 4-hour operating expectation documented with source-chain caveat; CCO maintains authoritative clock | CCO | Continuous | Low |
| GAP-RMiT-15-01 | RMiT Section 15 (Security Awareness and Education) | Bank-wide awareness programme | Partial | [POL-HR-01](../02-policies/POL-HR-01-hr-security-policy.md) Section 3.3 | Awareness Programme document (PLN-07) drafted FY2026; first full operating cycle pending | CHRO + CISO | 2026-12-31 | Medium |
| GAP-RMiT-18-01 | RMiT Section 18 (Assessment and Gap Analysis) | Document gap analysis against RMiT | Compliant | This register (REG-GAP); refreshed annually | CRO + CCO | Continuous | n/a |

### Summary roll-up (illustrative, FY2026 Q2)

| State | Count |
|---|---|
| Compliant | 87 |
| Partial | 12 |
| Non-compliant | 0 |
| Pending implementation | 4 |
| **Total RMiT clauses tracked** | **103** |

Of the 12 Partial states: 5 medium-risk (in active remediation), 7 low-risk (no remediation required — documented compensating controls). Of the 4 Pending implementation: 3 are CRF mandatory elements with phased operationalisation through FY2026; 1 is the FY2026 cyber drill (scheduled Q3).

## Maintenance

- Baseline gap analysis is **executed by 2nd-line Technology Risk** team based on the most recent RMiT issuance text in `/Users/dawud/claude/RMIT/` (reference repo).
- 1st-line (Information Security, IT Operations, etc.) provides evidence; 2nd-line assesses; 3rd-line (Internal Audit) independently validates a sample.
- **Material RMiT amendments** (issuance changes, supplementary guidance) trigger an immediate refresh — not a wait for the annual cycle.
- Each `Partial` or `Non-compliant` row must have a `remediation_plan` and a `linked_corrective_action`. A row with `Partial` and no plan is itself a control deficiency.
- Annual summary feeds the Board through RMC at the annual Management Review per [REG-MR](REG-MR-management-review-register.md).

## Related documents

- **Source-of-truth regulation:** `/Users/dawud/claude/RMIT/` (reference repo, 28 Nov 2025 issuance)
- **Parent policy:** [POL-22 IT Compliance Policy](../02-policies/POL-22-it-compliance-policy.md)
- **Feeds-to:** [REG-MR](REG-MR-management-review-register.md); [REG-CAP](REG-CAP-corrective-action-register.md); [REG-TR](REG-TR-technology-risk-register.md); Board / RMC reporting
- **Cross-references:** [REG-SOA](REG-SOA-statement-of-applicability.md) (ISO 27002 control map — parallel artefact for ISO certification); [REG-NCA](REG-NCA-ncii-audit-findings-register.md) (NACSA-specific findings)

## Document control

| Version | Date | Author | Reviewer | Approver | Change summary |
|---|---|---|---|---|---|
| 1.0 | 2026-05-30 | 2nd-line Technology Risk | CRO + CCO | Risk Management Committee | Initial version. Closes RMiT Section 18 (Assessment and Gap Analysis) evidence gap identified in v2 multi-agent review (GRC: "Required by RMiT Section 18 — no document exists"). |
