# REG-BCT — BC Test Outcomes Register

| | |
|---|---|
| **Document ID** | REG-BCT | **Owner** | Head of Business Continuity (under COO) |
| **Cadence** | Per test event | **Parent framework** | [BCMF](../01-frameworks/BCMF.md) |

## Purpose
Authoritative record of all business continuity test outcomes and real-event BC activations. Primary evidence consumed by RMC, Internal Audit, BNM examinations on BC.

## Schema

| Field | Description |
|---|---|
| `bct_id` | `BCT-YYYY-NNN` |
| `event_type` | Tabletop / Functional / End-to-end / Joint exercise / **Real-event activation** |
| `scope_services` | Multi reference to [REG-BIA](REG-BIA-business-impact-analysis-register.md) |
| `scenario_or_event` | text |
| `planned_date` / `executed_date` | dates |
| `bc_lead` | role |
| `executive_participation` | bool |
| `target_rto_achieved` | bool per scope |
| `target_rpo_achieved` | bool per scope |
| `actual_rto` | duration |
| `actual_rpo` | duration |
| `gaps_identified` | text + count |
| `corrective_actions` | Linked to [REG-CAP](REG-CAP-corrective-action-register.md) |
| `customer_impact` | If real event |
| `bnm_notification` | If real material event |
| `lessons` | text |
| `rmc_reported` | date |
| `status` | Planned / Executed / Debrief / Closed |

## Worked example — first entries (illustrative)

| bct_id | type | scope | scenario | date | rto_met | gaps | status |
|---|---|---|---|---|---|---|---|
| BCT-2026-Q1 | Tabletop | Internet banking + mobile | Primary data centre cooling failure | 2026-03-10 | n/a (simulated) | 4 (decision-rights ambiguity) | Closed |
| BCT-2026-Q2-FN-01 | Functional | Core banking (deposits) | Failover to secondary site | 2026-05-22 | Yes (1h 45min vs target 2h) | 2 (data replication lag on one customer-records table) | Closed |
| BCT-2026-Q2-FN-02 | Functional | Internet banking | Failover to secondary cloud region | 2026-05-30 | Yes (45min vs target 1h) | 1 (CDN cache pre-warming) | Closed |
| BCT-2026-Q3-E2E | End-to-end | Core banking + payment systems (joint) | Primary site total loss simulation | 2026-09-25 | (planned) | (TBD) | Planned |
| BCT-2026-EVENT-01 | **Real-event activation** | Internet banking | DDoS event partially impacting service | 2026-04-15 | Yes (degraded mode within 30 min; full service within 1h 15min vs target 1h) | 1 (DDoS protection tuning) | Closed |

## Maintenance
- Head of BC creates entry pre-test (planned status) and updates through completion.
- Real-event entries flagged distinctly; clear separation from test entries.
- Quarterly RMC summary.
- Annual programme review per [POL-14 Section 4.5](../02-policies/POL-14-business-continuity-policy.md).

## Related documents
[POL-14](../02-policies/POL-14-business-continuity-policy.md); [PLN-02](../05-plans/PLN-02-business-continuity-plan.md); [PLN-03](../05-plans/PLN-03-disaster-recovery-plan.md); [REG-BIA](REG-BIA-business-impact-analysis-register.md); [REG-DRR](REG-DRR-dr-test-register.md); [REG-CAP](REG-CAP-corrective-action-register.md).
