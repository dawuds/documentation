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
| **Parent framework(s)** | [CRMF](../01-frameworks/CRMF.md) (this Plan IS the bank Cyber Incident Response Plan per RMiT 11.13) |
| **COBIT objective(s)** | DSS02; DSS05 |
| **Aligned with** | NIST SP 800-61 Rev. 2 (Computer Security Incident Handling Guide); ISO/IEC 27035-1:2023; BNM RMiT (28 Nov 2025) Section 11 — particularly the Cyber Resilience Framework at Section 11.2/Section 11.3 (IPDRR), Section 11.12 (Cyber Crisis Management), Section 11.13 (Cyber Incident Response Plan), Section 11.14 (CERT Member Readiness), Section 11.15 (Out-of-Band Communication Infrastructure), Section 11.16 (Annual Cyber Drill Exercise), Section 11.17 (Cyber Insurance and Loss Provision), Section 11.18 (Cyber Incident Notification to BNM) |

> **Distribution.** This plan is *Internal — restricted*. The on-call card extracted from Section 4 and Section 5 is distributed to the response team via the secure on-call platform. Full plan distribution is to: CISO, CEO, CRO, CCO, General Counsel, COO, Head of SOC, Head of IT Ops, Corporate Communications, RMC members. Quarterly review confirms distribution list currency.

---

## 1. Purpose

To define how GIBB responds to confirmed security incidents — specifically SEV-1 and SEV-2 incidents under [STD-IR-01](../03-standards/STD-IR-01-incident-classification-and-severity-standard.md) — from declaration through post-incident review. The Plan operationalises [POL-13 Section 4.3](../02-policies/POL-13-incident-management-policy.md) and picks up where the [Incident Triage SOP](../04-procedures/SOP-IR-01-incident-triage-sop.md) hands off.

This Plan **is** the bank's Cyber Incident Response Plan for the purpose of **BNM RMiT Section 11.13** and implements the incident handling and crisis response playbook required by the **Cyber Resilience Framework** mandatory elements (RMiT Section 11.3(f)). The crisis-tier governance overlay is the **Cyber Crisis Management** capability required by **RMiT Section 11.12**.

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

## 5. Response phases (NIST SP 800-61 Rev. 2 aligned)

### 5.1 Preparation

(Continuous, not per-incident.)

- IRP reviewed annually and after every SEV-1 *(per RMiT Section 11.13)*.
- Tabletop exercise quarterly; functional / simulation exercise annually with executive engagement; **mandatory annual cyber drill exercise per BNM RMiT Section 11.16**.
- On-call rotation maintained and tested monthly (call-out drills); CERT-member readiness maintained per **BNM RMiT Section 11.14**.
- Response tooling (SOAR, EDR, forensic kit, conferencing, out-of-band channels) tested quarterly.
- Threat-intelligence feeds operated per **BNM RMiT Section 11.10**; sharing channels with peer FIs and BNM operated per **Section 11.19** and **Section 11.20**.
- Regulator contacts, supplier escalation paths, and NACSA contacts (where NCII per **Section 11.4**) maintained current.
- Cyber insurance and loss provision maintained per **BNM RMiT Section 11.17**.

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
| External — Regulator (NACSA, if NCII) | NCII-designated incident per **BNM RMiT Section 11.4** and Cyber Security Act 2024 | Per NACSA prescribed channels | Chief Compliance Officer + CISO | Per current NACSA directives for the financial sector |
| External — Sector peers (Threat Intelligence Sharing) | As warranted per **BNM RMiT Section 11.19** | Established sector-CERT and FI peer channels | CISO | Per CISO discretion |
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
| **Annually (overlap with BCP)** | Joint IRP/BCP/DRP exercise | CISO + COO | Internal + RMiT Section 10.29–10.35 |

Exercise outcomes are documented, gaps tracked to remediation, and material findings reported to the Risk Management Committee.

## 8. Reference appendices

(Maintained separately for distribution control; not included in this repo.)

- Appendix A — Notification template library (regulator, customer, internal, public).
- Appendix B — Forensic toolkit and evidence handling checklist (aligned with ISO/IEC 27037).
- Appendix C — External supplier escalation matrix (EDR vendor, IR retainer, forensic firm, law enforcement liaison).
- Appendix D — Recovery validation checklist (per service tier).
- Appendix E — Communications playbooks by category (ransomware, data breach, insider, supplier).

## 9. Incident orchestration — canonical document order and ID convention

A single material cyber incident touches multiple policies, standards, SOPs, and registers across four frameworks (CRMF / CIMF / NCIIF / TPRMF). This Section is the **canonical orchestration map** — the order operations follow and the canonical IDs that link evidence together. This Plan is authoritative if any contributing document diverges.

### 9.1 Canonical incident ID

Every confirmed incident gets a single canonical ID at the moment of severity confirmation: `INC-YYYY-NNN` (assigned by [SOP-IR-01](../04-procedures/SOP-IR-01-incident-triage-sop.md) and recorded in [REG-INC](../06-registers/REG-INC-incident-register.md)). Every downstream artefact references this ID. There is no separate "cyber incident ID" / "customer breach ID" / "NACSA incident ID" / "TPSP incident ID" — those registers maintain their own row IDs (REG-CDB.cdb_id, REG-NCN.ncn_id, REG-TPI.tpi_id) and each links back to the canonical `INC-` ID.

### 9.2 Orchestration order (for a material cyber incident)

| Phase | Authority | Action | Artefact |
|---|---|---|---|
| **T+0 Detection** | SOC | Event detected; triage begins | [SOP-IR-01](../04-procedures/SOP-IR-01-incident-triage-sop.md) Step 1 |
| **T+0 to T+15 min** | SOC Shift Lead | Severity proposed per [STD-IR-01](../03-standards/STD-IR-01-incident-classification-and-severity-standard.md) | SOP-IR-01 Step 3 |
| **T+15 min** | Head of SOC / CISO | Severity confirmed; canonical `INC-` ID created | REG-INC entry created |
| **T+15 min onward** | CISO + CRO | **Joint materiality determination** per [POL-04 Section 3](../02-policies/POL-04-information-security-policy.md) | Materiality basis logged to REG-INC |
| **Immediately on materiality confirmed** | CCO | **BNM 4-hour notification clock starts** per [POL-13 Section 4.4.3](../02-policies/POL-13-incident-management-policy.md) | CCO assumes ownership of regulatory notification track in parallel with response |
| **In parallel** | IC | Containment per Section 5.3 of this Plan | Response track |
| **In parallel** | CCO | BNM notification dispatched per RMiT 11.18 | Logged to REG-INC `regulator_notified` |
| **In parallel — if NCII-scope** | CISO + CCO | NACSA notification dispatched per [POL-23](../02-policies/POL-23-ncii-operational-policy.md) + [STD-NC-01](../03-standards/STD-NC-01-nacsa-notification-standard.md) | [REG-NCN](../06-registers/REG-NCN-nacsa-notification-register.md) entry linked back to INC- |
| **In parallel — if customer personal data affected** | DPO + CCO | PDPA assessment; customer notification per [POL-CI-02](../02-policies/POL-CI-02-customer-consent-and-disclosure-policy.md) + [SOP-CI-02](../04-procedures/SOP-CI-02-customer-data-breach-notification-sop.md) | [REG-CDB](../06-registers/REG-CDB-customer-data-breach-register.md) entry linked back to INC- |
| **In parallel — if TPSP-originated** | Head of TPRM | TPSP-incident parallel entry; vendor incident management invoked per [STD-TP-03 Section 3.2](../03-standards/STD-TP-03-tpsp-continuous-monitoring-standard.md) | [REG-TPI](../06-registers/REG-TPI-tpsp-incident-register.md) entry linked back to INC- |
| **Throughout** | IC | Comms per Section 6 of this Plan | Internal + External comms tracks |
| **Post-containment** | IC | Eradication and recovery per Sections 5.4 and 5.5 | Response track |
| **Within 15 working days of closure** | CISO | PIR per [POL-13 Section 4.7](../02-policies/POL-13-incident-management-policy.md) | PIR linked to REG-INC `corrective_actions` |
| **Post-PIR** | CISO + CRO | Corrective actions to [REG-CAP](../06-registers/REG-CAP-corrective-action-register.md); pattern feedback to [REG-TR](../06-registers/REG-TR-technology-risk-register.md) | REG-CAP + REG-TR |

### 9.3 Canonical authority — who decides what

| Decision | Authority | Documented in |
|---|---|---|
| Severity classification | Head of SOC initially; CISO confirms for SEV-1 | REG-INC |
| Materiality determination (does the BNM clock start?) | **CISO + CRO jointly** | POL-04 Section 3; REG-INC |
| Containment exceeding pre-authorisations | IC; CEO/designate for customer-impacting | REG-INC; PLN-01 Section 5.3 |
| Regulator notification dispatch (BNM, NACSA) | CCO (BNM); CISO + CCO joint (NACSA) | REG-INC; REG-NCN |
| Customer notification dispatch | Comms Lead with Legal sign-off, on DPO+CCO recommendation | REG-CDB |
| Recovery to production | IC + CEO/designate (customer-facing) | REG-INC; PLN-01 Section 5.5 |
| Incident closure | CISO (after 30-day enhanced monitoring) | REG-INC `closed_at` |

### 9.4 Authoritative artefact when documents conflict

If the contributing artefacts (POL-13, STD-IR-01, SOP-IR-01, SOP-CI-02, SOP-NC-01) diverge in operating detail or sequencing, **this PLN-01 Section 9 is authoritative**. Divergences are tracked as exceptions in [REG-EXC](../06-registers/REG-EXC-exception-register.md) and reconciled at the next document review cycle.

## 10. Related documents

- **Parent policy:** [POL-13 Incident Management Policy](../02-policies/POL-13-incident-management-policy.md)
- **Standard:** [STD-IR-01 Incident Classification & Severity Standard](../03-standards/STD-IR-01-incident-classification-and-severity-standard.md)
- **Procedure:** [SOP-IR-01 Incident Triage SOP](../04-procedures/SOP-IR-01-incident-triage-sop.md); [SOP-CI-02 Customer Data Breach Notification SOP](../04-procedures/SOP-CI-02-customer-data-breach-notification-sop.md); [SOP-NC-01 NACSA Incident Notification SOP](../04-procedures/SOP-NC-01-nacsa-incident-notification-sop.md)
- **Registers:** [REG-INC](../06-registers/REG-INC-incident-register.md) (canonical); [REG-CDB](../06-registers/REG-CDB-customer-data-breach-register.md); [REG-NCN](../06-registers/REG-NCN-nacsa-notification-register.md); [REG-TPI](../06-registers/REG-TPI-tpsp-incident-register.md)
- **Related policies:** [POL-14 Business Continuity Policy](../02-policies/POL-14-business-continuity-policy.md), [POL-16 Operations Security Policy](../02-policies/POL-16-operations-security-policy.md), [POL-22 Compliance Policy](../02-policies/POL-22-it-compliance-policy.md), [POL-23 NCII Operational Policy](../02-policies/POL-23-ncii-operational-policy.md), [POL-CI-02 Customer Consent and Disclosure Policy](../02-policies/POL-CI-02-customer-consent-and-disclosure-policy.md)
- **Escalation:** [Board Reporting and Escalation Annex](../00-architecture/board-reporting-and-escalation-annex.md)

## 11. Document control

| Version | Date | Author | Reviewer | Approver | Change summary |
|---|---|---|---|---|---|
| 1.0 | 2026-01-15 | CISO | Risk Management Committee | Risk Management Committee | Initial Effective version. |
| 1.1 | 2026-05-30 | CISO | CRO + CCO | Pending RMC | Added Section 9 Orchestration map (canonical document order, IDs, authority); response to v2 multi-agent review (IT Gov: "no single orchestration document declares the order, master incident ID convention"). |

---

## v2 re-anchoring (2026-05-28)

This document was re-anchored as part of the v2 build (Session 5) per [DEC-001](../_context/decisions.md). Substantive content preserved from the v1 snapshot at [`../v1/`](../v1/). Changes applied:

- Document ID updated to v2 numbering convention
- **Parent framework(s)** and **COBIT objective(s)** added to metadata block
- Bank name normalised from "General Bank" to **GIBB** (General Islamic Bank Berhad)
- Internal cross-references migrated from v1 paths to v2 paths
- v1 sister-document references updated to v2 document IDs

Pending formal GIBB approval under v2. The Effective and Next review dates above are inherited from the v1 1.x lifecycle and will be updated when this document is approved under v2 governance.
