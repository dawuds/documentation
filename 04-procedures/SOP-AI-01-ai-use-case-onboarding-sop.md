# SOP-AI-01 — AI Use Case Onboarding SOP

| | |
|---|---|
| **Document ID** | SOP-AI-01 | **Version** | 1.0 |
| **Owner / Approver** | AI Governance Committee (operated by Head of Data Governance) |
| **Parent standard** | [STD-AI-01](../03-standards/STD-AI-01-ai-use-case-risk-classification-standard.md) | **Parent policy** | [POL-21](../02-policies/POL-21-ai-acceptable-use-policy.md) |

## 1. Purpose
Operationalise AI use case onboarding — from idea through risk classification, validation, deployment, and continuous monitoring entry.

## 2. Trigger
Business proposal for new AI use case (in-house, vendor-procured, or generative AI deployment).

## 3. Procedure

### Phase 1 — Proposal and classification

| # | Actor | Action | Output |
|---|---|---|---|
| 1 | Business owner | Submit AI use case proposal — problem, expected outcome, data, model approach | Proposal |
| 2 | AI Governance team | Initial risk classification per [STD-AI-01](../03-standards/STD-AI-01-ai-use-case-risk-classification-standard.md) | Initial classification |
| 3 | AI Governance Committee (cross-functional: CDO, CISO, CRO, CCO, Shariah Compliance if relevant, business head) | Review and confirm classification; reject if Unacceptable | Confirmed classification recorded in [REG-AIU](../06-registers/REG-AIU-ai-use-case-register.md) |

### Phase 2 — Design (Limited and High-risk only)

| # | Actor | Action | Output |
|---|---|---|---|
| 4 | Business + Data Science | Use case design — model approach, training data sources, fairness considerations, explainability | Design document |
| 5 | CDO + DGF | Training data review per [DGF](../01-frameworks/DGF.md) and [POL-11](../02-policies/POL-11-data-classification-policy.md); customer data → CIMF check | Training data approval |
| 6 | CISO | AI security threat model — adversarial inputs, model poisoning, prompt injection for LLM-based, data leakage | Threat model |
| 7 | Shariah Committee Secretariat | Shariah triage — determines whether the use case is **Shariah-touching** (any one of: affects a Shariah-compliant product / contract; consumes or generates Shariah-confidential data; surfaces output to customer-facing Islamic-banking channels; influences a Shariah-judgement workflow). Shariah-not-touching cases proceed to Step 8 with documented basis. | Triage record |
| 7a | Shariah Committee (formal sitting) | **For Shariah-touching use cases — formal Shariah Committee deliberation and approval is required before any production deployment.** The Committee may: approve, approve with conditions, defer for more information, or reject. The Secretariat prepares a Shariah submission pack (purpose, model approach, data sources, customer surface, risk profile, intended product). | Shariah Committee decision minute |
| 7b | AI Governance Committee | Records Shariah Committee decision in [REG-AIU](../06-registers/REG-AIU-ai-use-case-register.md) with `shariah_decision`, `shariah_decision_date`, `shariah_conditions` fields. Rejected use cases are closed; approved-with-conditions cases proceed only after the conditions are met and re-verified by the Secretariat. | REG-AIU updated; conditions tracked in [REG-CAP](../06-registers/REG-CAP-corrective-action-register.md) |

### Phase 3 — Build and validate

| # | Actor | Action | Output |
|---|---|---|---|
| 8 | Data Science / Model Owner | Build model | Model artifacts |
| 9 | Model Risk function (independent — for High-risk) | Independent validation — accuracy, fairness, robustness, security | Validation report |
| 10 | AIGC | Approve for pilot | Pilot approval |

### Phase 4 — Deploy

| # | Actor | Action | Output |
|---|---|---|---|
| 11 | Data Science + IT | Production deployment with human oversight controls active (for High-risk) | Deployment |
| 12 | AI Governance | Update [REG-AIU](../06-registers/REG-AIU-ai-use-case-register.md) to Production | REG-AIU updated |

### Phase 5 — Monitor

| # | Actor | Action | Output |
|---|---|---|---|
| 13 | Data Science | Continuous monitoring — drift, fairness, security (per [POL-21 Section 4.7](../02-policies/POL-21-ai-acceptable-use-policy.md)) | Monitoring dashboard |
| 14 | AI Governance | Periodic review; retraining triggers; incident correlation | Review records |

## 4. Exception handling
Unacceptable-risk classification: rejected with explanation; cannot be exception-approved. Other AIGC decisions: per AIGC procedure with CRO escalation.

## 5. Evidence
Proposal; classification record; design; training data approval; threat model; validation report; AIGC approvals; deployment record; monitoring evidence. Retained per AIGF.

## 6. Document control
| Version | Date | Author | Approver | Change |
|---|---|---|---|---|
| 1.0 | [Effective] | AI Governance | AIGC | Initial |
