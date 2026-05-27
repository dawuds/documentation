# PLN-03-PMT — Payment Systems DRP

| | |
|---|---|
| **Document ID** | PLN-03-PMT | **Version** | 1.0 |
| **Owner / Approver** | Head of IT Operations + Head of Treasury Operations |
| **Parent plan** | [PLN-03 Master DRP](PLN-03-disaster-recovery-plan.md) |
| **Service** | SVC-005 Payment Systems (RENTAS / IBG / Mobile P2P) — Islamic-compliant |
| **Service tier** | Tier 0 |
| **RTO target** | 2 hours | **RPO target** | 1 minute |

## 1. Architecture summary
- Primary: on-prem DC-1 (payment processing engine)
- Secondary: cloud-region Malaysia (warm-standby)
- BNM RENTAS connectivity: redundant network paths (primary + secondary)
- IBG (Interbank GIRO) connectivity: redundant
- Mobile P2P: cloud-native with regional redundancy
- Settlement reconciliation: in-flight transaction reconciliation per cutover

## 2. Activation triggers
- DC-1 loss (any cause)
- Payment processing application failure > 30 min
- BNM RENTAS connectivity loss on both paths > 15 min
- Cyber-induced — destructive attack affecting payment data

## 3. DR Commander
Head of Treasury Operations + Head of IT Operations joint. Cyber-induced: + CISO.

## 4. Recovery procedure

### Failover
| # | Action | Owner | SLA |
|---|---|---|---|
| 1 | Confirm primary unrecoverable; DR Commander decision | DR Commander | ≤ 30 min |
| 2 | Pause new payment initiation at customer-facing layer | Digital Channels + Branch Ops | ≤ 5 min |
| 3 | Complete in-flight transactions at primary if possible | Payments app team | ≤ 30 min (best effort) |
| 4 | Promote secondary payment engine | DBA Lead + Payments app team | ≤ 30 min |
| 5 | Reconcile in-flight transactions (settlement integrity) | Treasury Operations | ≤ 30 min |
| 6 | Reconnect BNM RENTAS / IBG from secondary | Network + Payments | ≤ 15 min |
| 7 | Re-enable customer payment initiation | DR Commander | ≤ 10 min |
| 8 | Enhanced reconciliation monitoring | Treasury + SOC | 48 hours post-failover |

Total target: 2 hours.

## 5. Settlement integrity
**Critical:** settlement integrity > availability. Every in-flight payment must be confirmed as either settled (single time) or rejected (with customer notification). Dual-settlement (paying twice) is unacceptable.

## 6. Customer communication
- Customers with affected payments individually notified within 4 hours
- Counterparty banks notified via BNM channels (RENTAS membership) per BNM protocol
- Per [PLN-04 Crisis Comms](PLN-04-crisis-communications-plan.md)

## 7. Regulatory communication
- BNM RENTAS desk: immediate notification of any RENTAS connectivity issue
- BNM RMiT 11.18 (4-hour) for material payment-system disruption
- BNM Operational Risk Reporting Part C
- Where merchant-acquiring affected: BNM Merchant Acquiring Services PD paragraphs 19.25–19.26 (per RMiT 11.18 reference)

## 8. Shariah considerations
Payment processing logic must preserve Shariah-compliance attributes during failover (no riba calculation introduced, profit-sharing structures preserved per product). Shariah Liaison consulted at DR Commander level.

## 9. Testing
- Monthly: payment-system component failover test (sandbox)
- Quarterly: end-to-end payment failover with simulated BNM RENTAS reconnection
- Annually: full failover with executive + Shariah Liaison participation

## 10. Document control
| Version | Date | Author | Approver | Change |
|---|---|---|---|---|
| 1.0 | [Effective] | Head of IT Ops + Head of Treasury Ops | COO + CIO | Initial |
