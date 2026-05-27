# POL-16 — Operations Security Policy

| | |
|---|---|
| **Document ID** | POL-16 |
| **Layer** | Policy (Tier 1) |
| **Version** | 1.0 |
| **Owner** | Chief Information Officer + CISO (joint) |
| **Approver** | Risk Management Committee |
| **Classification** | Internal |
| **Effective** | [Effective] |
| **Next review** | Annual |
| **Parent framework(s)** | [TRMF](../01-frameworks/TRMF.md); secondary [CRMF](../01-frameworks/CRMF.md) |
| **RMiT clause(s)** | Section 10 in entirety (Technology Operations Management); 10.36–10.43 (Network Resilience); 10.44–10.45 (Backup); 11.9 (SOC); 11.10 (Threat Intel); 11.11 (Anomalous Activity); cross-reference 10.11 (change) |
| **COBIT objective(s)** | DSS01 Managed Operations; DSS02 Managed Service Requests and Incidents; DSS05 Managed Security Services |
| **Practice standard(s)** | ITIL 4 (Event Management, Monitoring and Event Management, Service Desk, Infrastructure and Platform Management practices); ISO/IEC 27002:2022 controls 8.6, 8.7, 8.13, 8.15, 8.16, 8.17, 8.32 |

---

## 1. Purpose

To define the operational controls applied across the running technology estate — capacity, malware protection, backup, logging, monitoring, time-sync, network operations — that maintain secure and reliable operation. Operations Security is the day-to-day operating discipline that sustains the controls established by other policies.

## 2. Scope

All production information systems and services, including those operated by third parties on the bank's behalf.

## 3. Definitions

| Term | Definition |
|---|---|
| **Operations** | Day-to-day running of technology services. |
| **SOC** | Security Operations Centre per RMiT 11.9 — the bank's 24×7 cyber monitoring and response function. |
| **Threat intelligence** | Information about cyber threats relevant to GIBB, consumed for proactive defence. |

## 4. Policy statements

### 4.1 Change management

- **4.1.1** Changes to production systems **shall** follow the [POL-07 Change Management Policy](POL-07-change-management-policy.md). *(Implements RMiT 10.11; ISO/IEC 27002:2022 control 8.32.)*

### 4.2 Capacity management

- **4.2.1** Capacity of critical services **shall** be managed per [POL-08 Capacity and Performance Management Policy](POL-08-capacity-and-performance-management-policy.md). *(Implements RMiT 10.29–10.31; COBIT BAI04.)*

### 4.3 Malware protection

- **4.3.1** Endpoint and server systems **shall** run approved endpoint protection (EDR / anti-malware) with current definitions, centrally managed and monitored. *(Implements ISO/IEC 27002:2022 control 8.7; RMiT 11.5 + Appendix 5.)*

### 4.4 Backup and recovery

- **4.4.1** Information critical to business operation **shall** be backed up per RPO defined per service, stored in geographically separate locations, encrypted, and tested for restorability at least annually. *(Implements RMiT 10.44; ISO/IEC 27002:2022 control 8.13.)*
- **4.4.2** A subset of backups **shall** be held in **tamper-proof / immutable** form with isolated recovery capability per RMiT 10.45. *(Implements RMiT 10.45.)*

### 4.5 Logging

- **4.5.1** Security-relevant events **shall** be logged with sufficient detail for detection, investigation, and forensics. Logs **shall** be centrally collected, time-synchronised, protected from tampering, and retained per records retention. *(Implements ISO/IEC 27002:2022 control 8.15; RMiT 10.42 — network device log retention.)*

### 4.6 Monitoring

- **4.6.1** Centralised security monitoring **shall** operate 24×7 through the SOC per RMiT 11.9 — supported by competent resources and equipped with necessary tooling, covering all critical systems and supporting infrastructure. *(Implements ISO/IEC 27002:2022 control 8.16; RMiT 11.9.)*
- **4.6.2** **Cyber threat intelligence** **shall** be operated per RMiT 11.10.
- **4.6.3** **Anomalous activity** **shall** be responded to per RMiT 11.11 and the [Incident Triage SOP](../04-procedures/incident-triage-sop.md).

### 4.7 Time synchronisation

- **4.7.1** Systems **shall** synchronise to an authoritative time source. *(Implements ISO/IEC 27002:2022 control 8.17.)*

### 4.8 Network resilience and security

- **4.8.1** Network design, services, and security **shall** comply with RMiT 10.36–10.43 (Network Resilience) — including enterprise network design, network fault prevention, network security for critical systems, network design blueprint, network device log retention, and network segmentation safeguards. *(Implements RMiT 10.36–10.43.)*

### 4.9 Service request and incident operations

- **4.9.1** Service request and incident operations **shall** follow ITIL-aligned service management practices and the [POL-13 Incident Management Policy](POL-13-incident-management-policy.md) for security incidents. *(Implements COBIT DSS02.)*

## 5. Roles and responsibilities

| Role | R | A | C | I |
|---|---|---|---|---|
| Risk Management Committee | | A | | |
| CIO | A (operations) | | C | |
| CISO | | A (SOC, threat intel, anomalous activity) | C | |
| Head of IT Operations | R | | C | I |
| Head of SOC | R (SOC operations) | | C | I |
| Head of Network | R (network) | | C | I |
| Service owners | R | | | I |

## 6. Exceptions

Per TRMF Section 12. Bypass of change management or backup discipline requires post-event review and CISO + CIO sign-off.

## 7. Enforcement

Per TRMF Section 12.

## 8. Related documents

- **Parent framework:** [TRMF](../01-frameworks/TRMF.md); [CRMF](../01-frameworks/CRMF.md)
- **Related policies:** [POL-07](POL-07-change-management-policy.md); [POL-08](POL-08-capacity-and-performance-management-policy.md); [POL-13 Incident Management Policy](POL-13-incident-management-policy.md); [POL-14 Business Continuity Policy](POL-14-business-continuity-policy.md); [POL-18 Vulnerability and Patch Management Policy](POL-18-vulnerability-management-policy.md)

## 9. References

- BNM RMiT, 28 November 2025: Section 10 in entirety; Section 11.9, 11.10, 11.11
- COBIT 2019 — DSS01; DSS02; DSS05
- ITIL 4 — Service Desk; Event Management; Monitoring and Event Management; Infrastructure and Platform Management; Service Configuration Management
- ISO/IEC 27002:2022 — controls 8.6, 8.7, 8.13, 8.15, 8.16, 8.17, 8.32

## 10. Document control

| Version | Date | Author | Reviewer | Approver | Change summary |
|---|---|---|---|---|---|
| 1.0 | [Effective] | CIO + CISO | RMC | RMC | Initial Effective version |
