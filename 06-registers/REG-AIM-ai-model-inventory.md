# REG-AIM — AI Model Inventory

| | |
|---|---|
| **Document ID** | REG-AIM | **Owner** | Data Science (under CDO) |
| **Cadence** | Continuous | **Parent framework** | [AIGF](../01-frameworks/AIGF.md) |

## Purpose
Technical inventory of GIBB-operated AI models — complement to [REG-AIU](REG-AIU-ai-use-case-register.md) (use cases). One use case may have multiple models; one model may serve multiple use cases.

## Schema

| Field | Description |
|---|---|
| `aim_id` | `AIM-NNNN` |
| `model_name` | |
| `model_version` | Semantic version |
| `model_type` | Per [REG-AIU](REG-AIU-ai-use-case-register.md) types |
| `framework` | TensorFlow / PyTorch / scikit-learn / vendor / etc. |
| `foundation_model_base` | If applicable |
| `model_owner_role` | Technical owner |
| `serving_use_cases` | Multi reference to [REG-AIU](REG-AIU-ai-use-case-register.md) entries |
| `training_data_refs` | Multi reference to [REG-DA](REG-DA-data-asset-register.md) |
| `training_environment` | Local / cloud / on-prem GPU cluster |
| `deployment_environment` | Production / Pilot / Sandbox |
| `inference_endpoint` | Internal endpoint reference |
| `model_card_link` | Documentation per industry practice |
| `validation_report_link` | Per [STD-AI-01](../03-standards/STD-AI-01-ai-use-case-risk-classification-standard.md) |
| `fairness_metrics` | Demographic parity / equalised odds / etc. with current values |
| `last_trained` | date |
| `next_retraining_due` | per cycle |
| `drift_status` | Stable / Drifting / Action required |
| `decommission_date` | date if retired |
| `status` | Development / Validation / Production / Suspended / Retired |

## Worked example — first entries (illustrative)

| aim_id | model | version | type | use_cases | last_trained | status |
|---|---|---|---|---|---|---|
| AIM-0001 | Retail fraud detector | 3.2 | Supervised ML ensemble | AIU-0001 | 2026-04-10 | Production |
| AIM-0002 | AML transaction-pattern model | 2.7 | Supervised ML | AIU-0002 | 2026-03-22 | Production |
| AIM-0003 | Islamic finance product recommendation | 1.4 | Supervised ML | AIU-0003 | 2026-02-15 | Production |
| AIM-0004 | Credit decisioning support | 4.1 | Supervised ML (XGBoost) | AIU-0004 | 2026-05-01 | Production |
| AIM-0005 | Customer service chatbot — LLM (vendor) | (vendor-managed) | Generative LLM | AIU-0005 | (vendor) | Production |
| AIM-0006 | Internal email summariser | (vendor LLM) | Generative LLM | AIU-0006 | (vendor) | Production |
| AIM-0007 | Code review assistant | (vendor LLM) | Generative LLM | AIU-0007 | (vendor) | Production |
| AIM-0008 | Sukuk pricing | 2.0 | Quantitative ML | AIU-0008 | 2026-01-10 | Production |
| AIM-0009 | Document classifier | 1.3 | Supervised classification | AIU-0009 | 2026-02-20 | Production |
| AIM-0010 | Customer churn prediction | 1.8 | Supervised ML | AIU-0010 | 2026-03-05 | Production |

## Maintenance
Monthly drift monitoring; quarterly fairness review; annual full re-validation for High-risk.

## Related documents
[REG-AIU](REG-AIU-ai-use-case-register.md); [REG-DA](REG-DA-data-asset-register.md); [POL-21](../02-policies/POL-21-ai-acceptable-use-policy.md); [AIGF](../01-frameworks/AIGF.md).
