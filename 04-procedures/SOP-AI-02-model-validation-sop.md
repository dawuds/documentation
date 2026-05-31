# SOP-AI-02 — AI Model Validation SOP

| | |
|---|---|
| **Document ID** | SOP-AI-02 | **Version** | 1.0 |
| **Owner / Approver** | Model Risk function (under CRO) |
| **Parent standard** | [STD-AI-02](../03-standards/STD-AI-02-ai-model-validation-standard.md) | **Parent policy** | [POL-21](../02-policies/POL-21-ai-acceptable-use-policy.md) |

## 1. Purpose
Operationalise model validation per risk class per [STD-AI-02 Section 3.2](../03-standards/STD-AI-02-ai-model-validation-standard.md).

## 2. Trigger
- New model pre-deployment
- Re-validation cycle (per [STD-AI-02 Section 3.6](../03-standards/STD-AI-02-ai-model-validation-standard.md))
- Drift detection breach
- Incident triggering re-validation
- Annual cycle for High-risk

## 3. Procedure — High-risk validation

| # | Actor | Action |
|---|---|---|
| 1 | Model owner | Submit model for validation with: model artefacts, training documentation, model card |
| 2 | Independent Validator (Model Risk; separate from development) | Confirm independence; engage |
| 3 | Validator | Test accuracy against validation set + business KPI |
| 4 | Validator | Test robustness — distribution shift, input perturbation |
| 5 | Validator | Test fairness across protected groups + Islamic-conventional product mix |
| 6 | Validator | Test explainability per use case requirement |
| 7 | Validator | Test security — adversarial inputs; for LLM: prompt injection per [STD-AI-03 Section 3.2](../03-standards/STD-AI-03-genai-security-standard.md) |
| 8 | Validator | Test compliance — PDPA, MCIPD, Shariah (if relevant) |
| 9 | Validator | Document findings; assign Pass / Conditional Pass / Fail |
| 10 | AIGC | Review validation report; approve for pilot / production |
| 11 | Model owner | Address conditions before deployment |
| 12 | Model Risk | Update [REG-AIM](../06-registers/REG-AIM-ai-model-inventory.md) and [REG-AIB AI Bias and Fairness Register](../06-registers/REG-AIB-ai-bias-and-fairness-register.md) |

## 4. Procedure — Limited-risk validation
Per [STD-AI-02 Section 3.2](../03-standards/STD-AI-02-ai-model-validation-standard.md): accuracy + compliance + security tested; Data Science Lead sign-off (not independent validator); validation report retained.

## 5. Procedure — re-validation
On retrain, drift, or annual cycle: triggered by Data Science Lead; validation depth per current risk class; updated REG-AIM and REG-AIB.

## 6. Evidence
Validation report; test results; fairness assessment; sign-offs; REG-AIM + REG-AIB entries. Permanent for High-risk.

## 7. Document control
| Version | Date | Author | Approver | Change |
|---|---|---|---|---|
| 1.0 | [Effective] | Model Risk function | CRO | Initial |
