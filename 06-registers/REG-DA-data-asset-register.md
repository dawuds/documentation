# REG-DA — Data Asset Register

| | |
|---|---|
| **Document ID** | REG-DA |
| **Layer** | Register (Layer 6) |
| **Owner** | Chief Data Officer (Head of Data Governance operates) |
| **Classification** | Internal |
| **Cadence** | Continuous |
| **Parent framework(s)** | [DGF](../01-frameworks/DGF.md) |
| **Parent policy** | [POL-11](../02-policies/POL-11-data-classification-policy.md) |
| **Implements** | RMiT Section 11.3(h) (centralised automated technology asset inventory — data-asset subset) |

---

## Purpose

The authoritative inventory of GIBB's data assets — what data exists, where it lives, who owns it, how it is classified, how it flows. Foundational to DGF, CIMF, AIGF, and to every downstream control (security, retention, disclosure, AI training).

## Schema

| Field | Type | Description |
|---|---|---|
| `da_id` | string | `DA-NNNN` |
| `asset_name` | string | Business-recognisable name |
| `domain` | enum | Customer / Product / Transaction / Reference / Master / Analytical / AI Training / Regulatory Reporting / Shariah / HR / Other |
| `business_owner_role` | role | Accountable data owner |
| `data_steward` | role | Day-to-day steward |
| `classification` | enum | Public / Internal / Confidential / Highly Restricted / Shariah-Confidential |
| `personal_data` | bool | PDPA scope |
| `shariah_relevant` | bool | Touches Shariah-compliant product or Shariah Committee material |
| `storage_systems` | reference (multi) | CMDB CIs (databases, data lakes, file shares, cloud storage) |
| `consuming_systems` | reference (multi) | CMDB CIs that read this asset |
| `producing_systems` | reference (multi) | CMDB CIs that write this asset |
| `lineage_documented` | bool | Material flows documented |
| `retention_period` | text | Per retention schedule + regulatory basis |
| `quality_dimensions_measured` | enum (multi) | Accuracy / Completeness / Consistency / Timeliness / Validity / Uniqueness |
| `last_quality_assessment` | date | |
| `quality_score` | text | % or qualitative |
| `ropa_link` | reference | If personal data — link to REG-ROPA entry |
| `ai_training_use` | bool | Used for AI training per AIGF |
| `cross_border_flow` | bool | Resides or flows outside Malaysia |
| `last_review` | date | |
| `next_review` | date | |
| `status` | enum | Active / Sunset / Archived |

## Worked example — first entries (illustrative)

| da_id | asset_name | domain | classification | personal | shariah | quality | retention | status |
|---|---|---|---|---|---|---|---|---|
| DA-0001 | Customer master | Customer / Master | Confidential | Y | Y (Islamic customers) | 99.2% accuracy | 7 yrs post-closure | Active |
| DA-0002 | Account transactions — retail | Transaction | Confidential | Y | Y | 99.9% | 7 yrs | Active |
| DA-0003 | Customer authentication credentials | Customer / Authentication | Highly Restricted | Y | n/a | n/a (hashed) | 7 yrs post-change | Active |
| DA-0004 | Product catalogue — Islamic finance products | Product / Reference | Internal | N | Y | 100% | Permanent | Active |
| DA-0005 | Shariah Committee deliberation records | Shariah | Shariah-Confidential | (Limited PII) | Y | n/a | Permanent | Active |
| DA-0006 | AML/KYC screening records | Customer / Regulatory | Confidential | Y | n/a | 99.5% | 7 yrs post-relationship | Active |
| DA-0007 | Fraud detection model training data | AI Training | Confidential (de-identified for training) | (Source was personal; de-identified) | n/a | 97% (validation set) | Per AIGF retention | Active |
| DA-0008 | Regulatory reporting — BNM submissions | Regulatory Reporting | Internal (aggregate) | N | n/a | 100% (gating) | Permanent | Active |
| DA-0009 | Workforce HR records | HR | Sensitive (Highly Restricted subset) | Y | n/a | 99% | Per labour law + 7 yrs | Active |
| DA-0010 | Reference data — country / currency / sukuk type codes | Reference | Internal | N | Y (some) | 100% | Permanent | Active |
| DA-0011 | Internet banking session logs | Behavioural | Internal | Y (linkable) | n/a | n/a | 7 yrs | Active |
| DA-0012 | Sukuk holdings — treasury | Product / Transaction | Confidential | (Counterparty PII) | Y | 99.9% | 7 yrs post-maturity | Active |

> Real entries carry full lineage diagrams, quality measurement detail, named consuming systems, dependency maps.

## Maintenance

- New data assets registered before production processing begins (gating control).
- Quarterly data steward review per domain.
- Annual full Quality Assessment per asset; results tracked in [REG-DQ Data Quality Register](REG-DQ-data-quality-register.md).
- Material lineage change triggers update.
- Asset retirement: status transitions Active → Sunset → Archived; retained for retention period then destroyed.

## Related documents

- **Parent framework:** [DGF](../01-frameworks/DGF.md)
- **Parent policy:** [POL-11](../02-policies/POL-11-data-classification-policy.md)
- **Related registers:** [REG-DQ Data Quality Register](REG-DQ-data-quality-register.md); [REG-DL Data Lineage Register](REG-DL-data-lineage-register.md); [REG-MD Master Data Register](REG-MD-master-data-register.md); [REG-ROPA](REG-ROPA-records-of-processing-activity.md) (for personal-data subset)
