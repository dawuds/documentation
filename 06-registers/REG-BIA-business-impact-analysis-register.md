# REG-BIA — Business Impact Analysis Register

| | |
|---|---|
| **Document ID** | REG-BIA |
| **Layer** | Register (Layer 6) |
| **Owner** | Head of Business Continuity (under COO) |
| **Classification** | Internal |
| **Cadence** | Annual review per service; on material change immediately |
| **Parent framework(s)** | [BCMF](../01-frameworks/BCMF.md) |
| **Parent policy** | [POL-14](../02-policies/POL-14-business-continuity-policy.md) |
| **Source procedure** | SOP-BC-01 BIA Methodology SOP (future) |

---

## Purpose

The authoritative record of critical business services, their dependencies, and their impact tolerances (MTPD, RTO, RPO). The primary input to BCMF strategy, DRP design, and continuity testing. Reviewed by RMC annually and consulted by Internal Audit, BNM, and NACSA examinations.

## Schema

| Field | Type | Description |
|---|---|---|
| `service_id` | string | `SVC-NNN` — unique service identifier |
| `service_name` | string | Business-recognisable service name |
| `business_line` | enum | Retail / Commercial / Corporate / Treasury / Cross-functional |
| `service_owner_role` | role | Accountable business head |
| `criticality_tier` | enum | Tier 0 (mission-critical) / Tier 1 (critical) / Tier 2 (important) / Tier 3 (non-critical) |
| `customer_facing` | bool | Direct customer-facing service |
| `shariah_compliant_service` | bool | Islamic-finance product service |
| `mtpd_hours` | int | Maximum Tolerable Period of Disruption |
| `rto_hours` | int | Recovery Time Objective |
| `rpo_minutes` | int | Recovery Point Objective |
| `peak_demand_period` | text | Periods of elevated demand (e.g., payroll dates, festive seasons) |
| `key_dependencies_systems` | reference (multi) | Critical systems supporting the service (CMDB CIs) |
| `key_dependencies_data` | reference (multi) | Critical data assets |
| `key_dependencies_suppliers` | reference (multi) | Critical TPSPs per TPRMF (REG-TPS link) |
| `key_dependencies_people` | text | Critical roles and skill dependencies |
| `recovery_strategy` | text | Continuity approach (alternate site, alternate supplier, manual workaround, technology failover) |
| `drp_reference` | reference | PLN-03-x Disaster Recovery Plan ID |
| `last_test_date` | date | Most recent test |
| `last_test_outcome` | enum | Pass / Pass with findings / Fail |
| `next_test_due` | date | Per testing programme |
| `last_bia_review` | date | Last BIA refresh |
| `next_bia_review` | date | Annual unless triggered earlier |
| `status` | enum | Active / Under change / Decommissioning |

## Tier criteria

| Tier | Definition | Typical MTPD | Typical RTO | Typical RPO |
|---|---|---|---|---|
| Tier 0 | Mission-critical; failure has direct material customer or regulatory impact | ≤ 4 hours | ≤ 2 hours | ≤ 5 minutes |
| Tier 1 | Critical; failure materially affects customer experience or operational capability | ≤ 24 hours | ≤ 8 hours | ≤ 30 minutes |
| Tier 2 | Important; failure causes customer inconvenience or operational degradation | ≤ 72 hours | ≤ 24 hours | ≤ 4 hours |
| Tier 3 | Non-critical; failure can be tolerated for an extended period | > 72 hours | > 24 hours | > 4 hours |

## Worked example — first entries (illustrative)

| service_id | service_name | business_line | tier | shariah | MTPD | RTO | RPO | last_test | outcome |
|---|---|---|---|---|---|---|---|---|---|
| SVC-001 | Internet Banking — retail | Retail | 0 | Y (Islamic) | 2 h | 1 h | 1 min | 2026-04-15 | Pass |
| SVC-002 | Mobile Banking — retail | Retail | 0 | Y (Islamic) | 2 h | 1 h | 1 min | 2026-04-15 | Pass |
| SVC-003 | Core Banking — deposits | Cross-functional | 0 | Y (Islamic) | 2 h | 1 h | 0 (synchronous replication) | 2026-03-10 | Pass with findings (failback time exceeded target by 12 min) |
| SVC-004 | Core Banking — financing (Murabahah, Musharakah) | Cross-functional | 0 | Y (Islamic) | 4 h | 2 h | 1 min | 2026-03-10 | Pass |
| SVC-005 | Payments — RENTAS / IBG | Treasury | 0 | Y (Islamic) | 4 h | 2 h | 1 min | 2026-05-02 | Pass |
| SVC-006 | ATM network | Retail | 1 | Y (Islamic) | 24 h | 4 h | 15 min | 2026-02-20 | Pass |
| SVC-007 | Branch Teller System | Retail | 1 | Y (Islamic) | 24 h | 8 h | 30 min | 2026-02-20 | Pass |
| SVC-008 | Call Centre IVR + agent platform | Cross-functional | 1 | n/a | 24 h | 8 h | 1 h | 2026-01-30 | Pass |
| SVC-009 | Treasury — Sukuk trading | Treasury | 1 | Y (Islamic) | 24 h | 8 h | 30 min | 2026-04-22 | Pass |
| SVC-010 | Regulatory reporting (BNM submissions) | Cross-functional | 1 | n/a | 24 h | 8 h | 1 h | 2026-03-15 | Pass |
| SVC-011 | Internal HR system (Workday) | Cross-functional | 2 | n/a | 72 h | 24 h | 4 h | 2026-01-15 | Pass |
| SVC-012 | Email and collaboration | Cross-functional | 2 | n/a | 72 h | 24 h | 4 h | 2026-01-15 | Pass |
| SVC-013 | Document management | Cross-functional | 3 | n/a | > 72 h | > 24 h | > 4 h | n/a | n/a (not tier-critical) |

> Real entries carry full dependency maps, recovery strategy detail, named contacts, last review notes. Worked example shows the shape.

## Maintenance

- Service owners review their BIA entries annually; material change triggers immediate update.
- BC function reconciles BIA against actual service performance metrics quarterly.
- New services on launch: BIA entry mandatory before production go-live (gating control in [POL-07 Change Management](../02-policies/POL-07-change-management-policy.md)).
- Decommissioning of a service: BIA entry status changes to `Decommissioning`, then `Decommissioned` (retained for audit traceability).
- Shariah-compliant service BIA entries reviewed by Shariah Compliance for continuity-strategy Shariah implications.

## Related documents

- **Parent framework:** [BCMF](../01-frameworks/BCMF.md)
- **Parent policy:** [POL-14](../02-policies/POL-14-business-continuity-policy.md)
- **Related plan:** [PLN-02 Business Continuity Plan](../05-plans/PLN-02-business-continuity-plan.md)
- **Related register:** REG-BCT BC Test Outcomes Register (future)
