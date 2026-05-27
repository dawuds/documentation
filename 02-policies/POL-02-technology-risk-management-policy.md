# POL-02 — Technology Risk Management Policy

| | |
|---|---|
| **Document ID** | POL-02 |
| **Layer** | Policy (Tier 1) |
| **Version** | 1.0 |
| **Owner** | Chief Risk Officer |
| **Approver** | Risk Management Committee |
| **Classification** | Internal |
| **Effective** | [Effective] |
| **Next review** | Annual |
| **Parent framework(s)** | [TRMF](../01-frameworks/TRMF.md) |
| **RMiT clause(s)** | Section 9.1 (TRMF Integration with ERM); 9.2 (TRMF Minimum Requirements — 11 mandatory elements); 9.3 (Independent Technology Risk Management Function) |
| **COBIT objective(s)** | APO12 Managed Risk; EDM03 Ensured Risk Optimisation |
| **Practice standard(s)** | ISO 31000:2018; ISO/IEC 27005:2022 |

---

## 1. Purpose

This policy operationalises the [TRMF](../01-frameworks/TRMF.md) at the policy level — establishing how technology risks are identified, assessed, treated, monitored, and reported at GIBB. Together with the [Technology Risk Appetite Statement (POL-03)](POL-03-technology-risk-appetite-statement.md), this policy is the principal day-to-day instruction set for technology risk owners and the Technology Risk Management function.

## 2. Scope

All technology-related risks at GIBB across all business lines, IT functions, and third parties. Includes cyber, third-party, data, cloud, AI, operational, and emerging-technology risk categories.

## 3. Definitions

See [TRMF Section 4](../01-frameworks/TRMF.md). Additional terms:

| Term | Definition |
|---|---|
| **Risk register** | The Technology Risk Register (REG-TR) maintained per RMiT 9.2(h) — the authoritative record of identified technology risks. |
| **Risk treatment plan** | The documented action set to treat a specific risk — actions, owners, dates, target residual rating. |

## 4. Policy statements

### 4.1 Risk identification

- **4.1.1** Technology risks **shall** be identified at defined trigger events: new system deployment, material change, new third-party engagement, new cloud service, new AI use case, emerging-technology adoption, regulatory change, post-incident. *(Implements RMiT 9.2(c).)*
- **4.1.2** Risk identification **shall** include emerging-technology risks per RMiT Appendix 9.
- **4.1.3** Identified risks **shall** be recorded in the Technology Risk Register within 5 business days of identification.

### 4.2 Risk assessment

- **4.2.1** Every identified risk **shall** be assessed for inherent likelihood and impact, controls in place, and residual likelihood and impact, using the TRMF materiality matrix (5×5). *(Implements RMiT 9.2(e); TRMF Section 8.2.1.)*
- **4.2.2** Material risks (Significant or Severe residual rating) **shall** receive independent second-line challenge by the Technology Risk Management function before treatment.

### 4.3 Risk treatment

- **4.3.1** Treatment **shall** be selected from: Treat, Tolerate, Transfer, Terminate. *(Implements RMiT 9.2(f).)*
- **4.3.2** Risk acceptance **shall** follow the TRMF authority matrix: Low → risk owner; Moderate → CRO; Significant → RMC; Severe → Board.
- **4.3.3** Treatment plans **shall** name specific actions, owners, and due dates, and **shall** be tracked to closure.

### 4.4 Risk monitoring

- **4.4.1** Risks **shall** be monitored continuously through KRIs, KCIs, and event-driven alerting per the TRMF. *(Implements RMiT 9.2(g).)*
- **4.4.2** KRI breaches **shall** trigger investigation and, where warranted, treatment plan adjustment.

### 4.5 Risk reporting

- **4.5.1** Technology risk profile **shall** be reported to RMC quarterly and to the Board annually per the TRMF Section 11 reporting matrix. *(Implements RMiT 8.4.)*
- **4.5.2** Material events **shall** be escalated per the TRMF Section 11.2 escalation triggers.

### 4.6 Scenario analysis

- **4.6.1** For Severe-rated risks and risks affecting critical services, **scenario analysis** **shall** be conducted to test the bank's capacity and readiness to resume critical systems under severe-but-plausible conditions. *(Implements RMiT 9.2(j).)*

### 4.7 Information system for risk management

- **4.7.1** An **effective information system** **shall** be maintained to keep the technology risk profile accurate and current per RMiT 9.2(h). Tooling supports risk registration, dashboards, KRI/KCI monitoring, and reporting.

### 4.8 Critical resources and dependencies

- **4.8.1** **Key resources and interdependencies** — including critical third-party service providers and their sub-providers — **shall** be identified and recorded per RMiT 9.2(i). The dependency map is maintained jointly by the Technology Risk Management function and Procurement.

## 5. Roles and responsibilities

| Role | R | A | C | I |
|---|---|---|---|---|
| Risk Management Committee | | A (approval of policy) | | I |
| CRO | A (policy ownership) | | | |
| Head of Technology Risk Management | R | | | I |
| 1st-line risk owners (function heads) | R | | | I |
| 2nd-line Technology Risk team | R (independent challenge) | | C | I |
| Internal Audit | | | C | I |

## 6. Exceptions

Per TRMF Section 12.

## 7. Enforcement

Per TRMF Section 12. Failure to report material risk or to honour treatment commitments is a control deficiency reported to RMC.

## 8. Related documents

- **Parent framework:** [TRMF](../01-frameworks/TRMF.md)
- **Companion policy:** [POL-03 Technology Risk Appetite Statement](POL-03-technology-risk-appetite-statement.md)
- **Related register:** [REG-TR Technology Risk Register](../06-registers/technology-risk-register.md)

## 9. References

- BNM RMiT, 28 November 2025: Section 9.1, 9.2, 9.3; Appendix 9
- COBIT 2019 — APO12; EDM03
- ISO 31000:2018; ISO/IEC 27005:2022

## 10. Document control

| Version | Date | Author | Reviewer | Approver | Change summary |
|---|---|---|---|---|---|
| 1.0 | [Effective] | CRO | RMC | RMC | Initial Effective version |
