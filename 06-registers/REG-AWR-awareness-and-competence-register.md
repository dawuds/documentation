# Awareness and Competence Register

| | |
|---|---|
| **Document ID** | REG-AWR |
| **Layer** | Register |
| **Owner** | CHRO (operating); CISO (content + measurement) |
| **Cadence** | Continuous — completion records on rolling basis; aggregate KPI monthly |
| **Implements** | ISO/IEC 27001:2022 Clause 7.2 (Competence — record retention) + Clause 7.3 (Awareness); ISO/IEC 27002:2022 control 6.3; BNM RMiT (28 Nov 2025) Section 15 |
| **Source procedure** | [PLN-07 Awareness and Competence Programme](../05-plans/PLN-07-awareness-and-competence-programme.md) |
| **Parent framework(s)** | [CRMF](../01-frameworks/CRMF.md); [TRMF](../01-frameworks/TRMF.md) |
| **COBIT objective(s)** | APO07 Managed Human Resources; APO13 Managed Security |

---

## Purpose

The mandatory ISO 27001 Clause 7.2 evidence record of competence and awareness — who completed what, when, and with what result. The LMS is the system of record; this register is the canonical schema and the GRC-side evidence index.

## Schema

| Field | Type | Description |
|---|---|---|
| `record_id` | string | `AWR-YYYY-NNNNN` |
| `workforce_id` | string | HRIS identifier (pseudonymised in this register) |
| `workforce_type` | enum | `Employee` / `Contractor` / `Secondee` / `Third party` |
| `role_family` | enum | Per [PLN-07 Section 3.2](../05-plans/PLN-07-awareness-and-competence-programme.md) |
| `curriculum_item` | string | Specific module / training ID |
| `assignment_date` | date | When the item was assigned |
| `due_date` | date | Completion deadline |
| `completion_date` | date | Actual completion |
| `outcome` | enum | `Passed` / `Failed` / `Overdue` / `Waived (with basis)` / `Not applicable` |
| `score` | numeric | Where assessed |
| `attempts` | int | Number of attempts to pass |
| `evidence` | reference | LMS link / certificate ID |
| `next_due` | date | Next refresh due |

## Aggregate KPI roll-up (illustrative — FY2026 Q1)

| KPI | Value | Target | Status |
|---|---|---|---|
| % workforce completed annual baseline within window | 96.4% | ≥ 98% | At risk — gap is in contractor cohort onboarding |
| Phishing click rate (monthly mean Q1) | 6.1% | ≤ 4% | At risk — see [REG-OBJ OBJ-2026-06](REG-OBJ-information-security-objectives-register.md) |
| % new joiners completed onboarding within 30 days | 99.2% | 100% | On track |
| % SOC analysts current on detection-engineering curriculum | 100% | 100% | On track |
| % developers current on secure-development curriculum | 91.4% | 100% | At risk — language-specific gap (Go) |
| % Board members completed annual cyber competence | 100% (8/8) | 100% | On track |
| % NCII-scope roles current on NACSA CoP | 100% | 100% | On track |
| % AI use-case owners current on AI risk curriculum | 84.6% | 100% | At risk — onboarding cycle lag |

### Phishing simulation trend (illustrative)

| Month | Sent | Clicked | Click rate | Reported | Report rate |
|---|---|---|---|---|---|
| 2026-01 | 4,810 | 312 | 6.5% | 1,402 | 29.1% |
| 2026-02 | 4,820 | 287 | 6.0% | 1,547 | 32.1% |
| 2026-03 | 4,830 | 280 | 5.8% | 1,612 | 33.4% |
| 2026-04 | 4,841 | 257 | 5.3% | 1,690 | 34.9% |

Trend: click rate improving 0.4 ppt/month; report rate improving 1.9 ppt/month. Target click rate (≤ 4%) projected to be met by Q3 if trajectory holds.

## Maintenance

- LMS is the source of record; this register is materialised daily from LMS data plus phishing-platform data.
- Failure to complete within window auto-generates a manager notification at 7 days before due, 1 day after due, and 14 days past due (escalation to skip-level).
- Waivers (e.g., long-term leave) require HRBP + CISO joint sign-off and have a defined return-to-curriculum trigger.
- Failed attempts trigger micro-learning + re-attempt; persistent failure (3+ attempts on baseline) triggers conversation with manager and CHRO.
- Aggregate metrics feed [REG-OBJ](REG-OBJ-information-security-objectives-register.md) and [REG-MR](REG-MR-management-review-register.md).

## Related documents

- **Parent plan:** [PLN-07 Awareness and Competence Programme](../05-plans/PLN-07-awareness-and-competence-programme.md)
- **Parent policy:** [POL-HR-01](../02-policies/POL-HR-01-hr-security-policy.md)
- **Feeds-to:** [REG-OBJ](REG-OBJ-information-security-objectives-register.md); [REG-MR](REG-MR-management-review-register.md); [REG-CAP](REG-CAP-corrective-action-register.md) (where KPI fails)

## Document control

| Version | Date | Author | Reviewer | Approver | Change summary |
|---|---|---|---|---|---|
| 1.0 | 2026-05-30 | CHRO + CISO | RMC | Risk Management Committee | Initial version. Closes ISO 7.2 record-retention evidence gap and operationalises PLN-07. |
