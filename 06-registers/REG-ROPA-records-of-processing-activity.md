# REG-ROPA — Records of Processing Activity

| | |
|---|---|
| **Document ID** | REG-ROPA |
| **Layer** | Register (Layer 6) |
| **Owner** | Data Protection Officer |
| **Classification** | Internal |
| **Cadence** | Continuous |
| **Parent framework(s)** | [CIMF](../01-frameworks/CIMF.md) |
| **Parent policy** | [POL-CI-01](../02-policies/POL-CI-01-customer-data-protection-policy.md) |
| **Implements** | Personal Data Protection Act 2010 record-keeping expectations; ISO/IEC 27701:2019 |

---

## Purpose

The authoritative inventory of personal-data processing activities at GIBB — the primary register for PDPA compliance and the document examined by the PDPA Commissioner. Covers what personal data is processed, why, by whom, with what lawful basis, retained for how long, and to whom disclosed.

## Schema

| Field | Type | Description |
|---|---|---|
| `ropa_id` | string | `ROPA-NNNN` |
| `processing_activity` | string | Business-recognisable name of the processing operation |
| `business_line` | enum | Retail / Commercial / Corporate / Treasury / Cross-functional |
| `data_owner_role` | role | Accountable role for this processing |
| `purpose` | text | Specific business purpose |
| `data_categories` | enum (multi) | Identifiers / Financial / Authentication / Behavioural / Sensitive / Shariah-Confidential / etc. |
| `data_subject_categories` | enum (multi) | Customer / Prospect / Employee / Contractor / Counterparty |
| `lawful_basis` | enum | Consent / Contract / Legal obligation / Vital interest / Legitimate interest / Public task |
| `consent_mechanism` | text | If consent-based: how captured, where stored, how withdrawn |
| `data_volume_indicator` | enum | < 1k / 1k–10k / 10k–100k / 100k–1M / > 1M records |
| `systems_involved` | reference (multi) | CMDB CIs |
| `internal_recipients` | text | Functions with access |
| `external_recipients` | text | TPSPs (link REG-TPS), regulators, courts |
| `cross_border_transfer` | bool | If Yes, jurisdiction(s) |
| `cross_border_safeguard` | enum | Standard contractual clauses / Binding corporate rules / Other PDPA-recognised |
| `retention_period` | text | Per retention schedule, with regulatory basis |
| `security_measures` | text | Cross-reference to CRMF and DGF |
| `dpia_required` | bool | Data Protection Impact Assessment required (high-risk processing) |
| `dpia_link` | reference | DPIA document if required |
| `shariah_review_required` | bool | Shariah Committee review applies |
| `last_review` | date | Last ROPA refresh |
| `next_review` | date | Annual or on material change |
| `status` | enum | Active / Suspended / Retired |

## Worked example — first entries (illustrative)

| ropa_id | activity | data_categories | lawful_basis | volume | cross_border | retention | status |
|---|---|---|---|---|---|---|---|
| ROPA-0001 | Customer account opening (retail) | Identifiers, Financial, Authentication | Contract + Legal obligation (AML/KYC) | 100k–1M | No | 7 years from account closure (BNM record-keeping) | Active |
| ROPA-0002 | Internet banking authentication | Authentication, Behavioural | Contract + Legitimate interest | > 1M sessions | No | 7 years (audit) | Active |
| ROPA-0003 | Marketing communications (retail) | Identifiers, Behavioural | Consent | 100k–1M | No | Until consent withdrawn or 2 years dormancy | Active |
| ROPA-0004 | AML/KYC sanctions screening | Identifiers, Behavioural | Legal obligation (AMLA) | > 1M | Yes (sanctions list providers) | 7 years post-relationship | Active |
| ROPA-0005 | Credit decisioning (financing) | Financial, Behavioural | Contract + Legitimate interest | 10k–100k | No | 7 years post-decision | Active |
| ROPA-0006 | Customer service call recording | Identifiers, Audio | Consent + Legitimate interest | > 1M | No | 90 days (default) / 7 years (regulatory/dispute) | Active |
| ROPA-0007 | Fraud detection analytics | Identifiers, Financial, Behavioural | Legitimate interest | > 1M | No | 7 years | Active |
| ROPA-0008 | Shariah Committee deliberation records | Shariah-Confidential | Legal obligation (BNM SGF) | < 1k | No | Permanent | Active |
| ROPA-0009 | Workforce HR records (employees) | Identifiers, Financial, Sensitive | Contract + Legal obligation | 1k–10k | No | Per labour law + 7 years post-termination | Active |
| ROPA-0010 | Regulatory reporting to BNM | Aggregated identifiers, Financial | Legal obligation (BNM directives) | n/a (aggregate) | No | Permanent (regulatory archive) | Active |

> Real entries carry full purpose narrative, dependencies, named contacts, DPIA documentation links.

## Maintenance

- New processing activity launches: ROPA entry mandatory before processing begins (gating control).
- Annual review per activity by data owner; DPO consolidates and reports to RMC.
- Material change (new data categories, new recipients, cross-border addition) triggers immediate update + DPIA assessment.
- PDPA Commissioner inspection: ROPA is the primary register inspected.

## Related documents

- **Parent framework:** [CIMF](../01-frameworks/CIMF.md)
- **Parent policy:** [POL-CI-01](../02-policies/POL-CI-01-customer-data-protection-policy.md); [POL-CI-02 Customer Consent and Disclosure Policy](../02-policies/POL-CI-02-customer-consent-and-disclosure-policy.md) (future)
- **Related registers:** REG-DSR Data Subject Request Register (future); REG-DIS Customer Disclosure Register (future); REG-CDB Customer Data Breach Register (future)
