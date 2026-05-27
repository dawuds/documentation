# REG-AIV — AI Vendor Register

| | |
|---|---|
| **Document ID** | REG-AIV | **Owner** | AI Governance + TPRM |
| **Cadence** | Continuous | **Parent framework** | [AIGF](../01-frameworks/AIGF.md); [TPRMF](../01-frameworks/TPRMF.md) |
| **Source procedure** | [SOP-AI-03](../04-procedures/SOP-AI-03-ai-vendor-assessment-sop.md) |

## Purpose
Subset of [REG-TPS](REG-TPS-third-party-service-provider-register.md) — vendors providing AI capability to GIBB, with AI-specific risk attributes.

## Schema
| Field | Description |
|---|---|
| `aiv_id` | `AIV-NNN` |
| `tpsp_id` | Link to [REG-TPS](REG-TPS-third-party-service-provider-register.md) |
| `vendor` | Vendor name |
| `ai_capability` | What AI service is provided |
| `foundation_model_basis` | If GenAI / LLM — which foundation model |
| `vendor_uses_gibb_input_for_training` | bool — contractually prohibited per [SOP-AI-03 §3e](../04-procedures/SOP-AI-03-ai-vendor-assessment-sop.md) |
| `vendor_security_attestation` | ISO 27001 / SOC 2 / specific AI security cert |
| `vendor_fairness_attestation` | bool + evidence |
| `vendor_ip_indemnification` | Customer-facing GenAI output IP cover |
| `risk_classification` | Per [STD-AI-01](../03-standards/STD-AI-01-ai-use-case-risk-classification-standard.md) |
| `serving_use_cases` | Multi link to [REG-AIU](REG-AIU-ai-use-case-register.md) |
| `serving_models` | Multi link to [REG-AIM](REG-AIM-ai-model-inventory.md) |
| `last_assessment` | date |
| `next_assessment` | per tier cadence |
| `status` | Active / Notice / Exited |

## Worked example
| aiv_id | vendor | capability | uses_gibb_training | risk | status |
|---|---|---|---|---|---|
| AIV-001 | Customer service chatbot LLM vendor | Conversational AI for product info | No (contractual prohibition) | Limited-risk | Active |
| AIV-002 | Foundation model API provider | API access for internal productivity LLM use | No | Limited-risk | Active |
| AIV-003 | Fraud detection ML vendor (TPS-0004 cross-link) | Embedded ML in managed SOC platform | No | High-risk (cyber detection — but informational, not autonomous) | Active |
| AIV-004 | Code review LLM vendor | Engineering productivity | No | Limited-risk | Active |

## Related documents
[POL-21](../02-policies/POL-21-ai-acceptable-use-policy.md); [SOP-AI-03](../04-procedures/SOP-AI-03-ai-vendor-assessment-sop.md); [REG-TPS](REG-TPS-third-party-service-provider-register.md); [REG-AIU](REG-AIU-ai-use-case-register.md); [REG-AIM](REG-AIM-ai-model-inventory.md)
