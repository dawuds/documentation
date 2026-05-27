# PLN-03-CB — Core Banking DRP

| | |
|---|---|
| **Document ID** | PLN-03-CB | **Version** | 1.0 |
| **Owner / Approver** | Head of IT Operations + Head of Core Banking |
| **Parent plan** | [PLN-03 Master DRP](PLN-03-disaster-recovery-plan.md) |
| **Service** | SVC-003 Core Banking (deposits + financing); SVC-004 Core Banking — Islamic financing |
| **Service tier** | Tier 0 |
| **RTO target** | 2 hours | **RPO target** | 1 minute (synchronous replication) |

## 1. Architecture summary
- Primary: GIBB on-prem data centre (DC-1), active
- Secondary: cloud-region Malaysia, hot-standby with synchronous replication
- Tertiary: cloud-region Singapore, warm-standby for catastrophic event (cross-border per [STD-CL-03](../03-standards/STD-CL-03-cloud-data-residency-standard.md) basis)
- Tamper-proof backup: immutable storage in isolated recovery environment per RMiT 10.45

## 2. Activation triggers
- Primary DC-1 loss (any cause)
- Core banking application-tier or database-tier total outage > 30 minutes trending to MTPD (4h)
- Cyber-induced encryption / corruption affecting primary + secondary
- Network segmentation isolating DC-1 from rest of estate

## 3. DR Commander
Head of IT Operations (Primary) / Deputy Head of IT Ops (Alternate). Cyber-induced: joint with CISO.

## 4. Recovery procedure

### Failover (primary → secondary cloud-MY)
| # | Action | Owner | SLA |
|---|---|---|---|
| 1 | Confirm primary unrecoverable in RTO; DR Commander decision | DR Commander | ≤ 30 min from trigger |
| 2 | Validate secondary replica lag (target ≤ 1 min) | DBA Lead | ≤ 10 min |
| 3 | Promote secondary replica to primary | DBA Lead | ≤ 20 min |
| 4 | Re-point application tier; smoke-test | Core Banking app team | ≤ 30 min |
| 5 | Shariah-compliance smoke test (Murabahah, Musharakah, Wadiah, Mudharabah transaction paths) | Shariah Compliance + app team | ≤ 20 min |
| 6 | Customer-facing service re-enable | DR Commander + Customer Ops | ≤ 30 min |
| 7 | Enhanced monitoring for 24 hours | SOC | Continuous post-cutover |

Total target: 2 hours from trigger.

### Cyber-induced — tamper-proof recovery
| # | Action | Owner |
|---|---|---|
| 1 | Containment first per [PLN-01 IRP](PLN-01-incident-response-plan.md) | CISO + DR Commander joint |
| 2 | Assess recovery target — clean isolated recovery environment per RMiT 10.45 | DR Commander |
| 3 | Restore from latest tamper-proof immutable backup per [SOP-BC-03](../04-procedures/SOP-BC-03-tamper-proof-backup-verification-sop.md) | Backup Operator (dual-control) |
| 4 | IoC sweep of recovered environment | SOC |
| 5 | Validation before customer re-enablement | DR Commander |
| 6 | Failback only after primary forensic-cleared | DR Commander + CISO |

## 5. Customer communication
Per [PLN-04 Crisis Comms](PLN-04-crisis-communications-plan.md). Templated holding statement for "core banking service disruption" available.

## 6. Regulatory communication
- BNM: per RMiT 11.18 (4-hour clock with source-chain caveat per [POL-13](../02-policies/POL-13-incident-management-policy.md)) — coordinated by CCO
- BNM material outsourcing notification (if cloud-secondary failover) per [POL-10](../02-policies/POL-10-it-vendor-management-policy.md)

## 7. Testing
- Quarterly: failover component test (database replica promotion)
- Annually: full failover exercise to cloud-MY with documented validation
- Biennially: failover to cloud-SG (cross-border) with PDPA + BNM Outsourcing PD considerations

## 8. Document control
| Version | Date | Author | Approver | Change |
|---|---|---|---|---|
| 1.0 | [Effective] | Head of IT Ops + Head of Core Banking | COO + CIO | Initial |
