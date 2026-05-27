# POL-14 — Business Continuity Policy

| | |
|---|---|
| **Document ID** | POL-14 |
| **Layer** | Policy (Tier 1) |
| **Version** | 1.0 |
| **Owner** | Chief Operating Officer |
| **Approver** | Risk Management Committee |
| **Classification** | Internal |
| **Effective** | [Effective] |
| **Next review** | Annual + post-disruption |
| **Parent framework(s)** | [BCMF](../01-frameworks/BCMF.md) |
| **RMiT clause(s)** | Section 10.24–10.28 (Data Centre Resilience); 10.29–10.35 (Service Availability); 10.32 (Critical System HA); 10.44–10.45 (Backup, incl. Tamper-Proof Backup and Isolated Recovery) |
| **COBIT objective(s)** | DSS04 Managed Continuity; DSS03 Managed Problems |
| **Practice standard(s)** | ISO/IEC 22301:2019; ISO/IEC 27031:2011 |
| **Additional anchors** | BNM Business Continuity Management Policy Document; BNM Operational Risk Reporting PD |

---

## 1. Purpose

To establish how GIBB sustains critical business services through disruption — whether arising from technology failure, cyber incident, third-party failure, environmental event, pandemic, or other cause — and to define the governance of business continuity and disaster recovery.

## 2. Scope

All business services, supporting systems, suppliers, personnel, and locations relied upon to deliver GIBB's regulated banking services to customers, BNM, financial market infrastructure participants, and other stakeholders.

## 3. Definitions

| Term | Definition |
|---|---|
| **Business continuity** | Capability to continue delivering critical services at acceptable predefined levels during and after disruption. |
| **Critical service** | A service whose disruption would have material customer, regulatory, operational, or reputational impact. |
| **BIA** | Business Impact Analysis — the process of identifying critical services, their dependencies, and impact tolerances. |
| **MTPD / RTO / RPO** | Maximum Tolerable Period of Disruption / Recovery Time Objective / Recovery Point Objective. |
| **Tamper-proof backup** | Backup retained with immutability protections per RMiT 10.45. |
| **Isolated recovery** | Recovery capability operating from an environment isolated from primary production. |

## 4. Policy statements

### 4.1 BIA-driven prioritisation

- **4.1.1** Critical services **shall** be identified through Business Impact Analysis conducted at least annually, with impact tolerances (MTPD, RTO, RPO) set per service and approved by the RMC. *(Implements RMiT 10.32; ISO 22301:2019 Clause 8.2.)*

### 4.2 Continuity strategy

- **4.2.1** Continuity strategies (alternate sites, alternate suppliers, manual workarounds, technology failover) **shall** be defined per critical service, proportionate to the impact tolerance from the BIA. *(Implements ISO/IEC 27002:2022 control 5.29.)*

### 4.3 ICT readiness

- **4.3.1** ICT services supporting critical business services **shall** be designed to meet the RTO and RPO defined for each, with documented architecture, data replication, and failover procedures. *(Implements RMiT 10.24, 10.32; ISO/IEC 27031:2011.)*
- **4.3.2** Data centres **shall** meet the resilience expectations of RMiT 10.24–10.28 with documented redundancy in power, cooling, network, and physical access.

### 4.4 Backup and tamper-proof recovery

- **4.4.1** Information critical to business operation **shall** be backed up at frequencies aligned with the RPO defined per service, stored in geographically separate locations, encrypted, and tested for restorability at least annually. *(Implements RMiT 10.44.)*
- **4.4.2** A subset of backups **shall** be held in **tamper-proof / immutable** form with **isolated recovery** capability, sufficient to recover from destructive attacks affecting primary and secondary storage concurrently. *(Implements RMiT 10.45 — Tamper-Proof Backup and Isolated Recovery.)*

### 4.5 Testing

- **4.5.1** Business continuity and disaster recovery capabilities **shall** be tested at least annually for critical services, with progressive depth (component → service → end-to-end) over a multi-year programme.
- **4.5.2** Test outcomes, gaps, and remediation actions **shall** be reported to the Risk Management Committee.

### 4.6 Activation

- **4.6.1** Activation of the Business Continuity Plan or Disaster Recovery Plan **shall** follow defined triggers and authorities, integrated with the [Incident Response Plan](../05-plans/PLN-01-incident-response-plan.md) where the disruption originates from a security incident.

### 4.7 Supplier continuity

- **4.7.1** Material suppliers **shall** maintain continuity capability proportionate to their criticality, with evidence reviewed at least annually per [POL-19](POL-19-supplier-security-policy.md) and [TPRMF](../01-frameworks/TPRMF.md).

## 5. Roles and responsibilities

| Role | R | A | C | I |
|---|---|---|---|---|
| Risk Management Committee | | A | | I |
| COO | A | | C | |
| CISO | | | C | I |
| Head of IT Operations | R | | C | I |
| Service owners | R | | | I |

## 6. Exceptions

Per TRMF Section 12. Service-level RTO/RPO exceptions require RMC approval.

## 7. Enforcement

Per TRMF Section 12.

## 8. Related documents

- **Parent framework:** [BCMF](../01-frameworks/BCMF.md)
- **Related plans:** [PLN-02 Business Continuity Plan](../05-plans/PLN-02-business-continuity-plan.md); PLN-03 Disaster Recovery Plans (per service)
- **Related policies:** [POL-13](POL-13-incident-management-policy.md); [POL-15](POL-15-physical-and-environmental-security-policy.md); [POL-19](POL-19-supplier-security-policy.md)
- **Related register:** [REG-BIA Business Impact Analysis Register](../06-registers/REG-BIA-business-impact-analysis-register.md)

## 9. References

- BNM RMiT, 28 November 2025: Section 10.24–10.28; 10.29–10.35; 10.44–10.45
- BNM Business Continuity Management Policy Document
- COBIT 2019 — DSS04; DSS03
- ISO/IEC 22301:2019; ISO/IEC 27031:2011
- ISO/IEC 27002:2022 — controls 5.29, 5.30

## 10. Document control

| Version | Date | Author | Reviewer | Approver | Change summary |
|---|---|---|---|---|---|
| 1.0 | [Effective] | COO | RMC | RMC | Initial Effective version |
