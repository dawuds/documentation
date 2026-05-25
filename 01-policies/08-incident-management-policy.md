# Incident Management Policy

| | |
|---|---|
| **Document ID** | POL-08 |
| **Layer** | Policy (Tier 1) |
| **Owner** | CISO |
| **Approver** | Risk Management Committee |
| **Classification** | Internal |
| **Version** | 1.0 |
| **Effective date** | 2026-02-01 |
| **Next review** | 2027-02-01 (annual, or sooner on material incident or regulatory change) |
| **ISO/IEC 27002:2022 controls** | 5.24 (Incident management planning & preparation), 5.25 (Assessment & decision on events), 5.26 (Response to incidents), 5.27 (Learning from incidents), 5.28 (Collection of evidence) |
| **BNM RMiT** | §10.36–10.43 (Cybersecurity incident management) |

> This is the **second fully drafted policy** in this repo. It is the parent of the Incident Management worked cascade — see the related documents in §9.

---

## 1. Purpose

To define how General Bank prepares for, detects, classifies, responds to, recovers from, and learns from information security and technology incidents. The policy ensures that incidents are handled in a way that limits operational and reputational impact, preserves evidence, satisfies regulatory notification obligations, and drives improvement.

In a Malaysian licensed bank, incident response is a regulated discipline — Bank Negara Malaysia's *Risk Management in Technology (RMiT)* requires the Board to oversee cyber resilience and requires institutions to notify the regulator of material technology incidents on a defined timeline. The policy therefore covers both the operational mechanics of response and the governance and notification obligations that accompany them.

## 2. Scope

**Applies to:**

- All security events and incidents affecting General Bank information assets, systems, services, personnel, or third parties processing General Bank information.
- All incident severity levels, from low-severity events handled by tier-1 SOC analysts to material crises requiring CEO and Board engagement.
- All response phases, from detection through post-incident review.

**Does not apply to:**

- Operational incidents with no security impact (handled under the IT Service Management incident process). Where the boundary is unclear, the event is treated as a security incident until classified otherwise.
- Fraud incidents with no technology component (handled by the Fraud function under separate governance).

Cross-over events involving both fraud and a technology component are dual-tracked: this policy governs the technology incident response, and the Fraud Policy governs the fraud investigation.

## 3. Definitions

| Term | Definition |
|---|---|
| **Event** | An observable occurrence in a system or network. |
| **Security event** | An event that may have security significance. |
| **Incident** | One or more related security events that compromise or threaten to compromise the confidentiality, integrity, or availability of an information asset. |
| **Material technology incident** | An incident which, in the judgement of the CISO in consultation with the CRO, has or may have a significant adverse impact on the bank's operations, customers, reputation, or regulatory standing. See [STD-08-01](../02-standards/incident-classification-and-severity-standard.md) for the materiality criteria. |
| **Severity** | The classification of an incident on a defined scale (SEV-1 through SEV-4), determined by impact and urgency per [STD-08-01](../02-standards/incident-classification-and-severity-standard.md). |
| **Incident Commander (IC)** | The named individual coordinating response to a specific incident. Authority and rotation are defined in the [Incident Response Plan](../04-plans/incident-response-plan.md). |
| **Indicator of Compromise (IoC)** | A piece of forensic data — file hash, IP address, domain, URL, behavioural pattern — that identifies potentially malicious activity. |
| **Post-Incident Review (PIR)** | The structured analysis conducted after every SEV-1 and SEV-2 incident (and selectively for lower severities). |

## 4. Policy statements

### 4.1 Preparation

- **4.1.1** The bank shall maintain a documented [Incident Response Plan](../04-plans/incident-response-plan.md), reviewed at least annually and after every SEV-1 or SEV-2 incident. *(Implements ISO/IEC 27002:2022 control 5.24; BNM RMiT §10.36.)*
- **4.1.2** Incident response capability shall be staffed 24×7 either internally or through a contracted managed service, with documented escalation paths and on-call rotations.
- **4.1.3** The Incident Response Plan shall be **exercised** at least twice per year through tabletop exercises, with at least one annual functional exercise involving the executive team. *(Implements ISO/IEC 27002:2022 control 5.24; BNM RMiT §10.37.)*
- **4.1.4** Detection capability shall be maintained through a Security Operations Centre (SOC) function aligned with BNM RMiT Appendix 10 (Cybersecurity Operations Centre).

### 4.2 Detection, classification, and assessment

- **4.2.1** Every security event shall be triaged using the [Incident Triage SOP](../03-procedures/incident-triage-sop.md). *(Implements ISO/IEC 27002:2022 control 5.25.)*
- **4.2.2** Incidents shall be classified by severity using [STD-08-01 Incident Classification & Severity Standard](../02-standards/incident-classification-and-severity-standard.md). Severity drives notification, escalation, and response cadence.
- **4.2.3** All personnel shall be trained and obligated to report observed security events without delay through the channels published in the Acceptable Use Policy and the Incident Triage SOP. Reporting in good faith shall not result in adverse consequences for the reporter, even where the event proves to be benign or self-caused.
- **4.2.4** Detection sources shall include but not be limited to: SIEM, endpoint detection and response (EDR), network detection, DLP, fraud monitoring, regulator and threat-intelligence feeds, external researcher reports, and customer reports.

### 4.3 Response

- **4.3.1** Every confirmed incident shall be assigned an **Incident Commander** with clear authority to coordinate the response, request resources, and make containment decisions within the bounds defined in the Incident Response Plan. *(Implements ISO/IEC 27002:2022 control 5.26.)*
- **4.3.2** Response shall follow the structured phases of the Incident Response Plan: **Preparation → Detection & Analysis → Containment → Eradication → Recovery → Post-Incident**, adapted from NIST SP 800-61 Rev. 2.
- **4.3.3** Containment decisions shall balance evidence preservation, business continuity, and risk of further compromise. Containment that significantly impacts customer-facing services requires CEO or designated delegate approval, except where a defined "act now" pre-authorisation applies (specified in the Incident Response Plan).
- **4.3.4** All response actions shall be logged in the [Incident Register](../05-registers/incident-register.md) and timestamped, to support post-incident review and any subsequent forensic, legal, or regulatory examination.

### 4.4 Communication and notification

- **4.4.1** Internal communication during an incident shall follow the communication plan defined in the Incident Response Plan: clear designation of who briefs the Board, the executive team, employees, and other internal audiences.
- **4.4.2** **Customer notification** shall be made in accordance with applicable law (including the Personal Data Protection Act 2010 where personal data is affected) and on a basis approved by the CRO and the Chief Compliance Officer. Customer notifications shall be drafted in plain language and avoid unnecessary technical jargon.
- **4.4.3** **Regulator notification** — material technology incidents shall be notified to Bank Negara Malaysia in accordance with the notification timelines and form specified in **BNM RMiT §10** and any superseding circular. *(⚠ The specific notification windows under current RMiT — including any "without delay" / hour-based clock — must be verified against the live RMiT issuance and any subsequent BNM circulars. This policy intentionally does not embed a numerical clock here, to avoid reliance on a number that may have changed. The CISO and Chief Compliance Officer shall maintain the current notification timelines in an internal procedural reference.)*
- **4.4.4** **Public communication** (media, social channels, press) shall be coordinated by Corporate Communications under the direction of the CEO, with security input from the CISO and legal input from General Counsel. No member of the incident response team shall make public statements without authorisation.

### 4.5 Evidence

- **4.5.1** Evidence relating to incidents shall be collected, preserved, and handled in a manner that supports its admissibility in legal or regulatory proceedings. *(Implements ISO/IEC 27002:2022 control 5.28.)*
- **4.5.2** Chain of custody shall be maintained for forensic artefacts (disk images, memory captures, log extracts) from the point of collection.
- **4.5.3** Evidence handling shall follow forensic procedures specified by the CISO and aligned with applicable Malaysian law and recognised forensic practice (e.g., ISO/IEC 27037:2012 for digital evidence).

### 4.6 Recovery

- **4.6.1** Recovery shall be authorised by the Incident Commander only when the incident has been contained, the root cause identified or sufficiently understood to prevent recurrence in the recovered state, and the recovered state has been validated as free of indicators of compromise.
- **4.6.2** Recovery from incidents affecting critical business services shall align with the recovery time and recovery point objectives defined in [POL-09 Business Continuity Policy](09-business-continuity-policy.md).

### 4.7 Post-Incident Review (PIR)

- **4.7.1** A **Post-Incident Review** shall be conducted for every SEV-1 and SEV-2 incident within 15 working days of incident closure, and selectively for SEV-3 incidents at the discretion of the CISO. *(Implements ISO/IEC 27002:2022 control 5.27.)*
- **4.7.2** PIRs shall produce: a timeline, root cause analysis, an assessment of detection and response performance against thresholds in [STD-08-01](../02-standards/incident-classification-and-severity-standard.md), and a corrective and preventive action plan with named owners and due dates.
- **4.7.3** PIRs shall be **blameless** — focused on systemic and process learning, not individual fault — while preserving the bank's ability to take disciplinary action where wilful misconduct or gross negligence is established.
- **4.7.4** Material findings from PIRs shall be reported to the Risk Management Committee and, for SEV-1 incidents, to the Board.

### 4.8 Reporting

- **4.8.1** A consolidated incident report shall be presented to the Risk Management Committee quarterly, summarising incident volumes, severity distribution, mean time to detect (MTTD) and contain (MTTC), notable incidents, and the status of corrective actions.
- **4.8.2** The CISO shall maintain the [Incident Register](../05-registers/incident-register.md) as the authoritative record of all incidents.

## 5. Roles and responsibilities

| Role | R | A | C | I |
|---|---|---|---|---|
| Board / Risk Management Committee | | A | | I |
| CEO | | | C | I |
| CRO | | | C | I |
| Chief Compliance Officer | | | C | I |
| General Counsel | | | C | I |
| CISO | A | | | |
| Head of SOC | R | | C | I |
| Incident Commander (assigned per incident) | R | | | I |
| Corporate Communications | R | | C | I |
| All personnel | R (report) | | | I |

**Specific accountabilities:**

- **CISO** — Accountable for this policy, the Incident Response Plan, incident classification, and post-incident review quality. Final escalation point for security incident decisions short of CEO-level decisions.
- **Head of SOC** — Responsible for 24×7 detection, initial triage, and SEV-3/SEV-4 response.
- **Incident Commander** — Coordinates a specific incident response. Authority defined in the Incident Response Plan.
- **Corporate Communications** — Owns external and internal communications under CEO direction.
- **General Counsel** — Provides legal advice on notification obligations, evidence handling, and external communications.
- **Chief Compliance Officer** — Owns regulatory notification to BNM and any other applicable regulator.

## 6. Exceptions

Exceptions to this policy may be granted only in exceptional circumstances — for example, where notification timing or evidence handling is constrained by an active law-enforcement investigation. Exceptions require approval by the **Risk Management Committee** and shall be documented in the Exception Register with a defined end condition.

## 7. Enforcement

Failure to report a security event, interference with an incident investigation, or unauthorised disclosure of incident information may result in disciplinary action up to and including termination of employment or contract, and where applicable, civil or criminal proceedings.

## 8. Related documents

- **Parent:** [POL-00 Information Security Policy](00-information-security-policy.md)
- **Supporting standards:**
  - [STD-08-01 Incident Classification & Severity Standard](../02-standards/incident-classification-and-severity-standard.md)
- **Supporting procedures:**
  - [SOP-08-01 Incident Triage SOP](../03-procedures/incident-triage-sop.md)
- **Plans:**
  - [PLN-08-01 Incident Response Plan](../04-plans/incident-response-plan.md)
- **Related registers:**
  - [REG-INC Incident Register](../05-registers/incident-register.md)
- **Related policies:**
  - [POL-09 Business Continuity Policy](09-business-continuity-policy.md)
  - [POL-11 Operations Security Policy](11-operations-security-policy.md)

## 9. References

- ISO/IEC 27001:2022 — Information security management systems — Requirements.
- ISO/IEC 27002:2022 — Information security controls (5.24–5.28).
- ISO/IEC 27035-1:2023 — Information security incident management — Part 1: Principles and process.
- ISO/IEC 27037:2012 — Guidelines for identification, collection, acquisition and preservation of digital evidence.
- NIST SP 800-61 Rev. 2 — Computer Security Incident Handling Guide.
- Bank Negara Malaysia, *Risk Management in Technology (RMiT)*, §10 (Cybersecurity Management); §10.36–10.43 (incident management); Appendix 10 (Cybersecurity Operations Centre).
- Personal Data Protection Act 2010 (Malaysia) — notification of personal data breaches.

## 10. Document control

| Version | Date | Author | Reviewer | Approver | Change summary |
|---|---|---|---|---|---|
| 0.1–0.9 | 2025-11-20 → 2026-01-10 | CISO | Technology Risk, Compliance, Legal, SOC, Internal Audit | — | Drafting cycle |
| 1.0 | 2026-01-15 | CISO | Risk Management Committee | Risk Management Committee | Initial Effective version. Approved by RMC (minutes 2026-01-15, agenda item 6.1). |
