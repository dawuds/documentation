# STD-CR-02 — Logging Standard

| | |
|---|---|
| **Document ID** | STD-CR-02 | **Version** | 1.0 |
| **Owner / Approver** | CISO + Head of SOC / CISO |
| **Parent policy** | [POL-16](../02-policies/POL-16-operations-security-policy.md) | **Parent framework** | [CRMF](../01-frameworks/CRMF.md) / [TRMF](../01-frameworks/TRMF.md) |
| **RMiT clause(s)** | Section 10.42 (Network Device Log Retention); 10.57 (Access Monitoring and Logging); 11.9 |
| **COBIT** | DSS05; APO13 | **Practice** | ISO/IEC 27002:2022 control 8.15; NIST SP 800-92 |

## 1. Purpose
Specify what events shall be logged, in what format, with what retention, with what integrity protection, to support detection, forensics, audit, and regulator examinations.

## 2. Scope
All production systems generating security-relevant events — applications, infrastructure, network devices, cloud workloads, identity systems, security tooling.

## 3. Requirements

### 3.1 Mandatory event types per system class

| System class | Events to log (minimum) |
|---|---|
| Identity / IDP | Authentication success/failure; MFA events; password changes; account create/disable; privilege escalation; session creation/termination |
| Privileged Access Management (PAM) | Account check-out; session start/end; command execution; password rotation; emergency break-glass |
| Application | User action material to business; transactions; data access for Confidential+; admin actions; errors |
| Database | Schema changes; privileged queries; bulk data access; user account changes |
| Network devices (firewall, router) | Configuration changes; denied connections; allowed connections to security-sensitive zones |
| Endpoint (EDR) | Process execution (high-value); file modifications in security-sensitive paths; network connections; alerts |
| Cloud (control plane) | API calls; IAM changes; resource provisioning/decommissioning; encryption key access |
| Security tooling (SIEM, DLP, email gateway) | Alerts; configuration changes; rule modifications |

### 3.2 Event content

| Ref | Requirement |
|---|---|
| 3.2.1 | Every event shall include: timestamp (UTC, ISO 8601), source system, event type, actor identity (where applicable), action, resource affected, outcome (success/failure). |
| 3.2.2 | Sensitive data shall not be logged (passwords, full PANs, full personal data). |

### 3.3 Time synchronisation

| Ref | Requirement |
|---|---|
| 3.3.1 | All systems shall synchronise to authoritative GIBB NTP source, ultimately traceable to a stratum-1 source. |
| 3.3.2 | Drift > 30 seconds shall trigger alert. |

### 3.4 Collection and centralisation

| Ref | Requirement |
|---|---|
| 3.4.1 | Logs from in-scope systems shall be forwarded to the central SIEM within 5 minutes of generation. |
| 3.4.2 | Log forwarding failures shall trigger alert; gap of > 30 minutes is a security incident. |

### 3.5 Integrity protection

| Ref | Requirement |
|---|---|
| 3.5.1 | Logs at rest in the SIEM shall be cryptographically integrity-protected (HMAC or signed). |
| 3.5.2 | Access to delete or modify retained logs shall be restricted to dual-control admin roles; any such action shall itself be logged. |

### 3.6 Retention

| Log category | Minimum retention |
|---|---|
| Security event logs (alerts, IDP, PAM, EDR) | 7 years (BNM record-keeping aligned) |
| Network device logs | 7 years (RMiT 10.42) |
| Application transaction logs | 7 years |
| Operating system logs | 1 year hot; 7 years cold |
| Debug / verbose logs | 30–90 days (per system) |
| Customer transaction records (per banking law) | 7 years post-relationship |

### 3.7 Availability

| Ref | Requirement |
|---|---|
| 3.7.1 | Logs in retention shall be retrievable for investigation within 4 hours for the first 90 days, within 5 business days for older retention. |

### 3.8 Cloud-native logging

| Ref | Requirement |
|---|---|
| 3.8.1 | Cloud-native log services (CloudWatch, Azure Monitor, Cloud Logging) shall feed into the central SIEM via approved connectors. |
| 3.8.2 | Cloud-control-plane logs (CloudTrail equivalent) shall be enabled for every cloud account with multi-region delivery. |

## 4. Exceptions
Per [POL-16](../02-policies/POL-16-operations-security-policy.md). Reduced retention for cost reasons requires CRO approval.

## 5. Related documents
[POL-16](../02-policies/POL-16-operations-security-policy.md); [POL-13](../02-policies/POL-13-incident-management-policy.md); [POL-06](../02-policies/POL-06-access-control-policy.md); [CRMF](../01-frameworks/CRMF.md)

## 6. References
BNM RMiT 28 Nov 2025 Section 10.42; 10.57; 11.9; ISO/IEC 27002:2022 control 8.15; NIST SP 800-92; PCI DSS 4.0 Req 10 (where applicable).

## 7. Document control
| Version | Date | Author | Approver | Change |
|---|---|---|---|---|
| 1.0 | [Effective] | CISO + Head of SOC | CISO | Initial |
