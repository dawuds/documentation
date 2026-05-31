# STD-BC-01 — Recovery Objectives Standard

| | |
|---|---|
| **Document ID** | STD-BC-01 | **Version** | 1.0 |
| **Owner / Approver** | COO + CIO / COO |
| **Parent policy** | [POL-14](../02-policies/POL-14-business-continuity-policy.md) | **Parent framework** | [BCMF](../01-frameworks/BCMF.md) |
| **RMiT clause(s)** | Section 10.24; 10.32; 10.44 |
| **COBIT** | DSS04 | **Practice** | ISO/IEC 22301:2019 Cl. 8.2.3 |

## 1. Purpose
Specify how Recovery Time Objective (RTO), Recovery Point Objective (RPO), and Maximum Tolerable Period of Disruption (MTPD) are set, approved, validated for each GIBB critical service.

## 2. Scope
All critical services identified in [REG-BIA](../06-registers/REG-BIA-business-impact-analysis-register.md).

## 3. Requirements

### 3.1 Tier-aligned default targets

| Tier | MTPD | RTO | RPO |
|---|---|---|---|
| Tier 0 (mission-critical) | ≤ 4 h | ≤ 2 h | ≤ 5 min |
| Tier 1 (critical) | ≤ 24 h | ≤ 8 h | ≤ 30 min |
| Tier 2 (important) | ≤ 72 h | ≤ 24 h | ≤ 4 h |
| Tier 3 (non-critical) | > 72 h | > 24 h | > 4 h |

### 3.2 Per-service targets

Each critical service shall have specific RTO/RPO/MTPD set in [REG-BIA](../06-registers/REG-BIA-business-impact-analysis-register.md), no looser than the tier default unless documented exception per Section 3.5.

### 3.3 Approval and review

| Ref | Requirement |
|---|---|
| 3.3.1 | Per-service targets shall be approved by service owner + RMC at BIA. |
| 3.3.2 | Targets reviewed annually with the BIA refresh; on material change immediately. |

### 3.4 Architecture compliance

| Ref | Requirement |
|---|---|
| 3.4.1 | ICT architecture supporting each critical service shall be designed to meet the target — data replication, failover, redundancy proportionate to tier. |
| 3.4.2 | Tier 0 services shall have synchronous data replication where technically feasible; near-synchronous otherwise. |

### 3.5 Exceptions

| Ref | Requirement |
|---|---|
| 3.5.1 | RTO/RPO targets looser than tier default require RMC approval and documented compensating mitigation. |

### 3.6 Test validation

| Ref | Requirement |
|---|---|
| 3.6.1 | Per-service targets shall be validated annually through DRP test (failover-and-verify per service per year on multi-year cycle). |
| 3.6.2 | Test outcome shall measure actual achieved RTO/RPO vs target. Variance > 20% requires remediation plan. |

## 4. Exceptions
Per Section 3.5 + [POL-14](../02-policies/POL-14-business-continuity-policy.md).

## 5. Related documents
[POL-14](../02-policies/POL-14-business-continuity-policy.md); [PLN-02](../05-plans/PLN-02-business-continuity-plan.md); [REG-BIA](../06-registers/REG-BIA-business-impact-analysis-register.md); [STD-BC-02](STD-BC-02-backup-and-restoration-standard.md); [BCMF](../01-frameworks/BCMF.md)

## 6. References
BNM RMiT 28 Nov 2025 Section 10.24; 10.32; 10.44; ISO/IEC 22301:2019 Cl. 8.2.3; BNM BCM PD.

## 7. Document control
| Version | Date | Author | Approver | Change |
|---|---|---|---|---|
| 1.0 | [Effective] | COO + CIO | COO | Initial |
