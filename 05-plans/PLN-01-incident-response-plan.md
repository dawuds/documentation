# Incident Response Plan

| | |
|---|---|
| **Document ID** | PLN-01 |
| **Layer** | Plan |
| **Owner** | CISO |
| **Approver** | Risk Management Committee |
| **Classification** | Internal — restricted |
| **Version** | 1.0 |
| **Effective date** | 2026-02-01 |
| **Next review** | 2027-02-01 (annual; immediately following any SEV-1 incident) |
| **Implements policy** | [POL-13 Incident Management Policy](../02-policies/POL-13-incident-management-policy.md) |
| **Aligned with** | NIST SP 800-61 Rev. 2 (Computer Security Incident Handling Guide); ISO/IEC 27035-1:2023; BNM RMiT (28 Nov 2025) Section 11 — particularly the Cyber Resilience Framework at Section 11.2/Section 11.3 (IPDRR), Section 11.12 (Cyber Crisis Management), Section 11.13 (Cyber Incident Response Plan), Section 11.14 (CERT Member Readiness), Section 11.15 (Out-of-Band Communication Infrastructure), Section 11.16 (Annual Cyber Drill Exercise), Section 11.17 (Cyber Insurance and Loss Provision), Section 11.18 (Cyber Incident Notification to BNM) |

> **Distribution.** This plan is *Internal — restricted*. The on-call card extracted from Section 4 and Section 5 is distributed to the response team via the secure on-call platform. Full plan distribution is to: CISO, CEO, CRO, CCO, General Counsel, COO, Head of SOC, Head of IT Ops, Corporate Communications, RMC members. Quarterly review confirms distribution list currency.

---

## 1. Purpose

To define how GIBB responds to confirmed security incidents — specifically SEV-1 and SEV-2 incidents under [STD-IR-01](../03-standards/STD-IR-01-incident-classification-and-severity-standard.md) — from declaration through post-incident review. The Plan operationalises [POL-13 Section 4.3](../02-policies/POL-13-incident-management-policy.md) and picks up where the [Incident Triage SOP](../04-procedures/SOP-IR-01-incident-triage-sop.md) hands off.

This Plan **is** the bank's Cyber Incident Response Plan for the purpose of **BNM RMiT Section 11.13** and implements the incident handling and crisis response playbook required by the **Cyber Resilience Framework** mandatory elements (RMiT Section 11.3(f)). The crisis-tier governance overlay is the **Cyber Crisis Management** capability required by **RMiT Section 11.12**.
| **Parent framework(s)** | [CRMF](../01-frameworks/CRMF.md) (this Plan IS the bank Cyber Incident Response Plan per RMiT 11.13) |
| **COBIT objective(s)** | DSS02; DSS05 |

## 2. Scope

**In scope:**

- All declared SEV-1 and SEV-2 incidents.
- Selected SEV-3 incidents at the discretion of the CISO (typically those with regulatory or reputational potential).

**Out of scope:**

- Triage of unconfirmed events — covered by [SOP-IR-01](../04-procedures/SOP-IR-01-incident-triage-sop.md).
- Business continuity activation arising from non-security disruption — covered by the Business Continuity Plan under [POL-14](../02-policies/POL-14-business-continuity-policy.md).
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

Out-of-band contacts are tested as part of the quarterly tabletop. Out-of-band channels are documented on physical on-call cards held by named individuals — not stored solely in systems that may be impacted by an incident. *(Implements **BNM RMiT Section 11.15 (Out-of-Band Communication Infrastructure)**.)*
| **Parent framework(s)** | [CRMF](../01-frameworks/CRMF.md) (this Plan IS the bank Cyber Incident Response Plan per RMiT 11.13) |
| **COBIT objective(s)** | DSS02; DSS05 |

## 5. Response phases (NIST SP 800-61 Rev. 2 aligned)

### 5.1 Preparation

(Continuous, not per-incident.)

- IRP reviewed annually and after every SEV-1 *(per RMiT Section 11.13)*.
- Tabletop exercise quarterly; functional / simulation exercise annually with executive engagement; **mandatory annual cyber drill exercise per BNM RMiT Section 11.16**.
- On-call rotation maintained and tested monthly (call-out drills); CERT-member readiness maintained per **BNM RMiT Section 11.14**.
| **Parent framework(s)** | [CRMF](../01-frameworks/CRMF.md) (this Plan IS the bank Cyber Incident Response Plan per RMiT 11.13) |
| **COBIT objective(s)** | DSS02; DSS05 |
- Response tooling (SOAR, EDR, forensic kit, conferencing, out-of-band channels) tested quarterly.
- Threat-intelligence feeds operated per **BNM RMiT Section 11.10**; sharing channels with peer FIs and BNM operated per **Section 11.19** and **Section 11.20**.
| **Parent framework(s)** | [CRMF](../01-frameworks/CRMF.md) (this Plan IS the bank Cyber Incident Response Plan per RMiT 11.13) |
| **COBIT objective(s)** | DSS02; DSS05 |
- Regulator contacts, supplier escalation paths, and NACSA contacts (where NCII per **Section 11.4**) maintained current.
- Cyber insurance and loss provision maintained per **BNM RMiT Section 11.17**.
| **Parent framework(s)** | [CRMF](../01-frameworks/CRMF.md) (this Plan IS the bank Cyber Incident Response Plan per RMiT 11.13) |
| **COBIT objective(s)** | DSS02; DSS05 |

### 5.2 Detection and Analysis

Inherited from [SOP-IR-01](../04-procedures/SOP-IR-01-incident-triage-sop.md). On activation, the Incident Commander:

- Confirms severity per [STD-IR-01](../03-standards/STD-IR-01-incident-classification-and-severity-standard.md).
- Confirms initial scope (affected assets, data, users, services).
- Opens incident bridge; convenes core response team.
- Assigns: SOC Lead, Technical Lead(s), Communications Lead, Legal Lead, Compliance Lead.
- Establishes timeline cadence (typically 30-min status checks for SEV-1, 60-min for SEV-2).
- Decides on engagement of external forensic / IR retainer (if applicable).

**Decision gate:** **Is the incident in scope of regulator notification?** If yes, Compliance Lead initiates notification process in parallel (see Section 6).

### 5.3 Containment

The IC selects a containment strategy:

| Strategy | When chosen |
|---|---|
| **Short-term — minimise impact, preserve evidence** | Default for SEV-1 unless eradication is straightforward. |
| **Long-term — sustainable containment while preparing eradication** | When eradication requires significant planning (e.g., re-imaging large estate). |
| **Permit-and-observe** | Rare; only with CISO + General Counsel agreement, typically for active adversary characterisation under law-enforcement guidance. |

Containment actions exceeding the pre-authorisations in [SOP-IR-01 Section 5.4](../04-procedures/SOP-IR-01-incident-triage-sop.md) require IC approval (logged), or CEO/designate approval for customer-impacting actions.

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

- Post-Incident Review (PIR) scheduled per [POL-13 Section 4.7](../02-policies/POL-13-incident-management-policy.md) — within 15 working days of incident closure for SEV-1 and SEV-2.
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
| External — Regulator (Bank Negara Malaysia) | Material cyber incident per **BNM RMiT Section 11.18** | Per BNM's prescribed channels; upstream policy chain is *Operational Risk Reporting* Part C and *Business Continuity Management* Part C | Chief Compliance Officer | **Within 4 hours of detection** of a material cyber incident *(⚠ The 4-hour clock is the bank's operating expectation derived from BNM operational reporting practice and surfaces in the GRC structured-data artefact tagged to RMiT Section 11.4. It is not stated numerically in RMiT Section 11.18 verbatim. CCO maintains the authoritative clock by reference to Operational Risk Reporting Part C.)* |
| **Parent framework(s)** | [CRMF](../01-frameworks/CRMF.md) (this Plan IS the bank Cyber Incident Response Plan per RMiT 11.13) |
| **COBIT objective(s)** | DSS02; DSS05 |
| External — Regulator (NACSA, if NCII) | NCII-designated incident per **BNM RMiT Section 11.4** and Cyber Security Act 2024 | Per NACSA prescribed channels | Chief Compliance Officer + CISO | Per current NACSA directives for the financial sector |
| **Parent framework(s)** | [CRMF](../01-frameworks/CRMF.md) (this Plan IS the bank Cyber Incident Response Plan per RMiT 11.13) |
| **COBIT objective(s)** | DSS02; DSS05 |
| External — Sector peers (Threat Intelligence Sharing) | As warranted per **BNM RMiT Section 11.19** | Established sector-CERT and FI peer channels | CISO | Per CISO discretion |
| **Parent framework(s)** | [CRMF](../01-frameworks/CRMF.md) (this Plan IS the bank Cyber Incident Response Plan per RMiT 11.13) |
| **COBIT objective(s)** | DSS02; DSS05 |
| External — Affected customers (where personal data affected) | Per Personal Data Protection Act 2010 assessment | Direct customer channel (email, SMS, secure message in app) | Communications Lead, with Legal sign-off | Without undue delay following assessment. |
| External — Media / public | Decision made jointly by CEO, CISO, Communications Lead, GC | Press statement, social channels | Communications Lead under CEO direction | As decided. |
| External — Law enforcement | If criminal activity suspected; CISO + GC decision | Per established law-enforcement liaison contact | CISO + General Counsel | As decided. |
| External — Threat-sharing community / sector CERT | Where threat intelligence sharing is appropriate | Established sharing channels | CISO | As decided. |

A single Communications Lead is responsible for ensuring that all external communications are consistent and that no member of the response team makes public statements without authorisation.

## 7. Testing and exercise

| Frequency | Type | Owner | Authority |
|---|---|---|---|
| **Monthly** | On-call rotation call-out drill | Head of SOC | Internal |
| **Quarterly** | Tabletop exercise — scenario rotates across categories (ransomware, insider, supplier compromise, data exfiltration, payment-system compromise) | CISO | Internal |
| **Annually** | **Cyber Drill Exercise** — mandatory under **BNM RMiT Section 11.16**; scope includes executive team and (selectively) Board observation; lessons feed corrective actions | CISO + CEO | RMiT Section 11.16 |
| **Parent framework(s)** | [CRMF](../01-frameworks/CRMF.md) (this Plan IS the bank Cyber Incident Response Plan per RMiT 11.13) |
| **COBIT objective(s)** | DSS02; DSS05 |
| **Annually (overlap with BCP)** | Joint IRP/BCP/DRP exercise | CISO + COO | Internal + RMiT Section 10.29–10.35 |

Exercise outcomes are documented, gaps tracked to remediation, and material findings reported to the Risk Management Committee.

## 8. Reference appendices

(Maintained separately for distribution control; not included in this repo.)

- Appendix A — Notification template library (regulator, customer, internal, public).
- Appendix B — Forensic toolkit and evidence handling checklist (aligned with ISO/IEC 27037).
- Appendix C — External supplier escalation matrix (EDR vendor, IR retainer, forensic firm, law enforcement liaison).
- Appendix D — Recovery validation checklist (per service tier).
- Appendix E — Communications playbooks by category (ransomware, data breach, insider, supplier).

## 9. Related documents

- **Parent policy:** [POL-13 Incident Management Policy](../02-policies/POL-13-incident-management-policy.md)
- **Standard:** [STD-IR-01 Incident Classification & Severity Standard](../03-standards/STD-IR-01-incident-classification-and-severity-standard.md)
- **Procedure:** [SOP-IR-01 Incident Triage SOP](../04-procedures/SOP-IR-01-incident-triage-sop.md)
- **Register:** [REG-INC Incident Register](../06-registers/REG-INC-incident-register.md)
- **Related policies:** [POL-14 Business Continuity Policy](../02-policies/POL-14-business-continuity-policy.md), [POL-16 Operations Security Policy](../02-policies/POL-16-operations-security-policy.md), [POL-22 Compliance Policy](../02-policies/POL-22-it-compliance-policy.md)

## 10. Document control

| Version | Date | Author | Reviewer | Approver | Change summary |
|---|---|---|---|---|---|
| 1.0 | 2026-01-15 | CISO | Risk Management Committee | Risk Management Committee | Initial Effective version. |

---

## v2 re-anchoring (2026-05-28)

This document was re-anchored as part of the v2 build (Session 5) per [DEC-001](../_context/decisions.md). Substantive content preserved from the v1 snapshot at [`../v1/`](../v1/). Changes applied:

- Document ID updated to v2 numbering convention
- **Parent framework(s)** and **COBIT objective(s)** added to metadata block
- Bank name normalised from "General Bank" to **GIBB** (General Islamic Bank Berhad)
- Internal cross-references migrated from v1 paths to v2 paths
- v1 sister-document references updated to v2 document IDs

Pending formal GIBB approval under v2. The Effective and Next review dates above are inherited from the v1 1.x lifecycle and will be updated when this document is approved under v2 governance.
