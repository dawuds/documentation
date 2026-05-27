# SOP-AI-03 — AI Vendor Assessment SOP

| | |
|---|---|
| **Document ID** | SOP-AI-03 | **Version** | 1.0 |
| **Owner / Approver** | AI Governance team + TPRM team |
| **Parent policy** | [POL-21 §4.8](../02-policies/POL-21-ai-acceptable-use-policy.md); [POL-10](../02-policies/POL-10-it-vendor-management-policy.md) | **Parent framework** | [AIGF](../01-frameworks/AIGF.md); [TPRMF](../01-frameworks/TPRMF.md) |

## 1. Purpose
Assess AI vendors and embedded AI in third-party products — AI-specific addenda to baseline TPSP onboarding per [SOP-TP-01](SOP-TP-01-tpsp-onboarding-sop.md).

## 2. Trigger
- New AI vendor engagement
- AI capability addition to existing vendor product
- Vendor's AI capability material change

## 3. Procedure

| # | Actor | Action |
|---|---|---|
| 1 | Business + AI Governance | Identify AI capability scope and risk classification per [STD-AI-01](../03-standards/STD-AI-01-ai-use-case-risk-classification-standard.md) |
| 2 | TPRM team | Execute baseline TPSP onboarding per [SOP-TP-01](SOP-TP-01-tpsp-onboarding-sop.md) |
| 3 | AI Governance | AI-specific addenda: |
| 3a | AI Governance | Foundation model provenance + lineage |
| 3b | AI Governance | Training data sources + IP / copyright posture |
| 3c | AI Governance | Vendor model evaluation reports |
| 3d | AI Governance | Vendor fairness / bias attestations |
| 3e | AI Governance | Vendor data handling — does vendor use GIBB inputs for foundation model training? Contractual prohibition unless explicit consent |
| 3f | AI Governance | Vendor security testing of AI capability — prompt injection, adversarial robustness |
| 3g | AI Governance | Vendor IP indemnification for generative outputs (where customer-facing) |
| 4 | CISO | AI security review per [STD-AI-03](../03-standards/STD-AI-03-genai-security-standard.md) |
| 5 | Shariah Compliance (if product-system relevant) | Shariah review |
| 6 | AIGC | Approve AI capability use; record risk classification |
| 7 | TPRM team | Update [REG-TPS](../06-registers/REG-TPS-third-party-service-provider-register.md) with AI-vendor flag |
| 8 | AI Governance | Register in REG-AIV AI Vendor Register; link to [REG-AIU](../06-registers/REG-AIU-ai-use-case-register.md) and (if vendor model) [REG-AIM](../06-registers/REG-AIM-ai-model-inventory.md) |

## 4. Periodic reassessment
Per AI vendor tier (Tier 0/1 annual; Tier 2 bi-annual). Per [SOP-TP-02](SOP-TP-02-tpsp-periodic-reassessment-sop.md) with AI-addenda.

## 5. Evidence
TPSP onboarding evidence; AI-specific addenda evidence; AIGC approval; REG-TPS, REG-AIV, REG-AIU, REG-AIM updates. Retained 7 years.

## 6. Document control
| Version | Date | Author | Approver | Change |
|---|---|---|---|---|
| 1.0 | [Effective] | AI Governance + TPRM team | AIGC | Initial |
