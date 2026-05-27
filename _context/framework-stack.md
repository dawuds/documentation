# Framework stack

The layered framework architecture for v2.

← [_context home](README.md) · [decisions.md](decisions.md)

---

## Layer 0 — Regulatory anchors (external, binding)

GIBB must satisfy each of these. They are the source of every "shall" obligation in v2.

| Anchor | Authority | Scope |
|---|---|---|
| **BNM RMiT** (28 Nov 2025) | Bank Negara Malaysia | Primary — Technology Risk + Cyber + IT Operations + Outsourcing + Audit + Awareness |
| **Cyber Security Act 2024** | Government of Malaysia / NACSA | NCII designation; NACSA Code of Practice; NCII-specific obligations |
| **BNM Shariah Governance Framework** | Bank Negara Malaysia | Islamic banks — Shariah Committee, Shariah Risk, Shariah Compliance, Shariah Audit |
| **BNM Business Continuity Management PD** | Bank Negara Malaysia | Business continuity, including the cyber incident notification clock referenced by RMiT 11.18 |
| **BNM Outsourcing PD** | Bank Negara Malaysia | Third-party arrangements |
| **BNM MCIPD** | Bank Negara Malaysia | Management of Customer Information and Permitted Disclosures |
| **BNM Operational Risk Reporting PD** | Bank Negara Malaysia | Operational risk reporting incl. cyber incident notification clock |
| **PDPA 2010** | Government of Malaysia | Personal data processing, breach notification |
| **IFSA 2013** | Government of Malaysia | Islamic Financial Services Act — licensing |
| **FSA 2013** | Government of Malaysia | Financial Services Act |
| **Computer Crimes Act 1997** | Government of Malaysia | Criminal liability; enforcement basis |

---

## Layer 1 — Reference frameworks (external, drawn upon, not authored)

GIBB cites these but does not own them. They provide taxonomy, structure, and operational practice.

| Framework | Use in v2 |
|---|---|
| **COBIT 2019** | Structural taxonomy for IT governance — 40 objectives across EDM / APO / BAI / DSS / MEA |
| **COBIT 2019 Focus Areas** — Information Security; Information & Technology Risk | Operational extension of COBIT for security and tech-risk specific content |
| **ITIL 4** | Service management practices — plug into COBIT DSS domain |
| **ISO/IEC 27001:2022** | Information Security Management System standard — plugs into CRMF as the Information Security sub-framework |
| **ISO/IEC 27002:2022** | 93 information security controls reference |
| **ISO/IEC 22301:2019** | Business Continuity Management System standard — plugs into BCMF |
| **ISO/IEC 42001:2023** | AI Management System standard — plugs into AIGF |
| **NIST CSF 2.0** | Informative cross-walk for cyber resilience |
| **NIST AI RMF 1.0** + **Generative AI Profile** | Primary reference for AIGF |
| **NIST SP 800-61 Rev. 2** | Computer Security Incident Handling Guide — incident response phases |
| **NIST SP 800-88 Rev. 1** | Media Sanitization |
| **NIST SP 800-63B** | Digital Identity Guidelines — authentication assurance |
| **EU AI Act (2024)** | Risk classification taxonomy reference for AIGF |
| **MAS FEAT principles** | Singapore cross-jurisdictional reference for fair AI |
| **CIS Benchmarks** | Configuration baselines (cited from TRMF as practice) |
| **TOGAF** | Enterprise Architecture (light touch — referenced if EA is built out) |

---

## Layer 2 — Bank-authored framework documents (nine)

These are the documents GIBB itself publishes. They cite Layer 0 and Layer 1 and are subject to Board / Risk Management Committee / Audit Committee approval.

| # | Document | Primary owner | Approving body |
|---|---|---|---|
| 1 | **TRMF** — Technology Risk Management Framework | CRO + Head of Tech Risk | Risk Management Committee |
| 2 | **CRMF** — Cyber Risk Management Framework (containing CRF per RMiT 11.2) | CISO | Risk Management Committee |
| 3 | **BCMF** — Business Continuity Management Framework | COO | Risk Management Committee |
| 4 | **TPRMF** — Third Party Risk Management Framework | Head of Procurement + CRO | Risk Management Committee |
| 5 | **CIMF** — Customer Information Management Framework | DPO + CCO | Risk Management Committee |
| 6 | **NCIIF** — NCII Compliance Framework | CISO + CCO | Risk Management Committee |
| 7 | **CloudRMF** — Cloud Risk Management Framework | Head of Cloud + CISO | Risk Management Committee |
| 8 | **DGF** — Data Governance Framework | Chief Data Officer | Risk Management Committee |
| 9 | **AIGF** — AI Governance Framework | Chief Data Officer + CISO | Risk Management Committee |

---

## Below Layer 2 (cascading from the frameworks)

| Tier | Layer name | Approver |
|---|---|---|
| 3 | **Policies** — drilled-down "shall" statements per topic | Risk Management Committee (or Board for master) |
| 4 | **Standards** — mandatory, measurable requirements | CISO / functional head |
| 5 | **Procedures / SOPs** — operational sequences | Process owner |
| 6 | **Registers** — evidence of operating controls | Process owner |

Plans (IRP, BCP, DRP) sit between standards and procedures as scenario-driven artefacts, owned at function level and approved by RMC.

---

## Document headings convention

Every v2 document opens with:

```
| RMiT clause(s)        | Section [N.N–N.M]                        |
| COBIT objective(s)    | [EDMxx / APOxx / BAIxx / DSSxx / MEAxx]   |
| Practice standard(s)  | ISO 27001:2022 / ITIL 4 / ISO 22301 / etc.|
| Additional anchors    | NACSA Code of Practice / MCIPD / SGF / etc.|
```

Order: regulatory mandate first, taxonomy second, practice third, additional anchors fourth.
