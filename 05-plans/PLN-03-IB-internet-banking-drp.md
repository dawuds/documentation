# PLN-03-IB — Internet Banking DRP

| | |
|---|---|
| **Document ID** | PLN-03-IB | **Version** | 1.0 |
| **Owner / Approver** | Head of IT Operations + Head of Digital Channels |
| **Parent plan** | [PLN-03 Master DRP](PLN-03-disaster-recovery-plan.md) |
| **Service** | SVC-001 Internet Banking — retail (Islamic); SVC-002 Mobile Banking — retail (Islamic) |
| **Service tier** | Tier 0 |
| **RTO target** | 1 hour | **RPO target** | 1 minute |

## 1. Architecture summary
- Primary: cloud-region Malaysia (CL-0001 IaaS active-active across availability zones)
- Secondary: cloud-region Malaysia (alternate provider — CL-0002) for provider-level failover
- Tertiary: cloud-region Singapore (CL-0002 DR region) — cross-border per [STD-CL-03](../03-standards/STD-CL-03-cloud-data-residency-standard.md)
- Customer authentication: cloud IDP (CL-0003) with regional failover
- CDN/WAF: multi-tier upstream of bank perimeter
- Data sync to Core Banking per real-time messaging fabric

## 2. Activation triggers
- Primary cloud-region MY material outage
- DDoS or other cyber attack causing service unavailability > 30 min
- Application-tier failure not recoverable in primary
- Customer Identity Provider failure (separate failover plan)

## 3. DR Commander
Head of Digital Channels (Primary). Cyber-induced: joint with CISO.

## 4. Recovery procedure

### Failover (primary cloud-region → secondary cloud provider)
| # | Action | Owner | SLA |
|---|---|---|---|
| 1 | Confirm primary unrecoverable in RTO | DR Commander | ≤ 15 min |
| 2 | Activate CDN/WAF traffic re-routing to secondary cloud | Network team | ≤ 10 min |
| 3 | Promote secondary application stack (already running warm) | Cloud team | ≤ 15 min |
| 4 | Validate data sync from Core Banking to secondary | Integration team | ≤ 5 min |
| 5 | Smoke-test critical transaction paths (Islamic + conventional product views) | App team | ≤ 10 min |
| 6 | Customer-facing service re-enable | DR Commander | ≤ 5 min |
| 7 | Enhanced monitoring | SOC | Continuous |

Total target: 1 hour.

### DDoS / volumetric attack handling
DDoS protection (CL-0005) is upstream; first-line response is per [PLN-01 IRP](PLN-01-incident-response-plan.md) SOC playbook. DRP activation only if DDoS overwhelms and primary remains unavailable > 30 min.

## 5. Customer communication
Per [PLN-04](PLN-04-crisis-communications-plan.md). In-app banner + mobile notification + customer support scripting.

## 6. Regulatory communication
- BNM per RMiT 11.18 (**4-hour clock with source-chain caveat** per [POL-13 Section 4.4.3](../02-policies/POL-13-incident-management-policy.md) — the 4-hour figure is the bank's operating expectation derived from BNM Operational Risk Reporting PD Part C and BCM Part C, not stated numerically in RMiT 11.18 verbatim; CCO maintains the authoritative clock) — coordinated by CCO
- BNM Digital Services notification under RMiT Section 12 if material change to customer-facing delivery

## 7. Testing
- Monthly: WAF / CDN failover test
- Quarterly: secondary cloud activation test
- Annually: full multi-region failover with executive participation

## 8. Document control
| Version | Date | Author | Approver | Change |
|---|---|---|---|---|
| 1.0 | [Effective] | Head of IT Ops + Head of Digital Channels | COO + CIO | Initial |
