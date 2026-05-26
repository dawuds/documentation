# Supplier & Third-Party Security Policy

| | |
|---|---|
| **Document ID** | POL-07 |
| **Layer** | Policy (Tier 1) |
| **Owner** | CISO |
| **Approver** | Risk Management Committee |
| **Classification** | Internal |
| **Version** | 1.0 |
| **Effective date** | 2026-02-01 |
| **Next review** | 2027-02-01 |
| **ISO/IEC 27002:2022 controls** | 5.19 (Information security in supplier relationships), 5.20 (Addressing information security within supplier agreements), 5.21 (Managing information security in the ICT supply chain), 5.22 (Monitoring, review and change management of supplier services), 5.23 (Information security for use of cloud services) |
| **BNM RMiT (28 Nov 2025)** | Section 10.46–10.49 (Third Party Service Provider Management); Section 14 (External Party Assurance); Section 10.50–10.52 + Appendix 10 (Cloud Services and Risk Coverage); Appendix 8 (Third-party risk coverage matrix) |

> Skeleton policy.

---

## 1. Purpose

To define how General Bank manages information security risk introduced by suppliers, outsourced service providers, and cloud services, across the supplier lifecycle from selection through exit.

## 2. Scope

All suppliers and third parties with access to General Bank information, systems, or premises, including cloud service providers, managed service providers, software vendors, professional service firms, and outsourced operations.

## 3. Policy statements

### 3.1 Selection and due diligence

- **3.1.1** Information security risk shall be assessed before engagement of any supplier processing Internal or higher-classified information. Material engagements shall be subject to enhanced due diligence per BNM RMiT Section 10.47 (Third Party Due Diligence) and shall consider the range of risks in Appendix 8 (Third-Party Risk Coverage Matrix). *(Implements ISO/IEC 27002:2022 control 5.19; BNM RMiT Section 10.46 (Third Party Service Provider Oversight); Section 10.47 (Due Diligence).)*
- **3.1.2** Material outsourcing arrangements shall comply with BNM outsourcing requirements, including any regulatory notification or approval obligations. External party assurance over outsourced services shall be obtained per BNM RMiT Section 14.

### 3.2 Contractual security requirements

- **3.2.1** Information security obligations shall be incorporated into all supplier contracts processing General Bank information, including: confidentiality, access control, incident notification, audit rights, sub-contracting controls, data return and destruction on exit, and applicable regulatory obligations. *(Implements ISO/IEC 27002:2022 control 5.20; BNM RMiT Section 10.48 (Service Level Agreement Requirements).)*
- **3.2.2** **Right-to-audit** clauses shall be included in all material supplier contracts, exercisable by General Bank or its appointed agent and (where applicable) by BNM. *(BNM RMiT Section 10.46 (TPSP Oversight); Section 14 (External Party Assurance).)*

### 3.3 Cloud services

- **3.3.1** Use of cloud services shall comply with BNM RMiT Section 10.50–10.52 (Cloud Services), including cloud risk assessment (Section 10.50), public cloud key risks and controls (Section 10.51, with Appendix 10 risk and control mapping matrix), and cloud data protection safeguards (Section 10.52). Cloud provider due diligence, data residency, exit strategy, and shared-responsibility documentation shall be maintained. Where the bank's risk management practice departs from Appendix 10, the bank shall be prepared to demonstrate to BNM that the alternative practice is at least as effective per Section 10.51. *(Implements ISO/IEC 27002:2022 control 5.23.)*
- **3.3.2** Cloud configuration shall be governed by cloud security baselines maintained by the CISO and enforced through cloud security posture management.

### 3.4 Supply-chain risk

- **3.4.1** ICT supply chain risk shall be managed through software composition analysis, vendor risk monitoring, and tiered assurance based on supplier criticality. *(Implements ISO/IEC 27002:2022 control 5.21.)*

### 3.5 Ongoing monitoring

- **3.5.1** Supplier security performance shall be monitored on a frequency proportionate to criticality, including security incident reporting from the supplier, attestation/certification monitoring (e.g., ISO 27001, SOC 2 Type 2), and periodic re-assessment. Continuous third-party cybersecurity monitoring shall apply per BNM RMiT Section 10.49. *(Implements ISO/IEC 27002:2022 control 5.22; BNM RMiT Section 10.49 (Continuous Third Party Cybersecurity Monitoring).)*

### 3.6 Exit

- **3.6.1** Every material supplier contract shall include an exit strategy covering data return or destruction, knowledge transfer, and orderly transition.

## 4. Roles and responsibilities

| Role | R | A | C | I |
|---|---|---|---|---|
| Risk Management Committee | | A | | I |
| CISO | A | | | |
| Head of Procurement | R | | C | I |
| Third-Party Risk Management | R | | C | I |
| Business owners of supplier relationships | R | | | I |

## 5. Exceptions

Per [POL-00](00-information-security-policy.md).

## 6. Enforcement

Per [POL-00](00-information-security-policy.md).

## 7. Related documents

[POL-00](00-information-security-policy.md), [POL-04](04-data-classification-policy.md), [POL-08](08-incident-management-policy.md).

## 8. References

ISO/IEC 27002:2022 — controls 5.19–5.23. BNM RMiT (28 Nov 2025) Section 10.46–10.49 (TPSP); Section 14 (External Party Assurance); Section 10.50–10.52 + Appendix 10 (Cloud); Appendix 8 (TPSP risk coverage matrix). [Regulatory Mapping Reference](../00-foundations/regulatory-mapping-reference.md).

## 9. Document control

| Version | Date | Author | Reviewer | Approver | Change summary |
|---|---|---|---|---|---|
| 1.0 | 2026-01-15 | CISO | Risk Management Committee | Risk Management Committee | Initial Effective version (skeleton). |
