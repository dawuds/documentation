# Risk Register

| | |
|---|---|
| **Document ID** | REG-RR |
| **Layer** | Register |
| **Owner** | Chief Risk Officer (CRO); CISO for information-security risk subset |
| **Cadence** | Continuous — risks added, treated, monitored, and closed as identified |
| **Implements** | ISO/IEC 27001:2022 Clause 6.1.2 (risk assessment) and 6.1.3 (risk treatment); BNM RMiT (28 Nov 2025) Section 9 (Technology Risk Management), particularly Section 9.1 (TRMF Integration), Section 9.2 (TRMF Minimum Requirements), Section 9.3 (Independent Technology Risk Management Function) |

---

## Purpose

The Risk Register is the authoritative record of all identified information security and technology risks. It captures: the risk, its owner, its rating before and after treatment, the treatment plan, the residual risk acceptance, and the monitoring approach.

The Register is an **operational register** — it is updated continuously, not annually. The annual ISMS Management Review consumes it; it does not exist for the Review.

---

## Schema

| Field | Type | Description | Source |
|---|---|---|---|
| `risk_id` | string | `RISK-YYYY-NNN` (year of registration + sequence) | Auto on creation |
| `title` | string | Short title (≤ 120 chars) | Risk owner |
| `description` | text | Risk description in **threat → vulnerability → impact** form | Risk owner |
| `category` | enum | InfoSec / Tech Ops / Cyber / Third-Party / Data / Compliance / Continuity / People | Risk owner |
| `asset` | reference | Affected information asset(s) | Asset register |
| `owner` | role | Accountable risk owner | Manager (1-up of accountable role) |
| `identified_date` | date | Date risk added | Auto |
| `identified_source` | enum | Assessment / Audit finding / Incident / Pen test / Vulnerability / Third-party report / Other | Risk owner |
| `inherent_likelihood` | enum | 1 (Rare) → 5 (Almost certain) | Risk owner |
| `inherent_impact` | enum | 1 (Insignificant) → 5 (Catastrophic) | Risk owner |
| `inherent_rating` | derived | likelihood × impact | Auto |
| `controls_in_place` | text | Existing controls reducing the risk | Risk owner |
| `residual_likelihood` | enum | 1 → 5 (after existing controls) | Risk owner |
| `residual_impact` | enum | 1 → 5 (after existing controls) | Risk owner |
| `residual_rating` | derived | likelihood × impact | Auto |
| `treatment` | enum | Treat / Tolerate / Transfer / Terminate | Risk owner |
| `treatment_plan` | text | Specific actions, with owners and due dates | Risk owner |
| `target_residual_rating` | derived | likelihood × impact post-treatment | Risk owner |
| `acceptance_authority` | role | Who has accepted current residual risk (CISO / RMC / Board per rating) | Per acceptance matrix |
| `acceptance_date` | date | Date of formal acceptance | Approver |
| `next_review` | date | Per cadence below | Auto |
| `status` | enum | Open / In Treatment / Accepted / Closed | Risk owner |

## Acceptance authority matrix

| Residual rating | Acceptance authority |
|---|---|
| Low (1–4) | Risk owner (line manager) |
| Moderate (5–9) | CISO |
| Significant (10–14) | Risk Management Committee |
| Severe (15–25) | Board of Directors |

## Review cadence

| Residual rating | Review cadence |
|---|---|
| Low | Annual |
| Moderate | Semi-annual |
| Significant | Quarterly |
| Severe | Monthly until reduced |

---

## Worked example — first rows

| risk_id | title | category | owner | inherent | residual | treatment | acceptance | status |
|---|---|---|---|---|---|---|---|---|
| RISK-2026-001 | Ransomware affecting production estate via initial-access broker chain | Cyber | CISO | 5×5 = 25 | 3×4 = 12 | Treat (EDR coverage 100%, immutable backups, network segmentation, phishing controls, IR readiness) | RMC | In Treatment (residual target 2×3 = 6 by Q4 2026) |
| RISK-2026-002 | Privileged credential theft via phishing of administrator | Cyber | CISO | 4×5 = 20 | 2×4 = 8 | Treat (FIDO2 MFA for privileged per STD-02-01, PAM brokering, just-in-time access, dedicated admin workstations) | CISO | Accepted (in line with target) |
| RISK-2026-003 | Cloud misconfiguration exposing customer data | InfoSec / Cloud | CISO | 4×5 = 20 | 2×4 = 8 | Treat (CSPM continuous monitoring, infrastructure-as-code guardrails, security review of new cloud deployments) | CISO | In Treatment |
| RISK-2026-004 | Material outsourcing supplier insolvency disrupting critical service | Third-Party | COO | 3×5 = 15 | 2×4 = 8 | Treat (exit plans per POL-07; supplier financial monitoring; secondary supplier identified for tier-1 services) | RMC | In Treatment |
| RISK-2026-005 | End-of-support legacy application processing customer data | Tech Ops | Head of IT Ops | 4×4 = 16 | 2×3 = 6 | Treat (replacement project funded, scheduled completion Q3 2026; interim compensating segmentation in place) | RMC | In Treatment |
| RISK-2026-006 | Insider misuse of authorised privileged access | Cyber / People | CISO | 3×5 = 15 | 2×4 = 8 | Treat (privileged session recording, quarterly recertification per REG-PAR, anomaly detection use cases) | CISO | Accepted |
| RISK-2026-007 | Personal data breach via mis-sent email | Data / People | DPO | 3×3 = 9 | 2×3 = 6 | Treat (DLP rules, awareness training, encryption defaults) | CISO | Accepted |
| RISK-2026-008 | DDoS impacting internet banking availability | Cyber / Continuity | Head of IT Ops | 4×4 = 16 | 2×3 = 6 | Treat (DDoS protection in place; runbook tested; CDN/WAF tier upstream of bank perimeter) | CISO | Accepted |

> Real entries carry far more detail — full description, controls inventory, action owners and dates, last-review note. The worked example shows the **shape** of useful entries.

---

## Maintenance

- Risks are added by any 1st-line owner; classification and rating reviewed by Technology Risk (2nd line).
- Treatment plans are tracked to closure; overdue actions are reported with the relevant risk in the quarterly RMC pack.
- Closed risks remain in the register (status `Closed`) for audit traceability; they are not deleted.
- The annual ISMS Management Review uses the Register as a primary input.

## Related documents

- **Parent policy:** [POL-00 Information Security Policy](../01-policies/00-information-security-policy.md) Section 8
- **SoA:** [REG-SOA](statement-of-applicability.md)
- **Incident Register:** [REG-INC](incident-register.md) (lessons feed Risk Register)
- **Document control:** [06-document-control](../06-document-control/)
