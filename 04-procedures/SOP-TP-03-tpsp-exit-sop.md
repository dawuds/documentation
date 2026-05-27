# SOP-TP-03 — TPSP Exit SOP

| | |
|---|---|
| **Document ID** | SOP-TP-03 | **Version** | 1.0 |
| **Owner / Approver** | Head of Procurement + CRO |
| **Parent standard** | [STD-TP-02](../03-standards/STD-TP-02-outsourcing-contractual-security-standard.md) | **Parent policy** | [POL-10](../02-policies/POL-10-it-vendor-management-policy.md) |

## 1. Purpose
Operationalise TPSP exit — planned end-of-contract, unplanned (TPSP failure / regulatory direction), or replacement transition.

## 2. Trigger
- Planned: contract end approaching; non-renewal decision
- Unplanned: TPSP material failure; regulatory direction; risk-driven decision
- Replacement: alternate TPSP being onboarded

## 3. Procedure

### Phase 1 — Decision and notification
| # | Actor | Action |
|---|---|---|
| 1 | Business relationship owner + Procurement | Confirm exit decision and timeline |
| 2 | CRO (Tier 0) / CISO (Tier 1) / Head of Procurement (Tier 2/3) | Approve exit |
| 3 | Procurement + Legal | Notify TPSP per contract notice requirements |
| 4 | CCO | If material outsourcing — BNM notification per BNM Outsourcing PD |
| 5 | TPRM team | Update [REG-TPS](../06-registers/REG-TPS-third-party-service-provider-register.md) status to "Notice given" |

### Phase 2 — Transition planning
| # | Actor | Action |
|---|---|---|
| 6 | Business + IT | Identify alternate provider or insourcing approach |
| 7 | Business + TPRM team | Develop transition plan with milestones |
| 8 | Procurement | Negotiate transition assistance per contract |

### Phase 3 — Data return / destruction
| # | Actor | Action |
|---|---|---|
| 9 | TPRM team + DPO + CISO | Confirm data scope held by TPSP |
| 10 | TPRM team | Receive return of GIBB data in agreed format |
| 11 | DPO | Verify data return completeness |
| 12 | CISO | Verify data destruction at TPSP per contract; obtain certificate of destruction |

### Phase 4 — Knowledge transfer
| # | Actor | Action |
|---|---|---|
| 13 | TPSP + GIBB (or alternate TPSP) | Knowledge transfer per documented transition plan |
| 14 | Business + IT | Validate alternate provider / insourced capability |

### Phase 5 — Cutover
| # | Actor | Action |
|---|---|---|
| 15 | IT + Business | Cutover to alternate; deactivate TPSP access |
| 16 | CISO | Verify all TPSP access revoked across systems |
| 17 | Procurement | Final contractual exit; closure of any payment obligations |

### Phase 6 — Closure
| # | Actor | Action |
|---|---|---|
| 18 | TPRM team | Update [REG-TPS](../06-registers/REG-TPS-third-party-service-provider-register.md) status to "Exited" |
| 19 | TPRM team | Lessons captured for future TPSP onboarding |
| 20 | CCO | Notify BNM of exit completion (where material) |

## 4. Unplanned-exit special handling
TPSP failure or regulatory-mandated exit may require BCP activation per [PLN-02](../05-plans/PLN-02-business-continuity-plan.md) to maintain service continuity during compressed transition.

## 5. Evidence
Exit decision; notifications; transition plan; data return / destruction certificates; knowledge-transfer record; cutover validation; final REG-TPS entry. Retained 7 years.

## 6. Document control
| Version | Date | Author | Approver | Change |
|---|---|---|---|---|
| 1.0 | [Effective] | Head of Procurement + CRO | Head of Procurement | Initial |
