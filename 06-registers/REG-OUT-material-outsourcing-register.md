# REG-OUT — Material Outsourcing Register

| | |
|---|---|
| **Document ID** | REG-OUT | **Owner** | Head of Procurement + CCO |
| **Classification** | Internal | **Cadence** | Continuous |
| **Parent framework** | [TPRMF](../01-frameworks/TPRMF.md) |
| **Implements** | BNM Outsourcing Policy Document notification + register obligations |

## Purpose
Subset of [REG-TPS](REG-TPS-third-party-service-provider-register.md) — material outsourcing arrangements per BNM Outsourcing PD definition, with BNM notification status and ongoing regulatory engagement. Primary register examined by BNM in outsourcing reviews.

## Schema

| Field | Description |
|---|---|
| `out_id` | `OUT-YYYY-NNN` |
| `tpsp_id` | Link to [REG-TPS](REG-TPS-third-party-service-provider-register.md) |
| `arrangement_name` | Outsourced function / service |
| `materiality_basis` | Why classified material per BNM Outsourcing PD definition |
| `business_lines_affected` | Multi |
| `contract_value_annual` | MYR (sensitivity-aware) |
| `bnm_notification_required` | bool |
| `bnm_notification_date` | date |
| `bnm_acknowledgement` | bool + date |
| `bnm_approval_required` | bool (per Outsourcing PD subset) |
| `bnm_approval_date` | date |
| `right_to_audit_clause` | Yes / No / Partial |
| `bnm_right_to_audit_clause` | Yes / No |
| `intra_group` | bool |
| `cross_border` | bool + jurisdictions |
| `sub_outsourcing_disclosed` | bool |
| `bcp_attestation` | Yes / No |
| `iso_27001_attestation` | Yes / No |
| `last_bnm_examination` | date |
| `last_internal_audit` | date |
| `shariah_relevant` | bool |
| `shariah_committee_approval` | bool + date |
| `exit_plan_documented` | bool |
| `exit_plan_tested` | bool + date |
| `status` | Active / Notice given / Exit in progress / Exited |

## Worked example — first entries (illustrative)

| out_id | tpsp_id | arrangement | basis | bnm_notified | r2a | shariah | exit_plan_tested | status |
|---|---|---|---|---|---|---|---|---|
| OUT-2026-001 | TPS-0001 | Production IaaS (compute, storage, network) | Tier 0; material per BNM | Yes (2024-08-15) | Yes | Yes (Shariah-aligned product workloads) | Yes (2026-04-15 functional test) | Active |
| OUT-2026-002 | TPS-0003 | Core banking platform support + licence | Tier 0; core operational dependency | Yes (long-standing) | Yes | Yes | Yes (2026-03-10) | Active |
| OUT-2026-003 | TPS-0004 | Managed SOC monitoring (24×7) | Tier 0; cyber detection capability | Yes (2025-02-20) | Yes | n/a | Yes (2026-01-30 — alternate provider stood up) | Active |
| OUT-2026-004 | TPS-0006 | HRIS (Workday) | Tier 2; material per data scope | Yes (notification basis) | Yes | n/a | Yes (2025-11) | Active |
| OUT-2026-005 | TPS-0010 | External Shariah audit advisory | Non-material in BNM Outsourcing PD sense; included here for Shariah Committee visibility | n/a | Yes | Yes (Shariah Committee primary) | n/a | Active |

## Maintenance

- New material outsourcing creates entry pre-contract-signing.
- BNM notification status tracked through to acknowledgement.
- Quarterly Procurement + CCO joint review.
- Annual concentration analysis per [POL-03 Section 4.2](../02-policies/POL-03-technology-risk-appetite-statement.md).
- BNM examination access via this register.

## Related documents
[POL-10](../02-policies/POL-10-it-vendor-management-policy.md); [REG-TPS](REG-TPS-third-party-service-provider-register.md); [TPRMF](../01-frameworks/TPRMF.md); BNM Outsourcing PD.
