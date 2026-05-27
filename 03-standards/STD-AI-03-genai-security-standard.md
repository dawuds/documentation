# STD-AI-03 — Generative AI Security Standard

| | |
|---|---|
| **Document ID** | STD-AI-03 | **Version** | 1.0 |
| **Owner / Approver** | CISO + Data Science / CISO |
| **Parent policy** | [POL-21](../02-policies/POL-21-ai-acceptable-use-policy.md) | **Parent framework** | [AIGF](../01-frameworks/AIGF.md); [CRMF](../01-frameworks/CRMF.md) |
| **Practice** | NIST AI RMF Generative AI Profile (July 2024); OWASP Top 10 for LLMs |

## 1. Purpose
Specify security controls for generative AI use at GIBB — LLM-based applications, agentic AI, foundation-model-based services.

## 2. Scope
All generative AI use cases — in-house deployed, vendor SaaS, foundation-model-API-consumed. Both customer-facing and internal.

## 3. Requirements

### 3.1 Approved tool catalogue
| Ref | Requirement |
|---|---|
| 3.1.1 | Only generative AI tools approved per GIBB AI tool catalogue may be used for work involving bank information |
| 3.1.2 | Data classification thresholds per tool documented in catalogue |
| 3.1.3 | Confidential or higher data may only be entered into tools explicitly approved for that classification |

### 3.2 Prompt injection defence
| Ref | Requirement |
|---|---|
| 3.2.1 | Inputs treated as untrusted; no direct execution of user-provided text as system instruction |
| 3.2.2 | System prompts separated from user content; clear delimiter |
| 3.2.3 | Output validation before action — no automatic execution of model output as code or as system command without human review |
| 3.2.4 | Prompt injection testing per [STD-AI-02 §3.4](STD-AI-02-ai-model-validation-standard.md) before deployment |

### 3.3 Data exfiltration controls
| Ref | Requirement |
|---|---|
| 3.3.1 | DLP rules applied to outbound generative-AI tool traffic where tools are externally hosted |
| 3.3.2 | Vendor data-handling attestation reviewed — vendor does not use GIBB inputs for foundation model training |
| 3.3.3 | Customer-facing chatbot outputs reviewed for accidental disclosure (e.g., other customers' data) |

### 3.4 Hallucination mitigation
| Ref | Requirement |
|---|---|
| 3.4.1 | Retrieval-augmented generation (RAG) preferred for factual-grounding use cases |
| 3.4.2 | Customer-facing informational generative use cases shall include disclaimer about AI-generated content |
| 3.4.3 | Generative AI for transactional decisioning (financing approval, customer outcome) prohibited unless approved as High-risk under [STD-AI-01](STD-AI-01-ai-use-case-risk-classification-standard.md) with human review |
| 3.4.4 | Hallucination rate monitored per [STD-AI-02 §3.4](STD-AI-02-ai-model-validation-standard.md) |

### 3.5 IP and copyright
| Ref | Requirement |
|---|---|
| 3.5.1 | Generative outputs used in customer-facing communication reviewed for potential IP issues |
| 3.5.2 | Foundation model vendor IP indemnification clauses required for customer-facing outputs |

### 3.6 Audit logging
| Ref | Requirement |
|---|---|
| 3.6.1 | Generative AI prompts and outputs logged per [STD-CR-02](STD-CR-02-logging-standard.md) for material use cases |
| 3.6.2 | Customer-facing chatbot conversations retained per [STD-CI-02](STD-CI-02-customer-data-retention-standard.md) |

### 3.7 Shariah for Islamic product systems
| Ref | Requirement |
|---|---|
| 3.7.1 | Generative AI describing Islamic finance products to customers shall use Shariah-Committee-approved content sources (RAG over approved knowledge base) |
| 3.7.2 | Generative AI shall not produce Shariah opinions (fatwa-equivalents) — those are Shariah Committee territory exclusively |

### 3.8 Agentic AI special handling
| Ref | Requirement |
|---|---|
| 3.8.1 | Agentic AI (autonomous task execution) shall have scoped capability — limited tools, limited actions |
| 3.8.2 | Material agentic actions require human approval before execution |
| 3.8.3 | Agentic AI for financial transactions prohibited without explicit RMC approval |

## 4. Exceptions
Per [POL-21](../02-policies/POL-21-ai-acceptable-use-policy.md).

## 5. Related documents
[POL-21](../02-policies/POL-21-ai-acceptable-use-policy.md); [STD-AI-01](STD-AI-01-ai-use-case-risk-classification-standard.md); [STD-AI-02](STD-AI-02-ai-model-validation-standard.md); STD-AI-04 AI Training Data; [STD-CR-02](STD-CR-02-logging-standard.md); [REG-AIU](../06-registers/REG-AIU-ai-use-case-register.md); [REG-AIM](../06-registers/REG-AIM-ai-model-inventory.md)

## 6. References
NIST AI RMF Generative AI Profile (July 2024); OWASP Top 10 for LLMs; ISO/IEC 42001:2023; EU AI Act (2024) GenAI provisions; BNM Discussion Paper on Responsible AI; BNM Shariah Governance Framework.

## 7. Document control
| Version | Date | Author | Approver | Change |
|---|---|---|---|---|
| 1.0 | [Effective] | CISO + Data Science | CISO | Initial |
