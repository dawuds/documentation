# Incident Response Plan

| | |
|---|---|
| **Document ID** | PLN-08-01 |
| **Layer** | Plan |
| **Owner** | CISO |
| **Approver** | Risk Management Committee |
| **Classification** | Internal — restricted |
| **Version** | 1.0 |
| **Effective date** | 2026-02-01 |
| **Next review** | 2027-02-01 (annual; immediately following any SEV-1 incident) |
| **Implements policy** | [POL-08 Incident Management Policy](../01-policies/08-incident-management-policy.md) |
| **Aligned with** | NIST SP 800-61 Rev. 2 (Computer Security Incident Handling Guide); ISO/IEC 27035-1:2023 |

> **Distribution.** This plan is *Internal — restricted*. The on-call card extracted from §4 and §5 is distributed to the response team via the secure on-call platform. Full plan distribution is to: CISO, CEO, CRO, CCO, General Counsel, COO, Head of SOC, Head of IT Ops, Corporate Communications, RMC members. Quarterly review confirms distribution list currency.

---

## 1. Purpose

To define how General Bank responds to confirmed security incidents — specifically SEV-1 and SEV-2 incidents under [STD-08-01](../02-standards/incident-classification-and-severity-standard.md) — from declaration through post-incident review. The Plan operationalises [POL-08 §4.3](../01-policies/08-incident-management-policy.md) and picks up where the [Incident Triage SOP](../03-procedures/incident-triage-sop.md) hands off.

## 2. Scope

**In scope:**

- All declared SEV-1 and SEV-2 incidents.
- Selected SEV-3 incidents at the discretion of the CISO (typically those with regulatory or reputational potential).

**Out of scope:**

- Triage of unconfirmed events — covered by [SOP-08-01](../03-procedures/incident-triage-sop.md).
- Business continuity activation arising from non-security disruption — covered by the Business Continuity Plan under [POL-09](../01-policies/09-business-continuity-policy.md).
- Routine SEV-4 handling — covered by SOC standard handling.

## 3. Activation

| Trigger | Authority to activate |
|---|---|
| SEV-1 declared during triage | Head of SOC initiates; CISO confirms and assumes IC. |
| SEV-2 declared during triage | Head of SOC initiates and assumes IC; CISO informed. |
| SEV-3 retrospectively assessed as material | CISO. |
| External notification of confirmed compromise (regulator, law enforcement, vendor) | CISO. |

Activation creates: (a) an Incident Register entry, (b) an incident bridge, (c) an assigned Incident Commander, (d) a tracked timeline. From the moment of activation all response activity is timestamped.

## 4. Roles and contacts

| Role | Default holder | Alternate | Contact (out-of-band — for use if primary systems compromised) |
|---|---|---|---|
| **Incident Commander — SEV-1** | CISO | Deputy CISO; rotational CISO-delegate per on-call card | Mobile phone + signal application + physical on-call card |
| **Incident Commander — SEV-2** | Head of SOC | Deputy Head of SOC; CISO if escalated | Mobile + on-call card |
| **SOC Lead** | Head of SOC | SOC Shift Lead | Per shift |
| **Technical Lead (per affected domain)** | Domain lead | Per on-call card | Mobile + on-call card |
| **Communications Lead** | Head of Corporate Communications | Deputy | Mobile + email |
| **Legal Lead** | General Counsel | Deputy GC | Mobile + email |
| **Compliance Lead** | Chief Compliance Officer | Deputy CCO | Mobile + email |
| **Executive Sponsor — SEV-1** | CEO | CRO if CEO unavailable | Mobile + secure channel |
| **Board contact** | Board Chair | Chair of Board Risk Committee | Mobile via Company Secretary |

Out-of-band contacts are tested as part of the quarterly tabletop. Out-of-band channels are documented on physical on-call cards held by named individuals — not stored solely in systems that may be impacted by an incident.

## 5. Response phases (NIST SP 800-61 Rev. 2 aligned)

### 5.1 Preparation

(Continuous, not per-incident.)

- IRP reviewed annually and after every SEV-1.
- Tabletop exercise quarterly; functional / simulation exercise annually with executive engagement.
- On-call rotation maintained and tested monthly (call-out drills).
- Response tooling (SOAR, EDR, forensic kit, conferencing) tested quarterly.
- Threat-intelligence feeds, regulator contacts, and supplier escalation paths maintained current.

### 5.2 Detection and Analysis

Inherited from [SOP-08-01](../03-procedures/incident-triage-sop.md). On activation, the Incident Commander:

- Confirms severity per [STD-08-01](../02-standards/incident-classification-and-severity-standard.md).
- Confirms initial scope (affected assets, data, users, services).
- Opens incident bridge; convenes core response team.
- Assigns: SOC Lead, Technical Lead(s), Communications Lead, Legal Lead, Compliance Lead.
- Establishes timeline cadence (typically 30-min status checks for SEV-1, 60-min for SEV-2).
- Decides on engagement of external forensic / IR retainer (if applicable).

**Decision gate:** **Is the incident in scope of regulator notification?** If yes, Compliance Lead initiates notification process in parallel (see §6).

### 5.3 Containment

The IC selects a containment strategy:

| Strategy | When chosen |
|---|---|
| **Short-term — minimise impact, preserve evidence** | Default for SEV-1 unless eradication is straightforward. |
| **Long-term — sustainable containment while preparing eradication** | When eradication requires significant planning (e.g., re-imaging large estate). |
| **Permit-and-observe** | Rare; only with CISO + General Counsel agreement, typically for active adversary characterisation under law-enforcement guidance. |

Containment actions exceeding the pre-authorisations in [SOP-08-01 §5.4](../03-procedures/incident-triage-sop.md) require IC approval (logged), or CEO/designate approval for customer-impacting actions.

**Decision gate:** **Has containment been validated?** Evidence: targeted detection rules show no further indicators of compromise activity; affected assets isolated or removed.

### 5.4 Eradication

- Root cause analysis sufficient to ensure recovered state will not be re-infected.
- Removal of malicious artefacts (files, accounts, persistence mechanisms, lateral footholds).
- Credential rotation for any compromised or potentially compromised credentials, including service accounts and break-glass.
- Patching or compensating control for the exploited vulnerability (handed to vulnerability management for tracking).

**Decision gate:** **Has eradication completed?** Evidence: independent verification (different analyst from initial responder) confirms no remaining indicators.

### 5.5 Recovery

- Recovery to production validated against detection rules and a hardening check (no remaining IoCs).
- Phased return to service where impact justifies (e.g., one branch then estate).
- Customer-facing return-to-service decision made jointly by IC, CEO/designate, and Communications Lead, considering customer experience, reputational, and detection-confidence factors.
- Enhanced monitoring period defined (typically 30 days) before declaring incident closed.

**Decision gate:** **Has recovery completed and the enhanced monitoring period passed without incident recurrence?**

### 5.6 Post-Incident

- Post-Incident Review (PIR) scheduled per [POL-08 §4.7](../01-policies/08-incident-management-policy.md) — within 15 working days of incident closure for SEV-1 and SEV-2.
- Lessons learned recorded; corrective and preventive actions assigned with named owners and due dates.
- IRP updated if response gaps identified.
- Detection and prevention controls updated if applicable.
- Board / RMC briefing prepared.

## 6. Communication

| Audience | Trigger | Channel | Owner | Timeline |
|---|---|---|---|---|
| Internal — Response team | Activation | Incident bridge + secure messaging channel | IC | Immediate. |
| Internal — Executive team (CEO, CRO, CCO, GC) | SEV-1: immediate; SEV-2: within 30 min of activation if material | Direct call + bridge invite | IC | Per severity. |
| Internal — Board Chair | SEV-1: immediate notification of activation | Via Company Secretary | CEO | Immediate on activation. |
| Internal — Risk Management Committee | SEV-1: within 4 hours of activation; SEV-2: within 24 hours | Email brief + offer of bridge | CISO | Per timing. |
| Internal — All staff | If staff action required (e.g., do-not-click, password change), or to provide context for visible disruption | Internal communication channels | Communications Lead, with CISO security input | As warranted; avoid speculation. |
| External — Regulator (Bank Negara Malaysia) | Material technology incident per BNM RMiT §10 | Per BNM's prescribed channels (verify current notification timelines and form against the live RMiT issuance and any superseding circular) | Chief Compliance Officer | Per regulatory clock — ⚠ specific clocks not pinned in this Plan; CCO maintains the current notification clocks as an internal procedural reference. |
| External — Affected customers (where personal data affected) | Per Personal Data Protection Act 2010 assessment | Direct customer channel (email, SMS, secure message in app) | Communications Lead, with Legal sign-off | Without undue delay following assessment. |
| External — Media / public | Decision made jointly by CEO, CISO, Communications Lead, GC | Press statement, social channels | Communications Lead under CEO direction | As decided. |
| External — Law enforcement | If criminal activity suspected; CISO + GC decision | Per established law-enforcement liaison contact | CISO + General Counsel | As decided. |
| External — Threat-sharing community / sector CERT | Where threat intelligence sharing is appropriate | Established sharing channels | CISO | As decided. |

A single Communications Lead is responsible for ensuring that all external communications are consistent and that no member of the response team makes public statements without authorisation.

## 7. Testing and exercise

| Frequency | Type | Owner |
|---|---|---|
| **Monthly** | On-call rotation call-out drill | Head of SOC |
| **Quarterly** | Tabletop exercise — scenario rotates across categories (ransomware, insider, supplier compromise, data exfiltration, payment-system compromise) | CISO |
| **Annually** | Functional / simulation exercise involving executive team and (selectively) Board observation | CISO + CEO |
| **Annually (overlap with BCP)** | Joint IRP/BCP/DRP exercise | CISO + COO |

Exercise outcomes are documented, gaps tracked to remediation, and material findings reported to the Risk Management Committee.

## 8. Reference appendices

(Maintained separately for distribution control; not included in this repo.)

- Appendix A — Notification template library (regulator, customer, internal, public).
- Appendix B — Forensic toolkit and evidence handling checklist (aligned with ISO/IEC 27037).
- Appendix C — External supplier escalation matrix (EDR vendor, IR retainer, forensic firm, law enforcement liaison).
- Appendix D — Recovery validation checklist (per service tier).
- Appendix E — Communications playbooks by category (ransomware, data breach, insider, supplier).

## 9. Related documents

- **Parent policy:** [POL-08 Incident Management Policy](../01-policies/08-incident-management-policy.md)
- **Standard:** [STD-08-01 Incident Classification & Severity Standard](../02-standards/incident-classification-and-severity-standard.md)
- **Procedure:** [SOP-08-01 Incident Triage SOP](../03-procedures/incident-triage-sop.md)
- **Register:** [REG-INC Incident Register](../05-registers/incident-register.md)
- **Related policies:** [POL-09 Business Continuity Policy](../01-policies/09-business-continuity-policy.md), [POL-11 Operations Security Policy](../01-policies/11-operations-security-policy.md), [POL-14 Compliance Policy](../01-policies/14-compliance-policy.md)

## 10. Document control

| Version | Date | Author | Reviewer | Approver | Change summary |
|---|---|---|---|---|---|
| 1.0 | 2026-01-15 | CISO | Risk Management Committee | Risk Management Committee | Initial Effective version. |
