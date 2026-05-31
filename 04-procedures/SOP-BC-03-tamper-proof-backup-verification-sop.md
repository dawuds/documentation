# SOP-BC-03 — Tamper-Proof Backup Verification SOP

| | |
|---|---|
| **Document ID** | SOP-BC-03 | **Version** | 1.0 |
| **Owner / Approver** | Head of IT Operations + CISO |
| **Parent standard** | [STD-BC-02 Section 3.4](../03-standards/STD-BC-02-backup-and-restoration-standard.md) | **Parent policy** | [POL-14](../02-policies/POL-14-business-continuity-policy.md) |
| **RMiT clause(s)** | Section 10.45 (Tamper-Proof Backup and Isolated Recovery) |

## 1. Purpose
Verify the integrity and recoverability of GIBB's tamper-proof / immutable backup capability per RMiT 10.45 — including the isolated recovery environment.

## 2. Trigger
Monthly verification cycle. Plus ad-hoc verification post any cyber incident affecting primary or secondary storage.

## 3. Procedure — monthly verification

| # | Actor | Action | Output |
|---|---|---|---|
| 1 | Backup Operator | Select Tier 0/1 immutable backup target per rotation | Selection |
| 2 | Backup Operator | Confirm immutability lock active (storage-layer attestation) | Lock confirmed |
| 3 | Backup Operator | Attempt to modify backup (negative test) — should fail | Failure confirmed (test pass) |
| 4 | Backup Operator (dual-control with CISO delegate) | Authenticate to isolated recovery environment | Access verified |
| 5 | Backup Operator | Restore selected backup into isolated recovery environment | Restoration |
| 6 | Backup Operator | Verify restored data integrity (hash check) | Hash verified |
| 7 | Backup Operator | Run service smoke test in isolated environment | Service operational |
| 8 | Backup Operator | Tear down test environment; verify no leakage to production | Clean tear-down |
| 9 | Backup Operator | Record in [REG-DRR](../06-registers/REG-DRR-dr-test-register.md) with type "Tamper-proof recovery" | DRR entry |
| 10 | Head of IT Ops + CISO | Review monthly verification batch | Review record |

## 4. Procedure — post-incident verification

Following any incident potentially affecting backup storage:

| # | Actor | Action |
|---|---|---|
| 1 | CISO | Activate post-incident verification |
| 2 | Backup Operator | Verify immutability lock unchanged |
| 3 | Backup Operator | Verify integrity hashes |
| 4 | Backup Operator | Sample restoration to isolated environment |
| 5 | CISO | Document outcome; if anomaly detected, treat as SEV-1 |

## 5. Annual full test
Annual full-failover test of tamper-proof + isolated recovery for one Tier 0 service per [PLN-03 Section 7](../05-plans/PLN-03-disaster-recovery-plan.md).

## 6. Exception handling
Verification failure on tamper-proof backup: SEV-1 incident; CISO + COO engaged; investigation of integrity-lock or backup-process compromise.

## 7. Evidence
Verification records; hash logs; isolated recovery environment access logs (dual-control); DRR entries. Retained permanently for compliance with RMiT 10.45.

## 8. Document control
| Version | Date | Author | Approver | Change |
|---|---|---|---|---|
| 1.0 | [Effective] | Head of IT Ops + CISO | Head of IT Ops | Initial |
