# PLN-03 — Disaster Recovery Plan

| | |
|---|---|
| **Document ID** | PLN-03 | **Version** | 1.0 |
| **Owner / Approver** | Head of IT Operations / COO + CIO |
| **Parent framework** | [BCMF](../01-frameworks/BCMF.md); secondary [TRMF](../01-frameworks/TRMF.md) |
| **Parent policy** | [POL-14](../02-policies/POL-14-business-continuity-policy.md) |
| **RMiT clause(s)** | Section 10.24–10.28; 10.32; 10.44–10.45 |

> This is the **master DRP** for GIBB. Per-service DRPs (e.g., PLN-03-CB Core Banking DRP, PLN-03-IB Internet Banking DRP, PLN-03-PMT Payment Systems DRP) are subordinate documents derived from this master and not included in this repo. The master DRP establishes the structure that per-service DRPs follow.

## 1. Purpose
To establish how GIBB recovers critical IT services from infrastructure-level disasters — primary site loss, primary-secondary loss, cloud-region loss, destructive cyber attack. Operationalises [POL-14](../02-policies/POL-14-business-continuity-policy.md) and the recovery commitments in [REG-BIA](../06-registers/REG-BIA-business-impact-analysis-register.md).

## 2. Scope

Critical IT services (Tier 0 and Tier 1) per [REG-BIA](../06-registers/REG-BIA-business-impact-analysis-register.md). Each service has a per-service DRP cross-referenced to this master plan.

## 3. Activation

| Trigger | Activation authority |
|---|---|
| Primary data centre loss or partial outage exceeding 30% of capacity | Head of IT Operations + COO |
| Cloud region loss (primary IaaS region) | Head of Cloud + COO |
| Destructive cyber attack (ransomware affecting production) | CISO + COO (joint, in coordination with [PLN-01 IRP](PLN-01-incident-response-plan.md)) |
| Multi-system outage with cascading customer impact | COO |
| Per-service RTO breach trending | Service owner + COO |

Activation creates: DR bridge; assigned DR Commander per service; activation log in [REG-DRR DR Test Register](../06-registers/REG-DRR-dr-test-register.md) (event entries flagged distinctly from test entries).

## 4. Roles and contacts

| Role | Default | Alternate | Out-of-band |
|---|---|---|---|
| **DR Commander** (overall) | Head of IT Operations | Deputy Head of IT Ops | Mobile + on-call card |
| **Per-service DR Lead** (service owner) | Per service | Deputy | Mobile + on-call card |
| **Cloud DR Lead** | Head of Cloud | Deputy | Mobile + on-call card |
| **Network Lead** | Head of Network | Deputy | Mobile + on-call card |
| **DBA Lead** | DBA Lead | Senior DBA | Mobile + on-call card |
| **Communications Lead** (with BC) | Head of Corp Comms | Deputy | Mobile + email |
| **Cyber Liaison** (if cyber-induced) | CISO | Deputy CISO | Per IRP |
| **CIO** (overall accountability) | CIO | CTO | Mobile + secure channel |

## 5. Recovery phases

### 5.1 Damage assessment

- DR Commander confirms scope: affected services, infrastructure, estimated duration.
- Compare projected outage against MTPD per service from [REG-BIA](../06-registers/REG-BIA-business-impact-analysis-register.md).
- Decide: failover (start) / wait-and-restore / hybrid.

### 5.2 Failover decision

- For Tier 0 services breaching or trending to breach RTO: failover authorised by DR Commander.
- For Tier 1 services: failover authorised by service owner + DR Commander.
- Cyber-induced disruption: failover to clean recovery environment per [STD-BC-02 Section 3.4](../03-standards/STD-BC-02-backup-and-restoration-standard.md) tamper-proof isolated recovery.

### 5.3 Service-by-service failover

Per per-service DRP. Each service has documented runbook covering:
- Pre-checks; environment validation
- Data replication state confirmation
- Switchover execution
- Validation post-switchover
- Customer-facing service re-enablement
- Reverse-failback plan

### 5.4 Validation

- Each restored service validated against pre-disaster baseline before customer re-enablement.
- For cyber-induced: enhanced security validation (IoC sweep on recovered environment).
- DR Commander signs off restoration per service.

### 5.5 Customer-facing re-enablement

- DR Commander + Communications Lead coordinate customer communication.
- Phased re-enablement preferred — internal users first, then customer-facing.
- Customer-facing services enabled only after validation passes.

### 5.6 Failback

- Once primary infrastructure restored: planned failback at scheduled window.
- Failback follows same rigour as failover — pre-checks, validation, sign-off.

### 5.7 Post-event review

- Within 15 working days: full DR event review.
- Lessons captured in [REG-DRR](../06-registers/REG-DRR-dr-test-register.md).
- Update master DRP and per-service DRPs as warranted.

## 6. Communication

Per [PLN-02 BCP Section 6](PLN-02-business-continuity-plan.md). Specifically:
- BNM notification per [POL-13 Section 4.4.3](../02-policies/POL-13-incident-management-policy.md) for material disruption.
- Customer communication per [PLN-04 Crisis Communications Plan](PLN-04-crisis-communications-plan.md).
- Shariah Liaison engagement if affecting Shariah-compliant services materially.

## 7. Testing and exercise

| Frequency | Type | Owner |
|---|---|---|
| Quarterly | Failover test for one Tier 0 service (rotating) | Head of IT Ops + service owner |
| Annually | Full DR exercise (end-to-end primary-to-secondary failover for one critical service per year on multi-year cycle) | Head of IT Ops + COO |
| Annually overlapping | Joint BCP/DRP/IRP exercise | Head of IT Ops + COO + CISO |

Test outcomes documented in [REG-DRR](../06-registers/REG-DRR-dr-test-register.md). Material findings reported to RMC.

## 8. Reference appendices

(Maintained separately for distribution control.)

- Appendix A — Per-service DRP index (PLN-03-x)
- Appendix B — Primary-secondary infrastructure map
- Appendix C — Cloud region failover procedures (per provider)
- Appendix D — Tamper-proof recovery procedure for cyber-induced loss
- Appendix E — Failback procedures

## 9. Document control
| Version | Date | Author | Reviewer | Approver | Change |
|---|---|---|---|---|---|
| 1.0 | [Effective] | Head of IT Ops | RMC | COO + CIO | Initial Effective version |
