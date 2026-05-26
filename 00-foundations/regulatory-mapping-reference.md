# Regulatory mapping reference

The authoritative cross-reference used by every document in this repo when citing BNM RMiT, ISO/IEC 27001/27002, and adjacent Malaysian regulation. **Edit here first; cascade everywhere else.**

| | |
|---|---|
| **Owner** | CISO (with Chief Compliance Officer) |
| **Cadence** | Reviewed on any regulatory issuance; minimum annual |
| **Source authority** | Each clause cited below traces to the issuing body's published text. This document is a navigation aid, not a substitute for the source. |

---

## 1. Bank Negara Malaysia, *Risk Management in Technology (RMiT)* — 28 November 2025 issuance

> **Source.** Bank Negara Malaysia, policy document `pd-rmit-nov25.pdf` (BNM/RH/PD 028-100), issued 28 November 2025. Supersedes the June 2020 issuance, which had substantially different numbering. **Do not cross-reference 2020 numbering.**

### 1.1 Structure overview

**Part B — Policy requirements (Sections 8–15):**

| Section  | Title | Subsections |
|---|---|---|
| **8** | Governance | 8.1–8.5 Board of Directors; 8.6–8.7 Senior management |
| **9** | Technology Risk Management | 9.1–9.3 TRMF; 9.4–9.5 Designated CISO |
| **10** | Technology Operations Management | See Section 1.2 below — 10.1–10.57 spanning 11 subsections |
| **11** | Cybersecurity Management | 11.1–11.7 Cyber Risk Management; 11.8–11.11 Cybersecurity Operations; 11.12–11.17 Cyber Response and Recovery; 11.18–11.20 Cyber Reporting and Threat Information Sharing |
| **12** | Digital Services | 12.1–12.2 Security of Digital Services; 12.3–12.9 Digital Fraud Management |
| **13** | Technology Audits | 13.1–13.4 Audit function |
| **14** | External Party Assurance | 14.1–14.2 |
| **15** | Security Awareness and Education | 15.1–15.3 |

**Part C — Regulatory process (Sections 16–18):**

| Section  | Title |
|---|---|
| **16** | Notification for Technology-Related Applications |
| **17** | Consultation and Notification related to Cloud Services and Emerging Technology |
| **18** | Assessment and Gap Analysis |

### 1.2 Section 10 (Technology Operations Management) subsection map

| Subsection | Clauses | Notes |
|---|---|---|
| Technology Project Management | 10.1–10.3 | |
| System Development and Acquisition | 10.4–10.16 | Includes change management embedded in 10.11; SDLC in 10.5; software supply chain in 10.15; shadow IT in 10.16 |
| Patch and End-of-Life System Management | 10.17–10.19 | |
| Cryptography | 10.20–10.23 | |
| Data Centre Resilience | 10.24–10.28 | |
| Service Availability | 10.29–10.35 | |
| Network Resilience | 10.36–10.43 | **Not** incident management — that is in Section 11 |
| System backup and restoration | 10.44–10.45 | Tamper-proof backup at 10.45 |
| Third Party Service Provider Management | 10.46–10.49 | |
| Cloud Services | 10.50–10.52 | |
| Access Control | 10.53–10.57 | Includes MFA at 10.55, access matrix at 10.56, monitoring at 10.57 |

### 1.3 Section 11 (Cybersecurity Management) — key clauses to know by heart

| Clause | Title | Operational significance |
|---|---|---|
| 11.1 | Enterprise-Wide Cyber Risk Management | Enterprise-wide cyber risk responsibility |
| 11.2 | Cyber Resilience Framework Development | The **CRF** — a named RMiT artefact |
| 11.3 | CRF Minimum Elements | **9 mandatory CRF elements** — see Section 1.4 below |
| 11.4 | NCII Compliance Requirements | NACSA / Cyber Security Act 2024 alignment |
| 11.5 | Cybersecurity Control Measures | Implements Appendix 5 control measures |
| 11.6 | Red Team Simulation Attacks | Mandatory red team |
| 11.7 | Crowdsourced Security Testing | Coordinated vulnerability disclosure |
| 11.8 | Cybersecurity Operations Responsibilities | |
| 11.9 | Continuous Security Monitoring and SOC | **SOC is mandated here, not in an appendix** |
| 11.10 | Cyber Threat Intelligence | |
| 11.11 | Anomalous Activity Response | |
| 11.12 | Cyber Crisis Management | Crisis-tier governance over IR |
| 11.13 | Cyber Incident Response Plan | The IRP requirement |
| 11.14 | CERT Member Readiness | |
| 11.15 | Out-of-Band Communication Infrastructure | |
| 11.16 | Annual Cyber Drill Exercise | Annual drill requirement |
| 11.17 | Cyber Insurance and Loss Provision | |
| 11.18 | Cyber Incident Notification to BNM | Notification clock lives in upstream policy — see Section 1.5 |
| 11.19 | Cyber Threat Intelligence Sharing | |
| 11.20 | Stakeholder Collaboration on Cyber Threats | |

### 1.4 The nine mandatory CRF elements (RMiT Section 11.3)

A Cyber Resilience Framework **must** include:

| # | Element |
|---|---|
| a | Institutional understanding of the cyber risk context, exposure, and current posture |
| b | Identification, classification, and prioritisation of critical systems, information, assets, and interconnectivity (internal and external) |
| c | Identification of threats, vulnerabilities, and countermeasures securing digital service delivery |
| d | Layered cyber defences referencing current international standards (zero-trust, defence-in-depth, security-by-design) |
| e | Timely detection of cybersecurity incidents through continuous surveillance and monitoring |
| f | Detailed incident handling policies and procedures plus a crisis response playbook |
| g | Policies for secure information sharing and collaboration with other FIs and financial market infrastructure participants |
| h | Centralised automated tracking system for technology asset inventory |
| i | Dedicated cyber risk management function for actual/potential threat analysis and escalation |

### 1.5 The incident notification clock — citation chain

RMiT Section 11.18 (verbatim):

> *"A financial institution is required to notify the Bank of cyber incidents in adherence to the Bank's policy documents on Operational Risk Reporting – Part C, Business Continuity Management – Part C, Merchant Acquiring Services – paragraphs 19.25 to 19.26 and any other relevant policy documents specified by the Bank."*

**Operational reading.** RMiT Section 11.18 does **not** itself state a numeric notification window. The clock lives in the upstream BNM policies named in Section 11.18:

- BNM *Operational Risk Reporting* policy document, Part C
- BNM *Business Continuity Management* policy document, Part C
- BNM *Merchant Acquiring Services* paragraphs 19.25–19.26 (for merchant-acquiring relevant incidents)

**The 4-hour notification window** for material cyber incidents is the BNM expectation in current operational reporting practice for licensed FIs. It surfaces in the structured-data evidence layer of the General Bank's GRC repo as: *"BNM Incident Reporting Procedure — Procedure for reporting material incidents to BNM within four hours"* (artifact tagged to RMiT clause 11.4). This 4-hour figure is therefore **cited via a derivative-source chain**:

> RMiT Section 11.18 (verbatim, no numeric clock) → upstream BNM Operational Risk Reporting Part C / BCM Part C (clock lives here) → derivative artefact text in the GRC structured-data repository (asserts "4 hours").

**Action for any document citing the 4-hour clock.** State the number, cite RMiT Section 11.18 as the obligation entry-point, and **also** cite the upstream Operational Risk Reporting / BCM policies as the authoritative source of the clock. Flag the 4-hour figure as ⚠ derivative-source until verified directly against the upstream BNM policy text.

### 1.6 Appendices — Nov 2025 RMiT

The November 2025 RMiT retains appendices, but **numbering and content differ from the June 2020 issuance**. Confirmed appendix references in the Nov 2025 text:

| App. | Topic (per Nov 2025 RMiT clauses that reference it) |
|---|---|
| Appendix 1 | Minimum controls for storage and transportation of sensitive data in removable media (referenced in 10.44) |
| Appendix 2 | Minimum security controls for delivery channels (referenced in 12.1) |
| Appendix 3 | Minimum security controls for digital services authentication and authorisation (referenced in 12.1) |
| Appendix 4 | (Referenced in 12.1 for delivery channels — verify scope from PDF) |
| Appendix 5 | Cybersecurity control measures (referenced in 11.5, 11.9) — the major cyber controls appendix |
| Appendix 6 | Criteria for simplified notification of digital service enhancements (referenced in 16.3) |
| Appendix 7 | Independent external party assurance format (Parts A–D) (referenced in 16.4) |
| Appendix 8 | Third-party service provider risk coverage matrix (referenced in 10.47) |
| Appendix 9 | Guidance on Emerging Technologies (referenced in 9.2) |
| Appendix 10 | Cloud risks and control mapping matrix (referenced in 10.51) |
| Appendix 11 | Fraud Detection Standards (referenced in 12.6) |

**Do not** reuse 2020 RMiT appendix references — they will misdirect readers. Any unverified appendix reference in this repo must be checked against the November 2025 PDF before publication.

### 1.7 Quick lookup — common citation translations from 2020 → 2025

| Topic | 2020 RMiT (deprecated) | **2025 RMiT (use this)** |
|---|---|---|
| Board oversight | Section 6.6 | **Section 8.1–8.5** (Board); **Section 8.2** for oversight specifically |
| Technology Risk Management Framework | Section 8 | **Section 9.1–9.3** |
| Designated CISO | Section 8 (within TRMF) | **Section 9.4–9.5** |
| Technology Operations | Section 9 | **Section 10** |
| Access Control | App. 6 | **Section 10.53–10.57** |
| Multi-Factor Authentication | App. 6 | **Section 10.55** |
| Patch & EOL | App. 7 | **Section 10.17–10.19** |
| Cryptography | (sparse) | **Section 10.20–10.23** |
| Data Centre Resilience | App. 3 | **Section 10.24–10.28** |
| Backup | App. 3 / scattered | **Section 10.44–10.45** |
| Third-Party Service Providers | Section 13 / App. 5 | **Section 10.46–10.49** + **Section 14** |
| Cloud Services | App. 5 | **Section 10.50–10.52** + **App. 10** |
| Cybersecurity Management (top level) | Section 10 | **Section 11** |
| Cyber Resilience Framework (the artefact) | (implicit) | **Section 11.2 + Section 11.3 (9 elements)** |
| NCII compliance | (n/a — 2024 Act post-dates 2020 RMiT) | **Section 11.4** |
| Cyber control measures | App. 5 / 10 | **Section 11.5 + App. 5** |
| Red Team | (sparse) | **Section 11.6** |
| Coordinated Disclosure | (n/a) | **Section 11.7** |
| SOC | App. 10 (CSOC) | **Section 11.9** |
| Threat Intelligence | (sparse) | **Section 11.10** |
| Cyber Crisis Management | (sparse) | **Section 11.12** |
| Cyber Incident Response Plan | (implicit) | **Section 11.13** |
| Out-of-Band Communication | (n/a) | **Section 11.15** |
| Annual Cyber Drill | (sparse) | **Section 11.16** |
| Cyber Insurance | (n/a) | **Section 11.17** |
| **Cyber Incident Notification to BNM** | App. 10 / Section 10.41-ish | **Section 11.18** (defers to upstream policy for clock — see Section 1.5) |
| Technology Audit | Section 11 | **Section 13** |
| Security Awareness and Education | Section 12 | **Section 15** |
| Digital Services | App. 8 | **Section 12** + **App. 2/3** |
| Digital Fraud Detection | App. 11 (then) | **Section 12.6 + App. 11** |

---

## 2. ISO/IEC 27001:2022 and ISO/IEC 27002:2022

### 2.1 ISO/IEC 27001:2022

The **management system standard** — what an ISMS is certified against. Mandatory documented information:

| Clause | Topic |
|---|---|
| 4.3 | Scope of the ISMS |
| 5.2 | Information Security Policy (board-approved) |
| 6.1.2 | Risk assessment process |
| 6.1.3 | Risk treatment process |
| 6.1.3 d | Statement of Applicability |
| 6.2 | Information security objectives |
| 7.2 | Competence (training records) |
| 7.5 | Control of documented information |
| 7.5.3 | Control of changes to documented information |
| 9.1 | Monitoring and measurement results |
| 9.2 | Internal audit programme and results |
| 9.3 | Management review results |
| 10.1 | Nonconformities and corrective action |

### 2.2 ISO/IEC 27002:2022

The **controls reference** — 93 controls in 4 themes:

| Theme | Code range | Count |
|---|---|---|
| Organisational | 5.1–5.37 | **37** |
| People | 6.1–6.8 | **8** |
| Physical | 7.1–7.14 | **14** |
| Technological | 8.1–8.34 | **34** |
| **Total** | | **93** |

ISO/IEC 27001:2022 Clause 6.1.3 d requires a Statement of Applicability listing every applicable control with implementation reference. See [`../05-registers/statement-of-applicability.md`](../05-registers/statement-of-applicability.md).

---

## 3. Adjacent Malaysian regulation referenced in this repo

| Instrument | Significance |
|---|---|
| **Financial Services Act 2013** | Master licensing and supervision framework for conventional FIs. |
| **Islamic Financial Services Act 2013** | Equivalent for Islamic FIs. |
| **Personal Data Protection Act 2010** | Personal data processing, breach assessment. |
| **Cyber Security Act 2024** | Establishes NCII designation regime; brings designated FIs into NACSA scope. Cited in RMiT Section 11.4. |
| **Computer Crimes Act 1997** | Criminal liability for unauthorised access; enforcement basis. |
| **BNM Operational Risk Reporting** policy document, Part C | Holds the cyber incident notification clock referenced by RMiT Section 11.18. |
| **BNM Business Continuity Management** policy document, Part C | Disruption notification thresholds referenced by RMiT Section 11.18 and Section 10.32–10.35. |
| **NACSA** directives and sector-lead instructions | Apply to FIs designated as NCII entities under Cyber Security Act 2024. |

---

## 4. Citation discipline (binding on every document in this repo)

1. Cite the **clause number** to the granularity the source uses (e.g., Section 11.3 not "Section 11").
2. State the **issuance date** when the regulator has multiple live versions in circulation. For RMiT, this is the November 2025 issuance unless explicitly stated.
3. **Never assert a regulatory clock or threshold without a source chain.** If the clock comes via a derivative source (e.g., structured-data artefact text rather than verbatim regulation), say so explicitly and flag with ⚠ for verification against the primary source.
4. **Never cite a deprecated issuance.** When updating a document, replace 2020 RMiT references in their entirety — do not leave one citation in old numbering and another in new.
5. **Material on regulation is illustrative.** It is not legal, regulatory, or audit advice. Every document touching regulatory obligation carries this caveat in its purpose section or in the repo-level disclaimer.

---

## 5. Maintenance

This document is the upstream reference. When BNM, ISO, or any cited authority issues new or revised text:

1. Update **this document first**.
2. Open a change-log entry in [`../06-document-control/change-log.md`](../06-document-control/change-log.md) under the documents affected.
3. Sweep affected documents downstream, reconciling against this reference.
4. Record the regulatory issuance in the document-control trail with the issuance date and reference.

Edits to this document themselves require CISO sign-off and a change-log row.
