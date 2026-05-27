# REG-DRR — DR Test Register

| | |
|---|---|
| **Document ID** | REG-DRR | **Owner** | Head of IT Operations |
| **Cadence** | Per test event | **Parent framework** | [BCMF](../01-frameworks/BCMF.md); [TRMF](../01-frameworks/TRMF.md) |
| **Source plan** | [PLN-03](../05-plans/PLN-03-disaster-recovery-plan.md) |

## Purpose
IT-specific record of DR tests — failover, failback, recovery validation per service. Complements [REG-BCT](REG-BCT-bc-test-outcomes-register.md) which covers broader BC scope. Primary evidence for RMiT 10.32 critical-system high-availability testing.

## Schema

| Field | Description |
|---|---|
| `drr_id` | `DRR-YYYY-NNN` |
| `service_id` | Link to [REG-BIA](REG-BIA-business-impact-analysis-register.md) |
| `test_type` | Failover / Failback / Backup restoration / Tamper-proof recovery (RMiT 10.45) / Component / End-to-end |
| `test_scope` | text |
| `executed_date` | |
| `test_lead` | Role |
| `target_rto` / `actual_rto` | per [STD-BC-01](../03-standards/STD-BC-01-recovery-objectives-standard.md) |
| `target_rpo` / `actual_rpo` | per STD-BC-01 |
| `result` | Pass / Pass with findings / Fail |
| `data_integrity_verified` | bool |
| `service_validation_passed` | bool |
| `customer_impact_during_test` | None / Planned outage / Unintended |
| `findings` | text |
| `corrective_actions` | Linked to [REG-CAP](REG-CAP-corrective-action-register.md) |
| `next_test_due` | date |
| `status` | Planned / Executed / Closed |

## Worked example — first entries (illustrative)

| drr_id | service | type | rto_target | rto_actual | result | findings | status |
|---|---|---|---|---|---|---|---|
| DRR-2026-001 | Core Banking (SVC-003) | Failover | 1h | 50min | Pass | None | Closed |
| DRR-2026-002 | Internet Banking (SVC-001) | Failover | 1h | 45min | Pass | None | Closed |
| DRR-2026-003 | Payment Systems (SVC-005) | Failover | 2h | 1h 50min | Pass | Minor — settlement reconciliation took 8min vs 5min target | Closed |
| DRR-2026-004 | Core Banking | Tamper-proof recovery (RMiT 10.45) | 4h | 3h 20min | Pass | Restored from isolated backup environment | Closed |
| DRR-2026-005 | Internet Banking | Backup restoration | n/a (test) | n/a | Pass | Integrity verified; restoration successful | Closed |
| DRR-2026-006 | ATM Network (SVC-006) | Component failover | 4h | 3h 30min | Pass with findings | Branch ATM connectivity 12% degraded mode during cutover | Closed (CAP-2026-0030 raised) |

## Maintenance
- Test schedule per [STD-BC-02 §3.5](../03-standards/STD-BC-02-backup-and-restoration-standard.md) and [PLN-03 §7](../05-plans/PLN-03-disaster-recovery-plan.md).
- Test failures trigger immediate investigation.
- Monthly Head of IT Ops review.
- Quarterly RMC reporting.
- BNM examination consumes this register for RMiT 10.32 evidence.

## Related documents
[STD-BC-01](../03-standards/STD-BC-01-recovery-objectives-standard.md); [STD-BC-02](../03-standards/STD-BC-02-backup-and-restoration-standard.md); [PLN-03](../05-plans/PLN-03-disaster-recovery-plan.md); [REG-BIA](REG-BIA-business-impact-analysis-register.md); [REG-BCT](REG-BCT-bc-test-outcomes-register.md); [REG-CAP](REG-CAP-corrective-action-register.md).
