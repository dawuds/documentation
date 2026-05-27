# REG-TPS — Third-Party Service Provider Register

| | |
|---|---|
| **Document ID** | REG-TPS |
| **Layer** | Register (Layer 6) |
| **Owner** | Head of Procurement + CRO |
| **Classification** | Internal |
| **Cadence** | Continuous |
| **Parent framework(s)** | [TPRMF](../01-frameworks/TPRMF.md) |
| **Parent policy** | [POL-10](../02-policies/POL-10-it-vendor-management-policy.md) |

---

## Purpose

The authoritative inventory of TPSPs at GIBB, with criticality classification, attestation status, contract lifecycle, and continuous monitoring outcomes. Primary input to RMC concentration reporting and to BNM examinations on outsourcing.

## Schema

| Field | Type | Description |
|---|---|---|
| `tpsp_id` | string | `TPS-NNNN` |
| `legal_entity` | string | TPSP legal name |
| `service_description` | text | What the TPSP provides |
| `service_type` | enum | IaaS / PaaS / SaaS / Managed Service / Software / Consultancy / Other |
| `materiality` | enum | Material / Non-material (per BNM Outsourcing PD) |
| `criticality_tier` | enum | Tier 0 / 1 / 2 / 3 (per criticality of services dependent on the TPSP) |
| `shariah_relevant` | bool | Touches Shariah-compliant product systems |
| `business_relationship_owner` | role | Named accountable role |
| `contract_start` / `contract_end` | date | |
| `renewal_decision_due` | date | 6 months before contract end for material |
| `dd_status` | enum | Initial DD completed / Last reassessment date / Overdue |
| `dd_last_date` | date | Last due diligence per RMiT 10.47 |
| `app8_rcm_coverage` | enum | Full / Partial / Not yet assessed (per RMiT Appendix 8) |
| `attestations_held` | enum (multi) | ISO 27001 / SOC 2 Type 2 / PCI DSS / ISO 22301 / etc. |
| `attestation_expiry` | date | Earliest of attestations held |
| `right_to_audit_in_contract` | bool | Per RMiT 10.46 |
| `sub_contractors_disclosed` | bool | 4th parties identified |
| `monitoring_cadence` | enum | Continuous (RMiT 10.49) / Quarterly / Annual |
| `incidents_to_date` | int | Count of TPSP-attributed incidents (link to REG-TPI) |
| `exit_plan_documented` | bool | Per POL-10 §4.5 |
| `bnm_notified` | bool | Where material outsourcing per BNM Outsourcing PD |
| `status` | enum | Onboarding / Active / Notice given / Exit in progress / Exited |

## Worked example — first entries (sanitised)

| tpsp_id | legal_entity | service | type | materiality | tier | shariah | dd_last | attestations | exit_plan | status |
|---|---|---|---|---|---|---|---|---|---|---|
| TPS-0001 | Cloud Provider A | Public cloud — IaaS + managed services | IaaS | Material | 0 | Y | 2026-02-10 | ISO 27001, SOC 2 Type 2, PCI DSS | Yes | Active |
| TPS-0002 | Cloud Provider B | Public cloud — IaaS (secondary) | IaaS | Material | 1 | Y | 2026-02-12 | ISO 27001, SOC 2 Type 2 | Yes | Active |
| TPS-0003 | Core Banking Vendor | Core banking platform support and licence | Software | Material | 0 | Y | 2026-01-25 | ISO 27001, ISO 22301 | Yes | Active |
| TPS-0004 | Managed SOC Provider | 24×7 SOC monitoring augmentation | Managed Service | Material | 0 | n/a | 2026-03-05 | ISO 27001, SOC 2 Type 2 | Yes | Active |
| TPS-0005 | CDN/WAF Provider | DDoS protection + WAF for digital channels | SaaS | Material | 0 | n/a | 2026-02-28 | ISO 27001, SOC 2 Type 2 | Yes | Active |
| TPS-0006 | HRIS Vendor (Workday) | Workforce management | SaaS | Material | 2 | n/a | 2026-01-30 | ISO 27001, SOC 2 Type 2 | Yes | Active |
| TPS-0007 | Email Security Vendor | Email gateway, anti-phishing | SaaS | Material | 1 | n/a | 2026-03-15 | ISO 27001, SOC 2 Type 2 | Yes | Active |
| TPS-0008 | Identity Provider (IDP) | Workforce identity and SSO | SaaS | Material | 0 | n/a | 2026-02-20 | ISO 27001, SOC 2 Type 2 | Yes | Active |
| TPS-0009 | Endpoint Detection & Response | EDR platform | SaaS | Material | 1 | n/a | 2026-02-25 | ISO 27001, SOC 2 Type 2 | Yes | Active |
| TPS-0010 | Shariah-Audit Advisory | External Shariah audit support | Consultancy | Non-material | 3 | Y | 2025-12-10 | n/a | Yes | Active |
| TPS-0011 | External Pen Testing | Annual pen testing per POL-18 | Consultancy | Material | 2 | n/a | 2026-04-05 | CREST attestation | Yes | Active |
| TPS-0012 | Independent External Assurance | Per RMiT Section 14 for digital service enhancements | Consultancy | Material | 2 | n/a | 2026-03-22 | ISAE 3402 SOC capability | Yes | Active |

> Real entries carry full risk assessment, last-monitoring outcome, renewal decision context, contract reference, named contacts.

## Maintenance

- New TPSP onboarding triggers entry creation; cannot go-live until entry complete (gating control).
- Material TPSP attestation review at attestation expiry; new attestation evidence linked.
- Annual concentration review by CRO: % of critical services per TPSP, identification of single-point-of-failure dependencies.
- Quarterly review by RMC of material TPSP status (active material, in onboarding, in exit).
- Shariah-relevant TPSPs reviewed by Shariah Compliance annually.

## Related documents

- **Parent framework:** [TPRMF](../01-frameworks/TPRMF.md)
- **Parent policy:** [POL-10](../02-policies/POL-10-it-vendor-management-policy.md); [POL-19](../02-policies/POL-19-supplier-security-policy.md)
- **Related register:** REG-OUT Material Outsourcing Register (future); REG-TPI TPSP Incident Register (future); [REG-INC](REG-INC-incident-register.md) (for TPSP-attributed incidents)
