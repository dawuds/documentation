# Information Security Objectives Register

| | |
|---|---|
| **Document ID** | REG-OBJ |
| **Layer** | Register |
| **Owner** | CISO |
| **Cadence** | Set annually; tracked quarterly to RMC; reviewed at every Management Review |
| **Implements** | ISO/IEC 27001:2022 Clause 6.2 (Information security objectives and planning to achieve them); Clause 9.1 (Monitoring, measurement, analysis and evaluation); BNM RMiT (28 Nov 2025) Section 9.2(k) (Technology Risk Performance Monitoring); Section 11.2/11.3 (CRF — measurable elements) |
| **Source procedure** | [POL-04 Section 4.4](../02-policies/POL-04-information-security-policy.md); CRMF Section 11 |
| **Parent framework(s)** | [CRMF](../01-frameworks/CRMF.md) |
| **COBIT objective(s)** | APO13 Managed Security; MEA01 Managed Performance and Conformance Monitoring |

---

## Purpose

The **mandatory ISO 27001:2022 Clause 6.2 record** of measurable information security objectives, their target levels, the resources required, who is responsible, when they will be achieved, and how the results will be evaluated. Closes the gap between policy intent ("we will protect customer data") and operational measurement.

Objectives flow from: (a) the Information Security Policy, (b) risk assessment outputs in [REG-TR](REG-TR-technology-risk-register.md), (c) interested-party requirements (Board appetite per [POL-03](../02-policies/POL-03-technology-risk-appetite-statement.md), regulator expectations, Shariah Committee directions), and (d) prior-period performance shortfalls. Objectives are reviewed at every Management Review per [REG-MR](REG-MR-management-review-register.md).

## Schema

| Field | Type | Description |
|---|---|---|
| `objective_id` | string | `OBJ-YYYY-NN` |
| `domain` | enum | `Identity` / `Detection` / `Response` / `Recovery` / `Vulnerability` / `Third-party` / `Data protection` / `Awareness` / `Cloud` / `AI governance` / `Other` |
| `objective_statement` | text | Plain-English objective (Clause 6.2 a — what is to be achieved) |
| `linked_risks` | array | Links to [REG-TR](REG-TR-technology-risk-register.md) entries |
| `linked_appetite_statement` | reference | [POL-03](../02-policies/POL-03-technology-risk-appetite-statement.md) clause |
| `kpi` | string | The measurable indicator (Clause 9.1 — what to measure) |
| `kpi_baseline` | numeric | Where we are starting from |
| `kpi_target` | numeric | What "achieved" looks like |
| `period_start` | date | Clause 6.2 d — when it will be achieved |
| `period_end` | date | |
| `accountable_role` | role | Clause 6.2 c — who is responsible |
| `resources_required` | text | Clause 6.2 b — what will be required (people, budget, tooling) |
| `evaluation_method` | text | Clause 6.2 e — how the result will be evaluated |
| `current_value` | numeric | Latest measurement |
| `current_value_as_of` | date | When current value was last measured |
| `status` | enum | `On track` / `At risk` / `Behind` / `Achieved` / `Carried over` / `Retired` |
| `notes` | text | Quarterly commentary |

## Worked example — first entries (illustrative, FY2026)

| objective_id | domain | objective | kpi | baseline | target | period | accountable | current | as of | status |
|---|---|---|---|---|---|---|---|---|---|---|
| OBJ-2026-01 | Detection | Reduce mean time to detect (MTTD) for SEV-2+ incidents | MTTD minutes (SEV-2 mean, rolling 90 d) | 92 | ≤ 60 | FY2026 | Head of SOC | 47 | 2026-04-30 | Achieved |
| OBJ-2026-02 | Identity | Phishing-resistant MFA rollout to 100% of workforce | % of identities on phishing-resistant MFA | 28% | 100% by 2026-12-31 | FY2026 | Head of IAM | 61% | 2026-04-30 | At risk |
| OBJ-2026-03 | Vulnerability | Internet-facing critical CVE remediation within SLA | % of critical (CVSS 9+ or KEV) closed ≤ 7 days | 87% | ≥ 98% | FY2026 | Head of SOC + Head of IT Ops | 95% | 2026-04-30 | On track |
| OBJ-2026-04 | Third-party | Material TPSP annual reassessment | % of material TPSPs reassessed in cycle | 78% (FY2025) | 100% | FY2026 | Head of TPRM | 32% (Q1 partial) | 2026-04-30 | On track |
| OBJ-2026-05 | Recovery | Quarterly DR test coverage of Tier-1 services | # Tier-1 services DR-tested per quarter | 2 / 6 | 6 / 6 by Q4 | FY2026 | Head of IT Ops + COO | 4 / 6 (cumulative through Q1) | 2026-04-30 | On track |
| OBJ-2026-06 | Awareness | Phishing simulation click rate | Click rate, monthly mean | 8.4% | ≤ 4% | FY2026 | CHRO + CISO | 6.1% | 2026-04-30 | On track |
| OBJ-2026-07 | Data protection | DSAR completion within statutory window | % of DSARs completed ≤ 21 working days | 88% | 100% | FY2026 | DPO | 100% | 2026-04-30 | Achieved |
| OBJ-2026-08 | Cloud | CSPM Critical findings — time to remediation | Mean hours, business-hours-adjusted | 18.7 | ≤ 8 (business) | FY2026 | Head of Cloud | 14.3 | 2026-04-30 | At risk |

## Maintenance

- Objectives are **set at the annual Management Review** (Q1) and ratified by the RMC.
- Each objective links to at least one risk in [REG-TR](REG-TR-technology-risk-register.md) — orphan objectives are a control-design defect.
- KPIs must be **measurable without re-querying source systems on demand** — the measurement is automated.
- Status changes from `On track` to `At risk` or `Behind` trigger an action in [REG-CAP](REG-CAP-corrective-action-register.md) with named owner and intervention plan, presented at the next quarterly review.
- The CISO presents objective performance at every Management Review per [REG-MR](REG-MR-management-review-register.md) input 9.3.2 d.

## Related documents

- **Parent policy:** [POL-04 Section 4.4](../02-policies/POL-04-information-security-policy.md); [POL-03 Technology Risk Appetite](../02-policies/POL-03-technology-risk-appetite-statement.md)
- **Inputs from:** [REG-TR](REG-TR-technology-risk-register.md); [REG-INC](REG-INC-incident-register.md); [REG-VUL](REG-VUL-vulnerability-register.md); [REG-PAR](REG-PAR-privileged-access-review-register.md); [REG-DRR](REG-DRR-dr-test-register.md)
- **Feeds-to:** [REG-MR](REG-MR-management-review-register.md); [REG-CAP](REG-CAP-corrective-action-register.md); Board / RMC quarterly reporting

## Document control

| Version | Date | Author | Reviewer | Approver | Change summary |
|---|---|---|---|---|---|
| 1.0 | 2026-05-30 | CISO | CRO | Risk Management Committee | Initial version. Closes ISO 27001 Clause 6.2 evidence gap identified in v2 multi-agent review (GRC: "no documented evidence pathway for ISMS objectives"). |
