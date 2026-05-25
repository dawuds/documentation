# Business Continuity Policy

| | |
|---|---|
| **Document ID** | POL-09 |
| **Layer** | Policy (Tier 1) |
| **Owner** | COO |
| **Approver** | Risk Management Committee |
| **Classification** | Internal |
| **Version** | 1.0 |
| **Effective date** | 2026-02-01 |
| **Next review** | 2027-02-01 |
| **ISO/IEC 27002:2022 controls** | 5.29 (Information security during disruption), 5.30 (ICT readiness for business continuity) |
| **BNM RMiT** | Appendix 3 (Data Centre Resilience); also addresses business continuity and disaster recovery expectations across §8–§10 |

> Skeleton policy. The Business Continuity Plan, Disaster Recovery Plan, and Business Impact Analysis methodology sit beneath this policy and are not included here.

---

## 1. Purpose

To establish the requirements for sustaining the bank's critical business services through disruption — whether arising from technology failure, cybersecurity incident, natural event, supplier failure, or other cause — and to define the governance of business continuity and disaster recovery.

## 2. Scope

All business services, supporting systems, suppliers, personnel, and locations relied upon to deliver General Bank's services to customers, regulators, and other stakeholders.

## 3. Policy statements

### 3.1 Business Impact Analysis (BIA)

- **3.1.1** A Business Impact Analysis shall be conducted at least annually, identifying critical business services, their dependencies, and the maximum tolerable period of disruption (MTPD), recovery time objectives (RTO), and recovery point objectives (RPO).

### 3.2 Continuity strategy

- **3.2.1** Continuity strategies (alternate sites, alternate suppliers, manual workarounds, technology failover) shall be defined per critical service, proportionate to the impact tolerance from the BIA. *(Implements ISO/IEC 27002:2022 control 5.29.)*

### 3.3 ICT readiness

- **3.3.1** ICT services supporting critical business services shall be designed to meet the RTO and RPO defined for each, with documented architecture, data replication, and failover procedures. *(Implements ISO/IEC 27002:2022 control 5.30; BNM RMiT Appendix 3.)*
- **3.3.2** Data centres shall meet the resilience expectations of BNM RMiT Appendix 3, with documented redundancy in power, cooling, network, and physical access.

### 3.4 Testing

- **3.4.1** Business continuity and disaster recovery capabilities shall be tested at least annually for critical services, with progressive depth (component test → service test → end-to-end exercise) over a multi-year programme.
- **3.4.2** Test outcomes, gaps, and remediation actions shall be reported to the Risk Management Committee.

### 3.5 Activation

- **3.5.1** Activation of the Business Continuity Plan or Disaster Recovery Plan shall follow defined triggers and authorities, integrated with the [Incident Response Plan](../04-plans/incident-response-plan.md) where the disruption originates from a security incident.

### 3.6 Supplier continuity

- **3.6.1** Material suppliers shall be required to maintain continuity capability proportionate to their criticality, with evidence reviewed at least annually.

## 4. Roles and responsibilities

| Role | R | A | C | I |
|---|---|---|---|---|
| Risk Management Committee | | A | | I |
| COO | A | | C | |
| CISO | | | C | I |
| Head of IT Operations | R | | C | I |
| Business service owners | R | | | I |

## 5. Exceptions

Per [POL-00](00-information-security-policy.md). Service-level RTO/RPO exceptions require Risk Management Committee approval.

## 6. Enforcement

Per [POL-00](00-information-security-policy.md).

## 7. Related documents

[POL-00](00-information-security-policy.md), [POL-07](07-supplier-security-policy.md), [POL-08](08-incident-management-policy.md), [POL-10](10-physical-security-policy.md).

## 8. References

ISO/IEC 27002:2022 — controls 5.29, 5.30. ISO 22301:2019 (Business Continuity Management Systems). BNM RMiT Appendix 3.

## 9. Document control

| Version | Date | Author | Reviewer | Approver | Change summary |
|---|---|---|---|---|---|
| 1.0 | 2026-01-15 | COO | Risk Management Committee | Risk Management Committee | Initial Effective version (skeleton). |
