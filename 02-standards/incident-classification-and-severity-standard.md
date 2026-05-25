# Incident Classification & Severity Standard

| | |
|---|---|
| **Document ID** | STD-08-01 |
| **Layer** | Standard (Tier 2) |
| **Owner** | CISO |
| **Approver** | CISO |
| **Classification** | Internal |
| **Version** | 1.0 |
| **Effective date** | 2026-02-01 |
| **Next review** | 2027-02-01 (annual or post-material-incident) |
| **Implements policy** | [POL-08 Incident Management Policy](../01-policies/08-incident-management-policy.md) |
| **ISO/IEC 27002:2022 controls** | 5.25 (Assessment and decision on information security events), 5.26 (Response to information security incidents) |
| **BNM RMiT** | §10.36–10.43 (incident management) |

---

## 1. Purpose

This standard defines **how General Bank classifies security incidents** by category and severity, the **performance thresholds** for detection and response by severity tier, and the **criteria for materiality** that drive executive escalation and regulator notification.

A consistent classification scheme is the foundation of incident management. Without it: severities are negotiated case-by-case (drift), reporting is incomparable across periods, post-incident learning is unfocused, and regulators receive inconsistent narratives. This standard removes those degrees of freedom.

## 2. Scope

All security events and incidents handled under [POL-08](../01-policies/08-incident-management-policy.md). Operational (non-security) incidents are classified under the IT Service Management standard; events with overlap are classified as security incidents until proven otherwise.

## 3. Requirements

### 3.1 Severity definitions

| Severity | Definition | Examples (illustrative — not exhaustive) |
|---|---|---|
| **SEV-1 — Critical** | Confirmed or strongly suspected material compromise; or significant operational impact on critical customer-facing services; or significant data confidentiality breach involving Confidential or Highly Restricted data; or sustained outage of a critical service. | Confirmed ransomware in production estate; confirmed exfiltration of customer data; compromise of a Tier-0 administrative account; sustained outage of internet banking. |
| **SEV-2 — High** | Confirmed compromise of a non-critical asset; or material near-miss on a critical asset; or significant suspicious activity requiring active response; or extended degradation of a critical service. | Confirmed phishing leading to single-account compromise (non-privileged); successful network intrusion contained at perimeter; break-glass credential usage outside agreed scenarios. |
| **SEV-3 — Medium** | Localised security event with active response required; no confirmed compromise of Confidential or higher data; limited operational impact. | Targeted phishing campaign with no confirmed click; malware contained at endpoint by EDR; unauthorised access attempt by terminated employee (blocked). |
| **SEV-4 — Low** | Routine security event triaged and closed within SOC standard handling. | Generic phishing detected and blocked at email gateway; failed brute-force attempt; policy violation requiring user follow-up. |

### 3.2 Materiality determination

An incident is **material** (regardless of severity tier above) where **any one** of the following is true:

| Materiality criterion | Notes |
|---|---|
| Customer data confidentiality is or may have been breached | Personal data, account data, transaction data. Triggers PDPA assessment. |
| A critical customer-facing service is unavailable for more than 30 minutes | RTO-aligned threshold; consult BCP for service classification. |
| A bank insider with Tier-0 access is implicated | Whether confirmed compromise or strong suspicion. |
| Funds movement integrity is or may have been impacted | Includes payment systems, settlement, treasury. |
| Regulator notification is required under BNM RMiT, PDPA, or other applicable obligation | Notification trigger derived from law/regulation, not from internal severity. |
| Material reputational risk (media, social, customer complaint volume) is realised or imminent | Judgement of CRO + Corporate Communications. |

Material incidents trigger executive engagement and regulator notification per [POL-08 §4.4](../01-policies/08-incident-management-policy.md). SEV-1 incidents are **always** material. SEV-2 and SEV-3 incidents may be material based on the criteria above.

### 3.3 Detection and response thresholds

| Severity | Mean Time to Detect (MTTD) target | Mean Time to Acknowledge (MTTA) target | Mean Time to Contain (MTTC) target |
|---|---|---|---|
| SEV-1 | ≤ 30 minutes | ≤ 15 minutes from detection | ≤ 4 hours from detection |
| SEV-2 | ≤ 2 hours | ≤ 30 minutes from detection | ≤ 12 hours from detection |
| SEV-3 | ≤ 8 hours | ≤ 2 hours from detection | ≤ 48 hours from detection |
| SEV-4 | ≤ 24 hours | ≤ 8 hours from detection | Per SOC handling |

These are targets, not guarantees. Variance is tracked and reported quarterly to the Risk Management Committee. Sustained failure to meet targets is treated as a control deficiency.

### 3.4 Escalation matrix

| Severity | First responder | Incident Commander | Executive notification | Board notification |
|---|---|---|---|---|
| SEV-1 | SOC | Head of SOC initially → CISO assumes IC role | CEO, CRO, CCO, General Counsel — within MTTA | Yes — Board Chair informed; full Board updated as appropriate |
| SEV-2 | SOC | Head of SOC | CISO, CRO; CEO if material | RMC at next meeting; Board if material |
| SEV-3 | SOC | SOC Shift Lead | CISO informed | RMC consolidated report |
| SEV-4 | SOC | SOC analyst | n/a | Aggregated metrics in quarterly report |

### 3.5 Regulator notification

- **3.5.1** Material technology incidents shall be notified to Bank Negara Malaysia in accordance with BNM RMiT §10 and any superseding circular. *(⚠ Specific notification clocks under current RMiT — including any "without delay" or hour-based clock for major incidents — must be verified against the live RMiT issuance and any subsequent BNM circulars. The CISO, in coordination with the Chief Compliance Officer, maintains the current notification clocks as an internal procedural reference.)*
- **3.5.2** Personal data breaches shall be assessed against the requirements of the Personal Data Protection Act 2010 and any applicable foreign data protection law.

### 3.6 Categorisation

In addition to severity, every incident shall be tagged with at least one **category** to support trend analysis:

| Category | Description |
|---|---|
| `phishing` | Email, SMS, voice, or social-engineering attack |
| `malware` | Including ransomware, banking trojans, commodity malware |
| `unauthorised-access` | Including credential abuse, brute force, session hijacking |
| `insider` | Authorised user misusing access |
| `data-loss` | Confidentiality breach (intentional or accidental) |
| `availability` | DDoS, service degradation, infrastructure failure with security relevance |
| `third-party` | Originating in or affecting a supplier |
| `physical` | Theft, loss of device, unauthorised premises access |
| `policy-violation` | Confirmed breach of policy not falling above |

### 3.7 Closure criteria

An incident may be closed when:

- The incident is **contained** (no further spread possible).
- The **root cause** has been identified or is sufficiently understood for the recovered state.
- **Recovery** is complete to a state validated free of indicators of compromise.
- Required **notifications** have been made.
- **Corrective and preventive actions** have been assigned to named owners with due dates.
- For SEV-1 and SEV-2 incidents — the **Post-Incident Review** has been scheduled (PIR completed within 15 working days of closure per POL-08 §4.7.1).

## 4. Exceptions

Severity downgrades require the Incident Commander's documented approval; severity downgrades on a SEV-1 or SEV-2 incident additionally require CISO sign-off.

## 5. Related documents

- **Parent policy:** [POL-08 Incident Management Policy](../01-policies/08-incident-management-policy.md)
- **Implementing procedures:** [SOP-08-01 Incident Triage SOP](../03-procedures/incident-triage-sop.md)
- **Plans:** [PLN-08-01 Incident Response Plan](../04-plans/incident-response-plan.md)
- **Related registers:** [REG-INC Incident Register](../05-registers/incident-register.md)

## 6. References

- ISO/IEC 27002:2022 — controls 5.25, 5.26.
- ISO/IEC 27035-1:2023 — Incident management — Principles and process.
- NIST SP 800-61 Rev. 2 — Computer Security Incident Handling Guide.
- Bank Negara Malaysia, *Risk Management in Technology (RMiT)*, §10.36–10.43, Appendix 10.
- Personal Data Protection Act 2010 (Malaysia).

## 7. Document control

| Version | Date | Author | Reviewer | Approver | Change summary |
|---|---|---|---|---|---|
| 1.0 | 2026-01-20 | CISO | Technology Risk, SOC, Compliance | CISO | Initial Effective version. |
