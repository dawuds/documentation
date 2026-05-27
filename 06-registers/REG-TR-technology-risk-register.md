# REG-TR — Technology Risk Register

| | |
|---|---|
| **Document ID** | REG-TR |
| **Layer** | Register (Layer 6) |
| **Owner** | Chief Risk Officer (Head of Technology Risk Management operates) |
| **Classification** | Internal |
| **Cadence** | Continuous |
| **Parent framework(s)** | [TRMF](../01-frameworks/TRMF.md) |
| **Source procedure** | TRMF Section 8 (Lifecycle / operating model); [POL-02 Technology Risk Management Policy](../02-policies/POL-02-technology-risk-management-policy.md) |
| **Implements** | RMiT 9.2(h) (effective information system for technology risk profile) |

---

## Purpose

The authoritative record of all identified technology risks at GIBB. Captures the risk, its owner, ratings, treatment plan, residual acceptance, and monitoring approach. Primary evidence consumed by RMC, Board, Internal Audit, BNM, and NACSA in reviewing GIBB's technology risk posture.

## Schema

| Field | Type | Description | Source |
|---|---|---|---|
| `risk_id` | string | `RISK-YYYY-NNN` | Auto on creation |
| `title` | string (≤ 120 chars) | Short title | Risk owner |
| `description` | text | Threat → Vulnerability → Impact form | Risk owner |
| `risk_category` | enum | Cyber / Third-Party / Data / Cloud / AI / Operational / Emerging / Other | Risk owner |
| `risk_sub_category` | string | E.g., ransomware, supply chain, model bias | Risk owner |
| `affected_assets` | reference | CMDB IDs of affected assets | Asset register |
| `business_lines_affected` | enum (multi) | Retail / Commercial / Corporate / Treasury / Cross-functional | Risk owner |
| `identified_date` | date | Date risk added | Auto |
| `identified_source` | enum | Assessment / Audit / Incident / Pen test / Vuln / TPSP report / Horizon-scanning / Other | Risk owner |
| `owner_role` | role | Risk owner (function head) | Per RACI |
| `owner_name` | string | Named individual | Owner-attributed |
| `cro_concurrence` | bool | 2nd-line CRO function concurrence | TRM function |
| `inherent_likelihood` | enum 1–5 | Per TRMF Section 8.2.1 | Risk owner |
| `inherent_impact` | enum 1–5 | Per TRMF Section 8.2.1 | Risk owner |
| `inherent_rating` | derived | L × I | Auto |
| `controls_in_place` | text | List + references | Risk owner |
| `residual_likelihood` | enum 1–5 | After controls | Risk owner |
| `residual_impact` | enum 1–5 | After controls | Risk owner |
| `residual_rating` | derived | L × I | Auto |
| `material` | bool | Per TRMF Section 8.2 materiality test | Risk owner + CRO |
| `appetite_alignment` | enum | Within / At / Above (per [POL-03](../02-policies/POL-03-technology-risk-appetite-statement.md)) | TRM function |
| `treatment` | enum | Treat / Tolerate / Transfer / Terminate | Risk owner |
| `treatment_plan_id` | reference | Link to treatment plan document | Auto |
| `target_residual_rating` | derived | Post-treatment target | Risk owner |
| `acceptance_authority` | enum | Owner / CRO / RMC / Board | Per TRMF 8.3 matrix |
| `acceptance_date` | date | When approved | Approver |
| `next_review` | date | Per residual rating cadence | Auto |
| `status` | enum | Open / In Treatment / Accepted / Closed | Risk owner |
| `framework_links` | reference (multi) | Layer 2 frameworks affected (TRMF, CRMF, BCMF, etc.) | Risk owner |
| `regulatory_links` | reference (multi) | RMiT clauses, NACSA, PDPA where relevant | TRM function |

## Acceptance authority matrix

| Residual rating | Acceptance authority |
|---|---|
| Low (1–5) | Risk owner |
| Moderate (6–10) | CRO |
| Significant (11–15) | Risk Management Committee |
| Severe (16–25) | Board of Directors |

## Review cadence by rating

| Rating | Review cadence |
|---|---|
| Low | Annual |
| Moderate | Semi-annual |
| Significant | Quarterly |
| Severe | Monthly until reduced |

## Worked example — first rows (illustrative)

| risk_id | title | category | inherent | residual | treatment | acceptance | status |
|---|---|---|---|---|---|---|---|
| RISK-2026-001 | Ransomware affecting production estate via initial-access broker chain | Cyber | 5×5 = 25 | 3×4 = 12 | Treat (EDR coverage 100%, immutable backups per RMiT 10.45, network segmentation per RMiT 10.43, IR readiness per CRMF) | RMC | In Treatment — residual target 2×3 = 6 by Q4 2026 |
| RISK-2026-002 | Privileged credential theft via phishing of administrator | Cyber | 4×5 = 20 | 2×4 = 8 | Treat (FIDO2 MFA for privileged per RMiT 10.55, PAM brokering, just-in-time access, dedicated admin workstations) | CRO | Accepted (within appetite target) |
| RISK-2026-003 | Cloud misconfiguration exposing customer data | Cloud / Data | 4×5 = 20 | 2×4 = 8 | Treat (CSPM continuous monitoring per CloudRMF, IaC guardrails, cloud security review of new deployments) | CRO | In Treatment |
| RISK-2026-004 | Material outsourcing supplier insolvency disrupting critical service | Third-Party / Operational | 3×5 = 15 | 2×4 = 8 | Treat (exit plans per TPRMF, supplier financial monitoring, secondary supplier for tier-1 services) | RMC | In Treatment |
| RISK-2026-005 | End-of-support legacy application processing customer data | Operational / Emerging | 4×4 = 16 | 2×3 = 6 | Treat (replacement project funded, scheduled completion Q3 2026; interim compensating segmentation) | RMC | In Treatment |
| RISK-2026-006 | Insider misuse of authorised privileged access | Cyber / People | 3×5 = 15 | 2×4 = 8 | Treat (privileged session recording, quarterly recertification, anomaly detection use cases under CRMF) | CRO | Accepted |
| RISK-2026-007 | Personal customer data breach via mis-sent email | Data / People | 3×3 = 9 | 2×3 = 6 | Treat (DLP rules, awareness training, encryption defaults; CIMF lawful-basis discipline) | CRO | Accepted |
| RISK-2026-008 | DDoS impacting digital banking availability | Cyber / Continuity | 4×4 = 16 | 2×3 = 6 | Treat (DDoS protection in place; runbook tested per BCMF; CDN/WAF tier upstream) | CRO | Accepted |
| RISK-2026-009 | AI model bias in retail credit decisioning | AI / Customer | 3×4 = 12 | 2×3 = 6 | Treat (model validation per AIGF, fairness monitoring continuous, human review of declines, retraining trigger) | CRO | In Treatment |
| RISK-2026-010 | Shariah-compliance logic regression after product system change | Shariah / Operational | 3×5 = 15 | 1×4 = 4 | Treat (mandatory Shariah review gate per POL-07 §4.3.2 and POL-17 §4.12.1; automated Shariah regression tests in CI) | Risk owner | Accepted |

> Real entries carry full description, controls inventory, action owners and dates, last-review note, and links to evidence. The worked example shows the shape of useful entries.

## Maintenance

- Risks added by any 1st-line owner; classification and rating reviewed by Technology Risk Management (2nd line).
- Treatment plans tracked to closure; overdue actions reported with the relevant risk in quarterly RMC pack.
- Closed risks retained for audit traceability (status `Closed`); not deleted.
- Annual ISMS / TRMF Management Review uses this register as a primary input.
- Quarterly: TRM function reconciles register against KRI/KCI dashboard; identifies under-reported risk categories.

## Related documents

- **Parent framework:** [TRMF](../01-frameworks/TRMF.md)
- **Parent policy:** [POL-02 Technology Risk Management Policy](../02-policies/POL-02-technology-risk-management-policy.md)
- **Companion policy:** [POL-03 Technology Risk Appetite Statement](../02-policies/POL-03-technology-risk-appetite-statement.md)
- **Cross-frameworks:** All Layer 2 frameworks contribute risks to this register
- **Document control:** [07-document-control](../07-document-control/)
