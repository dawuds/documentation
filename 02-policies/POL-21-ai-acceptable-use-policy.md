# POL-21 — AI Acceptable Use Policy

| | |
|---|---|
| **Document ID** | POL-21 |
| **Layer** | Policy (Tier 1) |
| **Version** | 1.0 |
| **Owner** | Chief Data Officer + CISO (joint) |
| **Approver** | Risk Management Committee |
| **Classification** | Internal |
| **Effective** | [Effective] |
| **Next review** | Annual + on BNM AI PD publication |
| **Parent framework(s)** | [AIGF](../01-frameworks/AIGF.md) |
| **RMiT clause(s)** | Section 9.2(c) (emerging technology risks); Appendix 9 (Guidance on Emerging Technologies) |
| **COBIT objective(s)** | EDM03; APO04 Managed Innovation; APO12 Managed Risk; APO14 Managed Data |
| **Practice standard(s)** | NIST AI Risk Management Framework 1.0 + Generative AI Profile; ISO/IEC 42001:2023 |
| **Additional anchors** | EU AI Act (2024); BNM Discussion Paper on Responsible AI; MAS FEAT principles; BNM Shariah Governance Framework |

> **Caveat.** This policy will be re-anchored when BNM issues a formal AI policy document.

---

## 1. Purpose

To define how AI may be used at GIBB — by whom, for what purposes, with what controls, and with what oversight. Operationalises [AIGF](../01-frameworks/AIGF.md) at the policy level. Covers AI built in-house, procured from vendors, and embedded in cloud or third-party products.

## 2. Scope

All AI use cases at GIBB — machine learning (supervised, unsupervised, reinforcement), deep learning, generative AI (LLM-based and other), expert systems, agentic AI, embedded AI in third-party products. All personnel using AI tools.

## 3. Definitions

See [AIGF Section 4](../01-frameworks/AIGF.md).

## 4. Policy statements

### 4.1 Risk classification first

- **4.1.1** Every AI use case **shall** be risk-classified per [STD-AI-01 AI Use Case Risk Classification Standard](../03-standards/STD-AI-01-ai-use-case-risk-classification-standard.md) (future) before development resources are committed. Classifications: **Unacceptable** (prohibited), **High-risk**, **Limited-risk**, **Minimal-risk**.

### 4.2 Approved tools only

- **4.2.1** Only AI tools approved per the GIBB AI tool catalogue **shall** be used for work involving bank information.
- **4.2.2** Confidential or higher-classification data **shall not** be entered into AI tools not explicitly approved for that classification.

### 4.3 Lawful, fair, explainable

- **4.3.1** AI use cases **shall** be lawful, fair to affected customers and employees, and explainable to the degree required by the use case's risk classification.

### 4.4 Human oversight for high-risk

- **4.4.1** High-risk AI use cases **shall** include human oversight in the decision loop. Fully autonomous AI decision-making affecting customer outcomes is prohibited without explicit RMC approval and a human-recourse mechanism.

### 4.5 Training data governance

- **4.5.1** AI training data **shall** be governed under [POL-11 Data Classification and Handling Policy](POL-11-data-classification-policy.md) and [DGF](../01-frameworks/DGF.md). Customer data used for training requires CIMF-compliant lawful basis and consent.

### 4.6 Model validation

- **4.6.1** Models **shall** be validated against fairness, accuracy, robustness, and security criteria proportionate to risk classification before deployment. High-risk use cases require independent validation.

### 4.7 Continuous monitoring

- **4.7.1** Deployed models **shall** be continuously monitored for drift, fairness degradation, security indicators (prompt injection for LLM-based), and performance.

### 4.8 AI vendor risk

- **4.8.1** AI vendors and embedded AI in third-party products **shall** be assessed per [TPRMF](../01-frameworks/TPRMF.md) with AI-specific addenda — training-data provenance, model evaluation reports, fairness attestations, security testing.

### 4.9 Generative AI special handling

- **4.9.1** Generative AI use cases **shall** apply additional controls — prompt-injection defence, output validation, hallucination mitigation, IP and data-leakage controls.
- **4.9.2** Use of generative AI for customer-facing communication **shall** include a human review step before sending unless the use case is approved as low-risk by the AI Governance Committee.

### 4.10 Shariah review for product-system AI

- **4.10.1** AI use cases embedded in Islamic product systems **shall** undergo Shariah Committee review for Shariah-compliance implications.

### 4.11 NCII overlay

- **4.11.1** AI systems within NCII scope **shall** comply with any additional NACSA expectations per [NCIIF](../01-frameworks/NCIIF.md).

## 5. Roles and responsibilities

| Role | R | A | C | I |
|---|---|---|---|---|
| Risk Management Committee | | A | | |
| CDO | A (joint) | | | |
| CISO | | A (joint — AI security) | | |
| CRO | | | C (model risk acceptance) | I |
| AI Governance Committee (cross-functional) | R | | | I |
| Shariah Committee | | A (Shariah of AI in product systems) | | |
| AI use case owners | R | | | I |
| All personnel using AI tools | R | | | I |

## 6. Exceptions

Per TRMF Section 12. **Unacceptable-risk AI use cases shall not be exception-approved.** Other AI exceptions require AI Governance Committee + CRO approval.

## 7. Enforcement

Per TRMF Section 12.

## 8. Related documents

- **Parent framework:** [AIGF](../01-frameworks/AIGF.md)
- **Related policies:** [POL-11](POL-11-data-classification-policy.md); [POL-05 Acceptable Use](POL-05-acceptable-use-policy.md); [POL-12](POL-12-cryptography-policy.md); [POL-17 Secure Development](POL-17-secure-development-policy.md)
- **Related register:** [REG-AIU AI Use Case Register](../06-registers/REG-AIU-ai-use-case-register.md)

## 9. References

- NIST AI RMF 1.0 (January 2023) + Generative AI Profile (July 2024)
- ISO/IEC 42001:2023 — AI Management System
- EU AI Act (2024) — risk classification reference
- BNM Discussion Paper on Responsible AI in Financial Services
- MAS FEAT principles (Singapore)
- BNM RMiT, 28 November 2025: Section 9.2(c); Appendix 9
- BNM Shariah Governance Framework
- COBIT 2019 — EDM03; APO04; APO12; APO14

## 10. Document control

| Version | Date | Author | Reviewer | Approver | Change summary |
|---|---|---|---|---|---|
| 1.0 | [Effective] | CDO + CISO | RMC | RMC | Initial Effective version. Re-anchor required on BNM formal AI PD issuance. |
