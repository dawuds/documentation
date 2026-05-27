# Incident Classification & Severity Standard

| | |
|---|---|
| **Document ID** | STD-IR-01 |
| **Layer** | Standard (Tier 2) |
| **Owner** | CISO |
| **Approver** | CISO |
| **Classification** | Internal |
| **Version** | 1.0 |
| **Effective date** | 2026-02-01 |
| **Next review** | 2027-02-01 (annual or post-material-incident) |
| **Implements policy** | [POL-13 Incident Management Policy](../02-policies/POL-13-incident-management-policy.md) |
| **ISO/IEC 27002:2022 controls** | 5.25 (Assessment and decision on information security events), 5.26 (Response to information security incidents) |
| **BNM RMiT (28 Nov 2025)** | Section 11.12 (Cyber Crisis Management); Section 11.13 (Cyber Incident Response Plan); Section 11.18 (Cyber Incident Notification to BNM); Section 11.19 (Cyber Threat Intelligence Sharing); Section 11.20 (Stakeholder Collaboration on Cyber Threats) |
| **Parent framework(s)** | [CRMF](../01-frameworks/CRMF.md); parent policy [POL-13](../02-policies/POL-13-incident-management-policy.md) |
| **COBIT objective(s)** | DSS02; DSS05 |

---

## 1. Purpose

This standard defines **how GIBB classifies security incidents** by category and severity, the **performance thresholds** for detection and response by severity tier, and the **criteria for materiality** that drive executive escalation and regulator notification.

A consistent classification scheme is the foundation of incident management. Without it: severities are negotiated case-by-case (drift), reporting is incomparable across periods, post-incident learning is unfocused, and regulators receive inconsistent narratives. This standard removes those degrees of freedom.

## 2. Scope

All security events and incidents handled under [POL-13](../02-policies/POL-13-incident-management-policy.md). Operational (non-security) incidents are classified under the IT Service Management standard; events with overlap are classified as security incidents until proven otherwise.

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

Material incidents trigger executive engagement and regulator notification per [POL-13 Section 4.4](../02-policies/POL-13-incident-management-policy.md). SEV-1 incidents are **always** material. SEV-2 and SEV-3 incidents may be material based on the criteria above.

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

- **3.5.1** Material cyber incidents shall be notified to Bank Negara Malaysia in accordance with **BNM RMiT Section 11.18 (Cyber Incident Notification to BNM)**, which itself defers to BNM's *Operational Risk Reporting* policy document Part C, the *Business Continuity Management* policy document Part C, and (for merchant-acquiring incidents) the *Merchant Acquiring Services* policy paragraphs 19.25–19.26. **Operating expectation: notification within four (4) hours of detection of a material cyber incident.** *(⚠ The 4-hour figure is derived from BNM operational reporting practice for licensed FIs and surfaces in the institution's GRC structured-data artefact text tagged to RMiT clause 11.4; it is not stated numerically in RMiT Section 11.18 verbatim, which defers to the upstream policies above. The Chief Compliance Officer maintains the authoritative clock by reference to the current Operational Risk Reporting Part C and BCM Part C policy documents, and refreshes this standard on any change.)*
| **Parent framework(s)** | [CRMF](../01-frameworks/CRMF.md); parent policy [POL-13](../02-policies/POL-13-incident-management-policy.md) |
| **COBIT objective(s)** | DSS02; DSS05 |
- **3.5.2** Where the bank is designated as a **National Critical Information Infrastructure (NCII)** entity under the **Cyber Security Act 2024**, NACSA notification obligations apply additionally per **BNM RMiT Section 11.4**, with timelines and form per current NACSA directives for the financial sector.
| **Parent framework(s)** | [CRMF](../01-frameworks/CRMF.md); parent policy [POL-13](../02-policies/POL-13-incident-management-policy.md) |
| **COBIT objective(s)** | DSS02; DSS05 |
- **3.5.3** Cyber threat intelligence sharing with sector peers shall be conducted per **BNM RMiT Section 11.19**. Stakeholder collaboration on cyber threats shall be conducted per **BNM RMiT Section 11.20**.
| **Parent framework(s)** | [CRMF](../01-frameworks/CRMF.md); parent policy [POL-13](../02-policies/POL-13-incident-management-policy.md) |
| **COBIT objective(s)** | DSS02; DSS05 |
- **3.5.4** Personal data breaches shall be assessed against the requirements of the **Personal Data Protection Act 2010** and any applicable foreign data protection law.

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
- For SEV-1 and SEV-2 incidents — the **Post-Incident Review** has been scheduled (PIR completed within 15 working days of closure per POL-13 Section 4.7.1).

## 4. Exceptions

Severity downgrades require the Incident Commander's documented approval; severity downgrades on a SEV-1 or SEV-2 incident additionally require CISO sign-off.

## 5. Related documents

- **Parent policy:** [POL-13 Incident Management Policy](../02-policies/POL-13-incident-management-policy.md)
- **Implementing procedures:** [SOP-IR-01 Incident Triage SOP](../04-procedures/SOP-IR-01-incident-triage-sop.md)
- **Plans:** [PLN-01 Incident Response Plan](../05-plans/PLN-01-incident-response-plan.md)
- **Related registers:** [REG-INC Incident Register](../06-registers/REG-INC-incident-register.md)

## 6. References

- ISO/IEC 27002:2022 — controls 5.25, 5.26.
- ISO/IEC 27035-1:2023 — Incident management — Principles and process.
- NIST SP 800-61 Rev. 2 — Computer Security Incident Handling Guide.
- Bank Negara Malaysia, *Risk Management in Technology (RMiT)*, **28 November 2025 issuance** — Section 11.12–11.20 (Cyber Response, Recovery, Reporting, Sharing).
- Bank Negara Malaysia, *Operational Risk Reporting* policy document, Part C — authoritative source for cyber incident notification timing.
- Bank Negara Malaysia, *Business Continuity Management* policy document, Part C.
- Cyber Security Act 2024 (Malaysia) — NCII designation regime and NACSA directives.
- Personal Data Protection Act 2010 (Malaysia).
- [Regulatory Mapping Reference](../00-foundations/regulatory-mapping-reference.md).

## 7. Document control

| Version | Date | Author | Reviewer | Approver | Change summary |
|---|---|---|---|---|---|
| 1.0 | 2026-01-20 | CISO | Technology Risk, SOC, Compliance | CISO | Initial Effective version. |

---

## v2 re-anchoring (2026-05-28)

This document was re-anchored as part of the v2 build (Session 5) per [DEC-001](../_context/decisions.md). Substantive content preserved from the v1 snapshot at [`../v1/`](../v1/). Changes applied:

- Document ID updated to v2 numbering convention
- **Parent framework(s)** and **COBIT objective(s)** added to metadata block
- Bank name normalised from "General Bank" to **GIBB** (General Islamic Bank Berhad)
- Internal cross-references migrated from v1 paths to v2 paths
- v1 sister-document references updated to v2 document IDs

Pending formal GIBB approval under v2. The Effective and Next review dates above are inherited from the v1 1.x lifecycle and will be updated when this document is approved under v2 governance.
