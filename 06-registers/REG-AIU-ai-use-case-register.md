# REG-AIU — AI Use Case Register

| | |
|---|---|
| **Document ID** | REG-AIU |
| **Layer** | Register (Layer 6) |
| **Owner** | AI Governance Committee (operated by Head of Data Governance under CDO) |
| **Classification** | Internal |
| **Cadence** | Continuous |
| **Parent framework(s)** | [AIGF](../01-frameworks/AIGF.md) |
| **Parent policy** | [POL-21](../02-policies/POL-21-ai-acceptable-use-policy.md) |

---

## Purpose

The authoritative inventory of GIBB's AI use cases — what AI is in development, deployed, monitored, retired. Anchors AI risk classification (per EU AI Act-aligned taxonomy), human oversight evidence, validation status, and fairness monitoring.

## Schema

| Field | Type | Description |
|---|---|---|
| `aiu_id` | string | `AIU-NNNN` |
| `use_case_name` | string | Business-recognisable name |
| `business_owner_role` | role | Accountable business head |
| `model_owner` | role | Technical model owner |
| `business_line` | enum | Retail / Commercial / Corporate / Treasury / Cross-functional / Internal Operations |
| `purpose` | text | Business problem being solved |
| `risk_classification` | enum | Unacceptable / High-risk / Limited-risk / Minimal-risk (per STD-AI-01) |
| `aigc_approved` | bool | AI Governance Committee approval for High-risk |
| `model_type` | enum | Supervised ML / Unsupervised ML / Deep Learning / Generative (LLM) / Generative (non-LLM) / Reinforcement / Embedded vendor AI / Other |
| `foundation_model` | string | If based on a foundation model — name |
| `vendor_provided` | bool | Embedded in third-party product |
| `tpsp_link` | reference | If vendor — link to REG-TPS |
| `training_data_assets` | reference (multi) | REG-DA entries used as training data |
| `customer_data_used` | bool | Customer personal data used (CIMF lawful basis required) |
| `shariah_relevant` | bool | In Islamic product system or affecting Shariah-compliance logic |
| `shariah_approval` | enum | Required / Granted / Not required |
| `validation_status` | enum | Not started / In validation / Validated / Re-validation due |
| `independent_validation` | bool | Required for high-risk; if Yes — date and approver |
| `human_oversight_mechanism` | text | How human review is built into the decision loop |
| `fairness_monitoring` | enum | Continuous / Periodic / Not yet implemented |
| `last_fairness_review` | date | |
| `drift_monitoring` | bool | Active |
| `last_retrain` | date | |
| `incident_count` | int | AI-attributed incidents (REG-INC cross-reference) |
| `ncii_scope` | bool | Within NCII scope per NCIIF |
| `status` | enum | Concept / Validation / Pilot / Production / Suspended / Retired |

## Worked example — first entries (illustrative)

| aiu_id | use_case | business_line | risk_class | model_type | shariah | validation | oversight | status |
|---|---|---|---|---|---|---|---|---|
| AIU-0001 | Fraud detection — retail card transactions | Retail | High-risk | Supervised ML (ensemble) | n/a | Validated; re-validation Q3 | Human review on flagged transactions > threshold | Production |
| AIU-0002 | AML transaction monitoring | Cross-functional | High-risk | Supervised ML + rule-based | n/a | Validated | Human review on high-priority alerts | Production |
| AIU-0003 | Customer financial advice — Islamic finance product recommendation | Retail | High-risk | Supervised ML | Y (Shariah Committee approved logic) | Validated; Shariah-compliance test included | Mandatory human (Islamic finance officer) review for Highly Confidential or high-value | Production |
| AIU-0004 | Credit decisioning support — financing applications | Retail / Commercial | High-risk | Supervised ML | Y (logic Shariah-aligned for Murabahah/Musharakah) | Validated | Mandatory human review of all declines | Production |
| AIU-0005 | Customer service chatbot (generative — LLM) | Retail | Limited-risk (informational only; not decisioning) | Generative LLM | Y (Islamic finance product information) | Validated; ongoing hallucination monitoring | Escalation to human agent for any account-action request | Production |
| AIU-0006 | Internal email summarisation (productivity) | Internal Operations | Minimal-risk | Generative LLM (approved enterprise tool) | n/a | Not required at this risk level | Used only on Internal-or-below | Production |
| AIU-0007 | Code review augmentation (engineering productivity) | Internal — Engineering | Limited-risk | Generative LLM | n/a | Tool-vendor validation accepted | Mandatory human review of all suggestions before merge | Production |
| AIU-0008 | Sukuk pricing model — treasury | Treasury | High-risk | Quantitative ML | Y (Sukuk structure Shariah-aligned) | Validated; independent quant review annually | Mandatory trader review | Production |
| AIU-0009 | Document classification — operational | Internal Operations | Minimal-risk | Supervised classification | n/a | Validated | Sample QA | Production |
| AIU-0010 | Customer churn prediction | Retail | Limited-risk | Supervised ML | n/a | Validated | Informational only — feeds retention campaigns; no automated customer action | Production |

> Real entries carry full validation reports, fairness metrics, drift monitoring dashboards, named oversight roles.

## Maintenance

- New AI use case onboarding gated by entry creation and AI Governance Committee classification.
- High-risk use cases require AIGC approval before transitioning from Validation to Pilot.
- Continuous monitoring outputs (drift, fairness) update entry status.
- Material model retraining triggers re-validation.
- Annual portfolio review by AIGC; reported to RMC.
- Shariah-relevant use cases reported to Shariah Committee quarterly.

## Related documents

- **Parent framework:** [AIGF](../01-frameworks/AIGF.md)
- **Parent policy:** [POL-21](../02-policies/POL-21-ai-acceptable-use-policy.md)
- **Related registers:** [REG-AIM AI Model Inventory](REG-AIM-ai-model-inventory.md); [REG-AIV AI Vendor Register](REG-AIV-ai-vendor-register.md); [REG-AIB AI Bias and Fairness Register](REG-AIB-ai-bias-and-fairness-register.md); [REG-DA](REG-DA-data-asset-register.md) (training data); [REG-INC](REG-INC-incident-register.md) (AI-attributed incidents)
