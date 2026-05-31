# Internal Audit Issues Register

| | |
|---|---|
| **Document ID** | REG-AUD |
| **Layer** | Register |
| **Owner** | Chief Internal Auditor |
| **Cadence** | Continuous — entry per audit issue; ageing reported quarterly |
| **Implements** | BNM RMiT (28 Nov 2025) Section 13 (Internal Audit and Independent Assurance); ISO/IEC 27001:2022 Clause 9.2 (Internal audit) + Clause 10.1 (Continual improvement); IIA IPPF |
| **Source procedure** | [PLN-08 Internal Audit Plan](../05-plans/PLN-08-internal-audit-plan.md); [POL-22 IT Compliance Policy](../02-policies/POL-22-it-compliance-policy.md) |
| **Parent framework(s)** | [TRMF](../01-frameworks/TRMF.md); [CRMF](../01-frameworks/CRMF.md); cross-cutting |
| **COBIT objective(s)** | MEA02 Managed System of Internal Control; MEA04 Managed Assurance |

---

## Purpose

The authoritative record of issues raised by Internal Audit through technology-related audit engagements. Tracks each issue from raising through management response, agreed remediation, validation of closure, and reporting to the BAC. Distinct from [REG-NCA](REG-NCA-ncii-audit-findings-register.md) (NACSA-specific) and [REG-GAP](REG-GAP-rmit-gap-analysis-register.md) (regulatory gap analysis).

## Schema

| Field | Type | Description |
|---|---|---|
| `audit_id` | string | Originating engagement ID (e.g., `IA-2026-03`) |
| `issue_id` | string | `AUD-YYYY-NNNN` |
| `auditable_unit` | enum | TAU number from [PLN-08](../05-plans/PLN-08-internal-audit-plan.md) Audit Universe |
| `title` | text | Issue title |
| `description` | text | Detailed finding |
| `root_cause` | text | Auditor-stated root cause |
| `risk_rating` | enum | `Critical` / `High` / `Medium` / `Low` |
| `affected_control` | array | Links to affected policy / standard / SOP / register |
| `linked_risk` | reference | [REG-TR](REG-TR-technology-risk-register.md) ID where applicable |
| `management_response` | text | 1st/2nd line response statement |
| `agreed_action` | text | Remediation commitment |
| `action_owner` | role | Accountable role |
| `target_date` | date | Committed remediation completion |
| `linked_corrective_action` | reference | [REG-CAP](REG-CAP-corrective-action-register.md) ID |
| `status` | enum | `Open` / `In progress` / `Remediated — awaiting validation` / `Validated closed` / `Past due` / `Withdrawn` |
| `closure_validation_date` | date | When IA validated closure |
| `closure_validation_evidence` | text | What evidence IA reviewed |
| `reported_to_bac` | array | BAC meeting dates this issue was reported |
| `notes` | text | Audit-team commentary |

## Worked example — first entries (illustrative)

| issue_id | audit | TAU | title | risk | owner | target | status |
|---|---|---|---|---|---|---|---|
| AUD-2026-0011 | IA-2026-01 | TAU-03 | Cyber threat intelligence feeds — coverage of OT/IoT threat actors limited | Medium | Head of SOC | 2026-09-30 | In progress |
| AUD-2026-0012 | IA-2026-01 | TAU-03 | Out-of-band communication infrastructure — annual test not evidenced for FY2025 | High | CISO | 2026-06-30 | Remediated — awaiting validation |
| AUD-2026-0023 | IA-2026-03 | TAU-04 | Privileged account quarterly review — 4 service accounts overdue beyond cycle | High | Head of IAM | 2026-07-15 | In progress |
| AUD-2026-0024 | IA-2026-03 | TAU-04 | JML 2-hour leaver disablement — 9 instances exceeded SLA in FY2026 Q1 | Medium | Head of IAM | 2026-08-31 | In progress |
| AUD-2026-0031 | IA-2026-04 | TAU-06 | Independent change reviewer field — 3 instances of self-review identified | High | CIO | 2026-06-30 | Validated closed (2026-06-15) |

### Quarterly ageing snapshot (illustrative — FY2026 Q2)

| Risk rating | Open | In progress | Past due |
|---|---|---|---|
| Critical | 0 | 0 | 0 |
| High | 2 | 5 | 0 |
| Medium | 4 | 7 | 1 |
| Low | 6 | 11 | 2 |

% closed within agreed target: **94%** (47 / 50). Past-due issues: 3 (all Medium / Low). Escalation: 1 past-due Medium issue (AUD-2026-0019) reported to BAC 2026-05-14 with revised target 2026-08-31.

## Maintenance

- Issues are raised by Internal Audit at audit-report close; management response captured within 30 days; agreed action and owner captured at sign-off of the audit report.
- Status changes are owned by the audit team — only IA validates closure.
- Past-due issues are escalated to the BAC at the next meeting and to the RMC if Critical or repeat past-due.
- Repeat issues (same root cause; reopened) are flagged separately in the dashboard.
- Quarterly ageing is reported to the BAC; trend analysis to the Board annually.

## Related documents

- **Source plan:** [PLN-08 Internal Audit Plan](../05-plans/PLN-08-internal-audit-plan.md)
- **Cross-references:** [REG-CAP](REG-CAP-corrective-action-register.md) (corrective actions); [REG-NCA](REG-NCA-ncii-audit-findings-register.md) (NACSA-specific findings); [REG-GAP](REG-GAP-rmit-gap-analysis-register.md) (RMiT compliance gaps); [REG-MR](REG-MR-management-review-register.md) (audit results feed Management Review per ISO 9.3.2 d)

## Document control

| Version | Date | Author | Reviewer | Approver | Change summary |
|---|---|---|---|---|---|
| 1.0 | 2026-05-30 | Chief Internal Auditor | CRO + BAC Chair | Board Audit Committee | Initial version. Closes RMiT Section 13 evidence gap. |
