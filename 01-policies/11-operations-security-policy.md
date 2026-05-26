# Operations Security Policy

| | |
|---|---|
| **Document ID** | POL-11 |
| **Layer** | Policy (Tier 1) |
| **Owner** | Head of IT Operations (joint with CISO) |
| **Approver** | Risk Management Committee |
| **Classification** | Internal |
| **Version** | 1.0 |
| **Effective date** | 2026-02-01 |
| **Next review** | 2027-02-01 |
| **ISO/IEC 27002:2022 controls** | 8.6 (Capacity management), 8.7 (Protection against malware), 8.13 (Information backup), 8.15 (Logging), 8.16 (Monitoring activities), 8.32 (Change management) |
| **BNM RMiT (28 Nov 2025)** | Section 10 (Technology Operations Management) — across change, backup, network resilience; Section 11.9 (Continuous Security Monitoring and SOC); Section 11.10 (Cyber Threat Intelligence); Section 11.11 (Anomalous Activity Response) |

> Skeleton policy. Aggregates several operational domains that often each have their own policy in larger organisations. Suitable for a mid-sized bank; split per-domain as scale and audit pressure demand.

---

## 1. Purpose

To define the operational controls applied across the running estate — change management, capacity, backup, logging, monitoring, malware protection — that maintain the secure and reliable operation of General Bank information services.

## 2. Scope

All production information systems and services, including those operated by third parties on the bank's behalf.

## 3. Policy statements

### 3.1 Change management

- **3.3.1** Changes to production systems shall be authorised, assessed for security and operational risk, tested, scheduled, communicated, and recorded. Emergency changes shall be limited to genuine emergencies and reviewed retrospectively. *(Implements ISO/IEC 27002:2022 control 8.32.)*

### 3.2 Capacity management

- **3.2.1** Capacity of critical services shall be monitored and forecasted, with capacity additions planned to maintain agreed service levels. *(Implements ISO/IEC 27002:2022 control 8.6.)*

### 3.3 Malware protection

- **3.3.1** Endpoint and server systems shall run approved endpoint protection (EDR / anti-malware) with current definitions, centrally managed and monitored. *(Implements ISO/IEC 27002:2022 control 8.7; BNM RMiT Section 11.5 (Cybersecurity Control Measures, implementing Appendix 5).)*

### 3.4 Backup

- **3.4.1** Information critical to business operation shall be backed up at frequencies aligned with the RPO defined per service, stored in geographically separate locations, encrypted, and tested for restorability at least annually. *(Implements ISO/IEC 27002:2022 control 8.13; BNM RMiT Section 10.44 (Backup Strategy and Procedures).)*
- **3.4.2** A subset of backups shall be held in **immutable / tamper-proof** form with an isolated recovery capability, to provide recovery in the event of ransomware affecting primary and secondary storage. *(BNM RMiT Section 10.45 (Tamper-Proof Backup and Isolated Recovery).)*

### 3.5 Logging

- **3.5.1** Security-relevant events shall be logged with sufficient detail to support detection, investigation, and forensics. Logs shall be centrally collected, time-synchronised, protected from tampering, and retained per the records retention schedule. *(Implements ISO/IEC 27002:2022 control 8.15.)*

### 3.6 Monitoring

- **3.6.1** Centralised security monitoring shall operate 24×7 through a **Security Operations Centre (SOC)** as required by BNM RMiT Section 11.9 (Continuous Security Monitoring and SOC). The SOC shall be supported by competent resources and necessary tooling, its monitoring scope shall cover all critical systems and supporting infrastructure, and it shall conduct regular vulnerability assessment and penetration testing in line with Appendix 5. **Cyber threat intelligence** shall be operated per Section 11.10. **Anomalous activity response** shall be operationalised per Section 11.11. Detection use cases shall be maintained, tuned, and tested. *(Implements ISO/IEC 27002:2022 control 8.16; BNM RMiT Section 11.9; Section 11.10; Section 11.11.)*

### 3.7 Time synchronisation

- **3.7.1** Systems shall synchronise to an authoritative time source. (Implements ISO/IEC 27002:2022 control 8.17 — not in this policy's primary control list but operationally tied.)

## 4. Roles and responsibilities

| Role | R | A | C | I |
|---|---|---|---|---|
| Risk Management Committee | | A | | I |
| Head of IT Operations | A | | C | |
| CISO | | | C (joint A on monitoring) | I |
| Service owners | R | | | I |
| SOC | R | | C | I |

## 5. Exceptions

Per [POL-00](00-information-security-policy.md). Bypass of change management requires post-event review and CISO sign-off.

## 6. Enforcement

Per [POL-00](00-information-security-policy.md).

## 7. Related documents

[POL-00](00-information-security-policy.md), [POL-08](08-incident-management-policy.md), [POL-09](09-business-continuity-policy.md), [POL-13](13-vulnerability-management-policy.md).

## 8. References

ISO/IEC 27002:2022 — controls 8.6, 8.7, 8.13, 8.15, 8.16, 8.32. BNM RMiT (28 Nov 2025) Section 10 (Technology Operations Management); Section 11.5; Section 11.9–11.11. [Regulatory Mapping Reference](../00-foundations/regulatory-mapping-reference.md).

## 9. Document control

| Version | Date | Author | Reviewer | Approver | Change summary |
|---|---|---|---|---|---|
| 1.0 | 2026-01-15 | Head of IT Ops + CISO | Risk Management Committee | Risk Management Committee | Initial Effective version (skeleton). |
