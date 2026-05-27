# STD-AI-01 — AI Use Case Risk Classification Standard

| | |
|---|---|
| **Document ID** | STD-AI-01 | **Version** | 1.0 |
| **Owner / Approver** | AI Governance Committee (CDO operates) / AIGC |
| **Parent policy** | [POL-21](../02-policies/POL-21-ai-acceptable-use-policy.md) | **Parent framework** | [AIGF](../01-frameworks/AIGF.md) |
| **Practice** | NIST AI RMF 1.0; EU AI Act (2024); ISO/IEC 42001:2023 |

## 1. Purpose
Specify how AI use cases are risk-classified at GIBB into Unacceptable / High-risk / Limited-risk / Minimal-risk, drawing on the EU AI Act risk taxonomy adapted for Malaysian banking.

## 2. Scope
All AI use cases at GIBB — pre-development, in-development, in-production.

## 3. Requirements

### 3.1 Unacceptable-risk (prohibited)

Use cases falling into any of the following are **prohibited** and cannot be approved:

| Pattern | Rationale |
|---|---|
| Social scoring of customers based on inferred behaviour (analogous to EU AI Act Art. 5 prohibition) | Reputational, ethical, and regulatory risk |
| Real-time biometric identification in publicly accessible spaces for marketing | Privacy and consent issues |
| Manipulation of customer behaviour through subliminal techniques | Ethics; consumer protection |
| Exploitation of vulnerabilities of specific customer groups (age, disability, financial distress) | Customer fairness; reputational |
| Fully autonomous decision-making affecting customer outcomes without human recourse | Regulatory and ethical risk |
| AI used to evade Shariah-compliance gates in product systems | Shariah governance breach |

### 3.2 High-risk

Use cases meeting any of the following criteria are **High-risk**:

| Criterion | Examples |
|---|---|
| Affects customer financial outcomes | Credit decisioning, financing approval, fraud-based account restrictions |
| Affects customer access to services | Customer onboarding decisions, KYC outcomes |
| Used in AML/CFT or regulatory compliance decisioning | Transaction monitoring, sanctions screening |
| Affects employee outcomes | Hiring decisions, performance assessments |
| Operates on Shariah-compliant product logic | AI in Murabahah pricing, Musharakah profit-share calculation |
| Processes sensitive personal data per PDPA | Health-based pricing, biometric authentication |
| Used in critical infrastructure / NCII context | Per CSA 2024 NCII operational AI |

High-risk requires: AIGC approval; independent validation; human-in-the-loop; continuous fairness monitoring; documented explainability; Shariah Committee approval if product-system relevant.

### 3.3 Limited-risk

Use cases involving:

| Criterion | Examples |
|---|---|
| Customer-facing communication but informational only (no decisioning) | Generative AI chatbot for product information |
| Internal productivity with controlled scope | Code review augmentation, document summarisation |
| Marketing personalisation (within consent) | Product recommendation |

Limited-risk requires: AIGC notification (not approval); standard validation; some human oversight (sampling); compliance with [POL-21 §4.9](../02-policies/POL-21-ai-acceptable-use-policy.md) generative AI controls.

### 3.4 Minimal-risk

Use cases with no customer-facing impact and limited internal scope:

| Examples |
|---|
| Internal email summarisation |
| Generic productivity (calendar scheduling assistance) |
| Information classification on Internal-or-below data |

Minimal-risk: standard tool approval; per [POL-21 §4.2](../02-policies/POL-21-ai-acceptable-use-policy.md) approved tool list.

### 3.5 Classification process

| Step | Owner |
|---|---|
| 1. Use case description submitted | Business owner |
| 2. Initial classification | AI Governance team |
| 3. Cross-functional review (Risk, Legal, Compliance, Shariah if relevant) | AIGC |
| 4. Classification approved | AIGC chair |
| 5. Recorded in [REG-AIU](../06-registers/REG-AIU-ai-use-case-register.md) | AI Governance |

### 3.6 Reclassification triggers

| Trigger | Action |
|---|---|
| Material change in use case scope | Re-classify |
| Material change in regulatory landscape (BNM AI PD issuance, EU AI Act updates) | Portfolio re-classification |
| Incident attributable to AI use case | Re-classify; may elevate one tier |

## 4. Exceptions
Unacceptable-risk use cases are **not** exception-approvable. Other reclassifications per AIGC.

## 5. Related documents
[POL-21](../02-policies/POL-21-ai-acceptable-use-policy.md); STD-AI-02 AI Model Validation Standard (future); [REG-AIU](../06-registers/REG-AIU-ai-use-case-register.md); [AIGF](../01-frameworks/AIGF.md)

## 6. References
NIST AI RMF 1.0; NIST AI RMF Generative AI Profile (July 2024); EU AI Act (2024); ISO/IEC 42001:2023; BNM Discussion Paper on Responsible AI; MAS FEAT.

## 7. Document control
| Version | Date | Author | Approver | Change |
|---|---|---|---|---|
| 1.0 | [Effective] | AI Governance | AIGC | Initial |
