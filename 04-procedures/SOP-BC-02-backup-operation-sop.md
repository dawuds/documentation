# SOP-BC-02 — Backup Operation SOP

| | |
|---|---|
| **Document ID** | SOP-BC-02 | **Version** | 1.0 |
| **Owner / Approver** | Head of IT Operations |
| **Parent standard** | [STD-BC-02](../03-standards/STD-BC-02-backup-and-restoration-standard.md) | **Parent policy** | [POL-14](../02-policies/POL-14-business-continuity-policy.md); [POL-16](../02-policies/POL-16-operations-security-policy.md) |

## 1. Purpose
Day-to-day operation of GIBB backup function per [STD-BC-02](../03-standards/STD-BC-02-backup-and-restoration-standard.md).

## 2. Trigger
Scheduled backup cycles; on-demand backup before material changes; recovery requests.

## 3. Procedure — daily operations

| # | Actor | Action | SLA |
|---|---|---|---|
| 1 | Backup Operator | Monitor scheduled backup jobs across systems | Continuous |
| 2 | Backup Operator | Triage backup failures — categorise (transient / persistent / infrastructure / capacity) | ≤ 4 hours from failure detection |
| 3 | Backup Operator | Re-run transient failures; raise ticket for persistent | Per category |
| 4 | Backup Operator | Verify integrity hash on completed backups (sample) | Daily |
| 5 | Backup Operator | Confirm geographic separation — primary + DR site replication completed | Daily |

## 4. Procedure — restoration request

| # | Actor | Action | SLA |
|---|---|---|---|
| 1 | Requester | Submit restore request with: target service, restore point, justification | Per request |
| 2 | Backup Operator | Verify authorisation per service owner | ≤ 1 hour |
| 3 | Backup Operator | Identify and validate backup artefact (hash check) | Per request |
| 4 | Backup Operator | Restore to staging environment first (where possible) | Per restore complexity |
| 5 | Requester + Backup Operator | Validate restored data | Per request |
| 6 | Backup Operator | Production restore if validation passed | Per change-management |
| 7 | Backup Operator | Document restoration outcome | Same day |

## 5. Procedure — monthly restorability test
Per [STD-BC-02 Section 3.5](../03-standards/STD-BC-02-backup-and-restoration-standard.md).

| # | Actor | Action |
|---|---|---|
| 1 | Backup Operator | Select Tier 0/1 backup target per rotation schedule |
| 2 | Backup Operator | Execute automated restore-and-validate to test environment |
| 3 | Backup Operator | Compare restored data against integrity expectations |
| 4 | Head of IT Ops | Review test result; failures trigger investigation |
| 5 | Head of IT Ops | Record outcome in [REG-DRR](../06-registers/REG-DRR-dr-test-register.md) |

## 6. Exception handling
Backup failure on Tier 0 service > 4 hours: SEV-3 incident raised. Repeated failures over 7-day window: SEV-2.

## 7. Evidence
Backup logs; restore logs; integrity verification records; monthly test results. Retained per [STD-CR-02 Section 3.6](../03-standards/STD-CR-02-logging-standard.md).

## 8. Document control
| Version | Date | Author | Approver | Change |
|---|---|---|---|---|
| 1.0 | [Effective] | Head of IT Ops | Head of IT Ops | Initial |
