# Information Security Policy

| | |
|---|---|
| **Document ID** | POL-00 |
| **Layer** | Policy (Tier 1) — **Master** |
| **Owner** | CISO |
| **Approver** | **Board of Directors** |
| **Classification** | Internal |
| **Version** | 1.0 |
| **Effective date** | 2026-02-01 |
| **Next review** | 2027-02-01 (annual, or sooner on material change) |
| **ISO/IEC 27001:2022** | Clause 5.2 (mandatory) |
| **ISO/IEC 27002:2022** | Control 5.1 (Policies for information security) |
| **BNM RMiT (28 Nov 2025)** | §8 (Governance) — particularly §8.1, §8.2 (Board); §9 (Technology Risk Management Framework) — incl. §9.4–9.5 (Designated CISO); §11 (Cybersecurity Management) |

> **Notice.** This document is the master policy of the General Bank Information Security Management System (ISMS). It is approved by the Board of Directors and supersedes all prior information security policies. It is mandatory and applies to every employee, contractor, third party, and system within the ISMS scope. Non-compliance is grounds for disciplinary action and, where applicable, civil or criminal proceedings.

---

## 1. Purpose

This policy establishes General Bank's commitment to the confidentiality, integrity, and availability of information entrusted to it by customers, employees, partners, and regulators. It sets out the principles by which General Bank protects information assets and discharges its obligations under Malaysian financial sector regulation, in particular Bank Negara Malaysia's *Risk Management in Technology (RMiT)* policy document.

It serves three purposes:

1. To express the Board's commitment to information security (satisfying ISO/IEC 27001:2022 Clause 5.2).
2. To establish the Information Security Management System (ISMS) as the means by which the commitment is operationalised.
3. To cascade into the supporting policies, standards, procedures, plans, and registers that implement the commitment day-to-day.

## 2. Scope

This policy applies to:

- **All information assets** owned, processed, transmitted, or stored by General Bank, regardless of location, ownership of the underlying infrastructure, or processing party.
- **All personnel** — employees, contractors, secondees, consultants, and any third party with access to General Bank information.
- **All systems and services** — owned, leased, cloud-hosted, outsourced, or provided by third parties — that process General Bank information.
- **All locations** — General Bank premises, third-party premises, remote-work locations, and any other location from which General Bank information is accessed.

The Statement of Applicability ([REG-SOA](../05-registers/statement-of-applicability.md)) records which ISO/IEC 27002:2022 controls are applicable, with justification for any exclusions (ISO/IEC 27001:2022 Clause 6.1.3 d).

## 3. Definitions

| Term | Definition |
|---|---|
| **Information asset** | Any item of information of value to General Bank, in any form (digital, physical, spoken). |
| **ISMS** | Information Security Management System — the systematic approach for managing information security, as defined by ISO/IEC 27001:2022. |
| **Confidentiality** | Property that information is not made available or disclosed to unauthorised individuals, entities, or processes (ISO/IEC 27000). |
| **Integrity** | Property of accuracy and completeness (ISO/IEC 27000). |
| **Availability** | Property of being accessible and usable upon demand by an authorised entity (ISO/IEC 27000). |
| **Material technology incident** | An incident which, in the judgement of the CISO and the CRO, has or may have a significant adverse impact on the bank's operations, customers, reputation, or regulatory standing. Refer to [STD-08-01](../02-standards/incident-classification-and-severity-standard.md) for the materiality criteria. |
| **Risk appetite** | The aggregate level and types of risk the Board is willing to accept in pursuit of its strategic objectives. |

## 4. ISMS establishment

The Board hereby establishes the Information Security Management System for General Bank. The ISMS:

- **4.1** Is led by the Chief Information Security Officer (CISO), who reports functionally to the Chief Risk Officer (CRO) and has direct access to the Board Risk Committee.
- **4.2** Operates under a three-line model: business and IT (1st line) operate controls; Technology Risk and Compliance (2nd line) provide independent challenge; Internal Audit (3rd line) provides independent assurance.
- **4.3** Is reviewed for effectiveness by the Risk Management Committee quarterly, and by the Board at least annually as part of the ISMS Management Review (ISO/IEC 27001:2022 Clause 9.3).
- **4.4** Is subject to internal audit at a frequency determined by the audit plan, and to external certification audit on the cycle required by the certification body (typically annual surveillance, triennial recertification).

## 5. Information security objectives

In accordance with ISO/IEC 27001:2022 Clause 6.2, General Bank establishes the following measurable objectives for the ISMS. Performance against these objectives is reported to the Risk Management Committee quarterly.

| Objective | Measure | Target |
|---|---|---|
| Maintain customer data confidentiality | Number of confirmed data confidentiality breaches affecting customer data | Zero per year |
| Maintain critical service availability | Availability of customer-facing critical services | ≥ 99.9% per RMiT-aligned classification |
| Detect and contain incidents quickly | Mean time to detect (MTTD) and mean time to contain (MTTC) by severity tier | Per STD-08-01 thresholds |
| Maintain control effectiveness | % of ISMS controls assessed as effective in periodic testing | ≥ 95% |
| Maintain regulatory compliance | Number of overdue regulatory remediation actions | Zero past due |
| Maintain workforce awareness | % of personnel completing mandatory security training | 100% within 30 days of joining; ≥ 95% annual renewal compliance |

## 6. Principles

The following principles are mandatory across the organisation. Each is operationalised in one or more supporting policies (§9).

### 6.1 Governance and accountability

- **6.1.1** Information security shall be governed by the Board through the Risk Management Committee. *(Implements ISO/IEC 27001:2022 Clause 5.1; BNM RMiT §8.1 (Board approval of technology risk appetite); §8.2 (Board oversight responsibilities); §8.3 (Board-level technology committee).)*
- **6.1.2** Every information asset shall have a named owner accountable for its protection. *(Implements ISO/IEC 27002:2022 control 5.9.)*
- **6.1.3** Every supporting policy, standard, procedure, plan, and register in the ISMS shall have a named owner and an approval authority. *(Implements ISO/IEC 27001:2022 Clause 5.3.)*

### 6.2 Risk-based protection

- **6.2.1** Information security risks shall be identified, assessed, treated, and monitored through a documented risk management process aligned with ISO/IEC 27005:2022. *(Implements ISO/IEC 27001:2022 Clause 6.1.)*
- **6.2.2** The selection of controls shall be risk-based, with applicable ISO/IEC 27002:2022 controls recorded in the Statement of Applicability and justified exclusions documented. *(Implements ISO/IEC 27001:2022 Clause 6.1.3 d.)*
- **6.2.3** Risk acceptance decisions shall be made by the risk owner, with material residual risks escalated to the Risk Management Committee.

### 6.3 Least privilege and segregation of duties

- **6.3.1** Access to information assets shall be granted on a least-privilege, role-based basis, and reviewed at intervals defined by [POL-02 Access Control Policy](02-access-control-policy.md). *(Implements ISO/IEC 27002:2022 controls 5.15, 5.18; BNM RMiT §10.53–10.57 (Access Control), particularly §10.54 (principles) and §10.55 (MFA).)*
- **6.3.2** Duties that present a risk of error, fraud, or unauthorised activity if combined shall be segregated. *(Implements ISO/IEC 27002:2022 control 5.3.)*

### 6.4 Defence in depth

- **6.4.1** Information assets shall be protected by layered controls — preventive, detective, and corrective — proportionate to the value and sensitivity of the asset. *(Implements ISO/IEC 27002:2022 controls 8.6, 8.7, 8.16.)*
- **6.4.2** No single control shall be the sole protection of a critical information asset.

### 6.5 Secure by design

- **6.5.1** Information security requirements shall be defined, designed, and tested across the lifecycle of every system, application, and service. *(Implements ISO/IEC 27002:2022 controls 8.25–8.31; BNM RMiT §10.4–10.16 (System Development and Acquisition) and §12 (Digital Services) with Appendices 2 and 3 for delivery-channel and authentication minimum controls.)*
- **6.5.2** Vulnerabilities shall be identified, prioritised, and remediated within timelines defined by [POL-13 Vulnerability Management Policy](13-vulnerability-management-policy.md). *(Implements ISO/IEC 27002:2022 control 8.8; BNM RMiT §10.17–10.19 (Patch and End-of-Life System Management).)*

### 6.6 Resilience

- **6.6.1** Critical business services shall have documented recovery objectives (RTO, RPO, MTPD), tested at least annually. *(Implements ISO/IEC 27002:2022 controls 5.29, 5.30; BNM RMiT §10.24–10.28 (Data Centre Resilience); §10.29–10.35 (Service Availability); §10.44–10.45 (Backup, including tamper-proof backup at §10.45).)*
- **6.6.2** Incidents shall be detected, classified, contained, and learned from, with material technology incidents escalated to the regulator in accordance with [POL-08 Incident Management Policy](08-incident-management-policy.md). *(Implements ISO/IEC 27002:2022 controls 5.24–5.28; BNM RMiT §11.12–11.17 (Cyber Response and Recovery); §11.18 (Cyber Incident Notification to BNM).)*

### 6.7 Information classification

- **6.7.1** Information shall be classified, labelled, and handled according to its sensitivity, in accordance with [POL-04 Data Classification & Handling Policy](04-data-classification-policy.md). *(Implements ISO/IEC 27002:2022 controls 5.12, 5.13.)*

### 6.8 Third-party assurance

- **6.8.1** Information security risks introduced by suppliers and third parties shall be identified, assessed, contractually addressed, and continuously monitored, in accordance with [POL-07 Supplier & Third-Party Security Policy](07-supplier-security-policy.md). *(Implements ISO/IEC 27002:2022 controls 5.19–5.23; BNM RMiT §10.46–10.49 (Third Party Service Provider Management); §14 (External Party Assurance); §10.50–10.52 and Appendix 10 for cloud services.)*

### 6.9 People

- **6.9.1** All personnel shall be subject to screening proportionate to the sensitivity of their role, contractually bound to confidentiality, and trained on information security responsibilities. *(Implements ISO/IEC 27002:2022 controls 6.1–6.3.)*
- **6.9.2** Security awareness shall be continuous, not annual-only, and reinforced through targeted training for high-risk roles. *(Implements ISO/IEC 27002:2022 control 6.3; BNM RMiT §15 (Security Awareness and Education).)*

### 6.10 Continual improvement

- **6.10.1** The ISMS shall be subject to internal audit, management review, and continual improvement. Findings, nonconformities, and incidents shall drive corrective and preventive actions. *(Implements ISO/IEC 27001:2022 Clauses 9.2, 9.3, 10.1.)*

## 7. Roles and responsibilities

| Role | Responsibility |
|---|---|
| **Board of Directors** | Approves this policy; ultimately accountable for information security; receives at least annual ISMS reporting. |
| **Risk Management Committee** | Approves supporting policies and plans; oversees ISMS performance quarterly; reviews material risks and incidents. |
| **Chief Executive Officer** | Sponsors the ISMS; ensures resourcing; accountable for execution. |
| **Chief Risk Officer (CRO)** | Functional line manager of the CISO; ensures information security risk is integrated into enterprise risk management. |
| **Chief Information Security Officer (CISO)** | Operates the ISMS; owns this policy; chairs the ISMS Working Group; reports to the Risk Management Committee and the Board. |
| **Chief Compliance Officer (CCO)** | Maps regulatory obligations to ISMS controls; provides compliance assurance. |
| **Chief Information Officer (CIO) / Head of IT** | Implements technical controls; operates IT services to defined security standards. |
| **Chief Human Resources Officer (CHRO)** | Operates personnel security (screening, contracts, training) per [POL-06](06-hr-security-policy.md). |
| **All personnel** | Comply with this policy and the supporting suite; report security events; complete required training. |
| **Internal Audit** | Independently tests ISMS controls; reports to the Audit Committee. |
| **ISMS Manager** | Operates document control, manages the ISMS calendar, supports the CISO with management reviews and audits. |

## 8. Risk management

The information security risk management process is documented in the **Information Security Risk Management Methodology** (separate procedural document) and operationalised in the [Risk Register](../05-registers/risk-register.md). The process aligns with ISO/IEC 27005:2022 and integrates with the enterprise risk management framework.

Risks are owned by named risk owners, treated through a treatment plan, and reviewed at least quarterly by the Risk Management Committee.

## 9. Supporting policy suite

This master policy is implemented through the following supporting policies. Each is mandatory within its scope.

| ID | Policy | Primary ISO/IEC 27002:2022 controls | Primary BNM RMiT (Nov 2025) |
|---|---|---|---|
| [POL-01](01-acceptable-use-policy.md) | Acceptable Use Policy | 5.10, 8.1 | §10.53–10.57 (Access Control); §15 (Awareness) |
| [POL-02](02-access-control-policy.md) | Access Control Policy | 5.15–5.18, 8.2–8.5 | §10.53–10.57 |
| [POL-03](03-asset-management-policy.md) | Asset Management Policy | 5.9–5.11 | §9.2 (TRMF asset identification); §11.3(h) (centralised asset inventory) |
| [POL-04](04-data-classification-policy.md) | Data Classification & Handling Policy | 5.12, 5.13 | §9.2(d) (asset classification); §10.44(d) + App. 1 (sensitive media); §12 (Digital Services) |
| [POL-05](05-cryptography-policy.md) | Cryptography Policy | 8.24 | §10.20–10.23 (Cryptography) |
| [POL-06](06-hr-security-policy.md) | HR Security Policy | 6.1–6.6 | §15 (Security Awareness and Education) |
| [POL-07](07-supplier-security-policy.md) | Supplier & Third-Party Security Policy | 5.19–5.23 | §10.46–10.49 (TPSP); §14 (External Party Assurance); §10.50–10.52 + App. 10 (Cloud) |
| [POL-08](08-incident-management-policy.md) | Incident Management Policy | 5.24–5.28 | §11.1–11.7 (CRF); §11.12–11.17 (Cyber Response and Recovery); §11.18 (BNM Notification) |
| [POL-09](09-business-continuity-policy.md) | Business Continuity Policy | 5.29, 5.30 | §10.24–10.28 (DC Resilience); §10.29–10.35 (Service Availability); §10.44–10.45 (Backup) |
| [POL-10](10-physical-security-policy.md) | Physical & Environmental Security Policy | 7.1–7.14 | §10.26 (DC Physical Security) |
| [POL-11](11-operations-security-policy.md) | Operations Security Policy | 8.6, 8.7, 8.13, 8.15, 8.16, 8.32 | §10 (Tech Operations); §11.9 (SOC); §11.10 (Threat Intel) |
| [POL-12](12-secure-development-policy.md) | Secure Development Policy | 8.25–8.31 | §10.4–10.16 (SDLC); §12 (Digital Services) + App. 2/3 |
| [POL-13](13-vulnerability-management-policy.md) | Vulnerability & Patch Management Policy | 8.8 | §10.17–10.19 (Patch and EOL); §11.6 (Red Team); §11.7 (Coordinated Disclosure) |
| [POL-14](14-compliance-policy.md) | Compliance Policy | 5.31–5.36 | §13 (Technology Audits); §11.4 (NCII / Cyber Security Act 2024) |

## 10. Compliance with laws and regulations

General Bank shall comply with all applicable laws, regulations, and contractual obligations relating to information security, including but not limited to:

- The Financial Services Act 2013 (Malaysia)
- The Islamic Financial Services Act 2013 (Malaysia)
- The Personal Data Protection Act 2010 (Malaysia)
- The Computer Crimes Act 1997 (Malaysia)
- The **Cyber Security Act 2024** (Malaysia) — including NCII designation obligations and any directives issued by the National Cyber Security Agency (NACSA), where the bank is designated as a National Critical Information Infrastructure entity (per BNM RMiT §11.4)
- Bank Negara Malaysia *Risk Management in Technology (RMiT)*, policy document issued 28 November 2025 (BNM/RH/PD 028-100)
- Bank Negara Malaysia *Operational Risk Reporting* policy document (the upstream source of cyber incident notification timelines referenced by RMiT §11.18)
- Bank Negara Malaysia *Business Continuity Management* policy document
- Bank Negara Malaysia *Outsourcing* policy document
- Any applicable foreign data protection law for cross-border processing

Compliance with these obligations is operationalised in [POL-14 Compliance Policy](14-compliance-policy.md) and tracked through the Compliance Register.

## 11. Awareness and communication

This policy shall be:

- Communicated to all personnel within 30 days of joining and on every material revision.
- Acknowledged in writing (or by equivalent attestation) by every employee and contractor annually.
- Available to all personnel through the intranet.
- Available to external parties (auditors, regulators, contractually entitled third parties) on request.

## 12. Exceptions

Any deviation from this policy or the supporting suite shall be:

- Documented in the Exception Register with a stated justification and compensating control.
- Approved by the **Risk Management Committee** for policy-level exceptions, or by the CISO for standard-level exceptions, time-bound to a maximum of 12 months, renewable once with re-justification.
- Reviewed quarterly by the Risk Management Committee for trends suggesting the underlying policy should be revised.

## 13. Enforcement

Non-compliance with this policy or the supporting suite may result in disciplinary action up to and including termination of employment, termination of contract, and, where applicable, civil or criminal proceedings.

## 14. Related documents

- **Parent:** None — this is the master policy.
- **Supporting policies:** POL-01 through POL-14 (see §9).
- **Statement of Applicability:** [REG-SOA](../05-registers/statement-of-applicability.md)
- **Risk Register:** [REG-RR](../05-registers/risk-register.md)

## 15. References

- ISO/IEC 27001:2022 — Information security management systems — Requirements.
- ISO/IEC 27002:2022 — Information security controls.
- ISO/IEC 27005:2022 — Guidance on managing information security risks.
- ISO/IEC 27000:2018 — Overview and vocabulary.
- Bank Negara Malaysia, *Risk Management in Technology (RMiT)*, policy document, **issued 28 November 2025** (BNM/RH/PD 028-100).
- Bank Negara Malaysia, *Operational Risk Reporting* policy document, Part C.
- Bank Negara Malaysia, *Business Continuity Management* policy document, Part C.
- Cyber Security Act 2024 (Malaysia) — NCII designation regime and NACSA directives.
- Financial Services Act 2013 (Malaysia).
- Personal Data Protection Act 2010 (Malaysia).
- Computer Crimes Act 1997 (Malaysia).
- [Regulatory Mapping Reference](../00-foundations/regulatory-mapping-reference.md) — repo-internal canonical mapping (this document is bound by it).

## 16. Document control

| Version | Date | Author | Reviewer | Approver | Change summary |
|---|---|---|---|---|---|
| 0.1–0.9 | 2025-11-20 → 2026-01-10 | CISO | Technology Risk, Compliance, Legal, Internal Audit | — | Drafting cycle |
| 1.0 | 2026-01-15 | CISO | Risk Management Committee | **Board of Directors** | Initial Effective version. Approved by the Board (minutes 2026-01-15, agenda item 4.2). |
