# STD-AI-02 — AI Model Validation Standard

| | |
|---|---|
| **Document ID** | STD-AI-02 | **Version** | 1.0 |
| **Owner / Approver** | Model Risk function (under CRO) / CRO |
| **Parent policy** | [POL-21](../02-policies/POL-21-ai-acceptable-use-policy.md); POL-AI-01 AI Model Risk Management Policy (future) | **Parent framework** | [AIGF](../01-frameworks/AIGF.md) |
| **Practice** | NIST AI RMF 1.0; ISO/IEC 42001:2023 |

## 1. Purpose
Specify validation requirements for AI models before deployment and through lifecycle.

## 2. Scope
All AI models — in-house developed, vendor-procured, embedded foundation-model-based. Validation depth proportionate to risk classification per [STD-AI-01](STD-AI-01-ai-use-case-risk-classification-standard.md).

## 3. Requirements

### 3.1 Validation dimensions
| Dimension | Definition |
|---|---|
| Accuracy | Performance on validation set (and against business KPI) |
| Robustness | Performance under input perturbation, distribution shift |
| Fairness | Performance parity across customer-affecting groups (demographic, age, location, Islamic-conventional product) |
| Explainability | Model decisions explainable to required depth |
| Security | Adversarial robustness; data leakage testing; for LLM-based: prompt injection testing |
| Compliance | Aligned with applicable regulation (PDPA, MCIPD, Shariah for product-system) |

### 3.2 Required validation by risk class

| Risk class | Independence | Depth | Sign-off |
|---|---|---|---|
| Unacceptable | n/a (prohibited) | n/a | — |
| High-risk | Independent (separate from development team) | All 6 dimensions | AIGC |
| Limited-risk | Internal review (not by developer) | Accuracy + Compliance + Security | Data Science Lead |
| Minimal-risk | Self-attestation | Accuracy + Compliance | Model owner |

### 3.3 Fairness criteria
For models affecting customers:
- Demographic parity assessed across statutory protected groups under PDPA
- Equalised odds for binary classifications affecting outcomes
- Islamic-conventional product fairness — no systematic disadvantaging based on product type
- Shariah-product fairness assessed by Shariah Compliance

### 3.4 LLM / generative AI additional validation
- Hallucination rate measured on representative prompts
- Prompt injection resistance tested per published threat patterns
- Output toxicity / harm filtered
- IP / sensitive data leakage tested with canary prompts
- Bias on representative scenarios

### 3.5 Validation documentation
| Artefact | Required |
|---|---|
| Model card per industry practice | All models |
| Validation report covering dimensions per §3.2 | Per risk class |
| Fairness assessment | High-risk + Limited-risk affecting customers |
| Validation sign-off | Per §3.2 |
| Linked to [REG-AIM AI Model Inventory](../06-registers/REG-AIM-ai-model-inventory.md) | All models |

### 3.6 Re-validation triggers
| Trigger | Action |
|---|---|
| Material model retraining | Full re-validation |
| Drift detection threshold breach | Targeted re-validation + decision (retrain, retire) |
| Fairness metric degradation | Fairness-focused re-validation |
| New regulatory expectation | Re-validation per new criteria |
| Annual cycle (High-risk) | Full re-validation |

### 3.7 Suspension criteria
Model suspended pending re-validation if:
- Material incident attributable to model
- Validation finding above acceptable threshold
- Regulatory directive requiring suspension

## 4. Exceptions
Per [POL-21](../02-policies/POL-21-ai-acceptable-use-policy.md). Unacceptable-risk not exception-approvable.

## 5. Related documents
[POL-21](../02-policies/POL-21-ai-acceptable-use-policy.md); [STD-AI-01](STD-AI-01-ai-use-case-risk-classification-standard.md); STD-AI-03 GenAI Security; STD-AI-04 AI Training Data; [REG-AIU](../06-registers/REG-AIU-ai-use-case-register.md); [REG-AIM](../06-registers/REG-AIM-ai-model-inventory.md); REG-AIB AI Bias and Fairness Register (future); [AIGF](../01-frameworks/AIGF.md)

## 6. References
NIST AI RMF 1.0; NIST AI RMF GenAI Profile (July 2024); ISO/IEC 42001:2023; EU AI Act (2024) Art. 9–15 high-risk system requirements; BNM Discussion Paper on Responsible AI.

## 7. Document control
| Version | Date | Author | Approver | Change |
|---|---|---|---|---|
| 1.0 | [Effective] | Model Risk function | CRO | Initial |
