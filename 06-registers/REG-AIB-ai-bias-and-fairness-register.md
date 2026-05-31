# REG-AIB — AI Bias and Fairness Register

| | |
|---|---|
| **Document ID** | REG-AIB | **Owner** | AI Governance |
| **Cadence** | Continuous (per measurement) | **Parent framework** | [AIGF](../01-frameworks/AIGF.md) |
| **Parent standard** | [STD-AI-02 Section 3.3](../03-standards/STD-AI-02-ai-model-validation-standard.md) |

## Purpose
Authoritative record of fairness measurements across GIBB AI use cases — demographic parity, equalised odds, Islamic-conventional product fairness, with material findings and remediations.

## Schema
| Field | Description |
|---|---|
| `aib_id` | `AIB-YYYY-NNN` |
| `model_id` | Link to [REG-AIM](REG-AIM-ai-model-inventory.md) |
| `use_case_id` | Link to [REG-AIU](REG-AIU-ai-use-case-register.md) |
| `measurement_date` | |
| `measurement_type` | Pre-deployment validation / Continuous monitoring / Re-validation / Incident-triggered |
| `protected_groups_assessed` | Demographic / Geographic / Age / Islamic-conventional product mix / etc. |
| `fairness_metric_used` | Demographic parity / Equalised odds / Disparate impact / Custom |
| `metric_value` | Numerical |
| `acceptable_threshold` | Set per use case |
| `pass_fail` | |
| `material_finding` | If fail — description |
| `remediation_action` | Resampling / Augmentation / Data exclusion / Model retraining / Use case re-scoping |
| `shariah_consultation` | If Islamic product system involved |
| `dpo_consulted` | If protected groups involve personal data |
| `aigc_reviewed` | bool |
| `status` | Open finding / In remediation / Closed |

## Worked example
| aib_id | model | use_case | groups | metric | pass | finding | status |
|---|---|---|---|---|---|---|---|
| AIB-2026-001 | AIM-0004 Credit decisioning | AIU-0004 | Demographic + product mix | Demographic parity | Pass | None | Closed |
| AIB-2026-002 | AIM-0003 Islamic product recommendation | AIU-0003 | Customer demographic | Disparate impact | Pass | None | Closed |
| AIB-2026-003 | AIM-0010 Customer churn prediction | AIU-0010 | Geographic | Equalised odds | Pass with note | Minor regional variance, within threshold | Closed |
| AIB-2026-004 | AIM-0001 Fraud detector | AIU-0001 | Customer segment | Disparate impact | Pass | None | Closed |

## Related documents
[POL-21](../02-policies/POL-21-ai-acceptable-use-policy.md); [STD-AI-01](../03-standards/STD-AI-01-ai-use-case-risk-classification-standard.md); [STD-AI-02](../03-standards/STD-AI-02-ai-model-validation-standard.md); [REG-AIU](REG-AIU-ai-use-case-register.md); [REG-AIM](REG-AIM-ai-model-inventory.md)
