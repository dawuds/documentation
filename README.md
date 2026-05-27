# documentation

A worked example of IT governance documentation structure for a Malaysian licensed Islamic bank designated as a National Critical Information Infrastructure (NCII) entity.

## Versions

| Version | Status | Folder | Notes |
|---|---|---|---|
| **v1** | Stable (tagged `v1.0`) | [`v1/`](v1/) | ISO 27001-anchored ISMS for General Bank. Two worked cascades (Access Control, Incident Management). |
| **v2 Phase 1** | **Drafted in full (Sessions 1–11 complete)** | (root) | Full IT governance architecture for **General Islamic Bank Berhad (GIBB)** — federated GRC, NCII-designated. Nine bank-authored frameworks + 25 policies + 15 standards + 11 SOPs + 6 plans + 21 registers + document control suite + migration playbook. All 9 frameworks have cascade depth visible from framework → policy → standard → SOP → register. |

## v2 — current state

| Folder | Contents |
|---|---|
| [`_context/`](_context/) | Design decisions (13 ADRs); bank profile; framework stack; seams; glossary; role; outcome |
| [`_templates/`](_templates/) | Six templates (framework, policy, standard, procedure, plan, register) |
| [`_learning/`](_learning/) | Migration playbook (v2 addition); v1 reading paths + extension roadmap remain at v1/_learning/ |
| [`00-architecture/`](00-architecture/) | GIBB IT Governance Architecture (ARCH-001) — picture-first opener |
| [`01-frameworks/`](01-frameworks/) | Nine Layer 2 frameworks: TRMF, CRMF, BCMF, TPRMF, CIMF, NCIIF, CloudRMF, DGF, AIGF |
| [`02-policies/`](02-policies/) | 25 Layer 3 policies — TRMF cascade (10) + CRMF cascade re-anchored from v1 (7) + framework cascades (7) + POL-HR-01 HR Security (re-anchored from v1 POL-06) |
| [`03-standards/`](03-standards/) | 15 standards — TRMF (CM, AM), CRMF (AC, IR, CR-01/02/03), BCMF (BC-01/02), TPRMF (TP-01), CIMF (CI-01), NCIIF (NC-01), CloudRMF (CL-01), DGF (DG-01), AIGF (AI-01) |
| [`04-procedures/`](04-procedures/) | 11 SOPs — CM-01, CM-02, AC-01, IR-01, CR-01 Cyber Drill, CI-02 Breach Notif, NC-01 NACSA Notif, BC-01 BIA, TP-01 TPSP Onboarding, CL-01 Cloud Onboarding, AI-01 AI Use Case Onboarding |
| [`05-plans/`](05-plans/) | 6 plans — PLN-01 IRP, PLN-02 BCP, PLN-03 DRP, PLN-04 Crisis Comms, PLN-05 Cyber Drill, PLN-06 Pandemic |
| [`06-registers/`](06-registers/) | 21 registers — framework anchors (REG-TR, INC, PAR, SOA, BIA, TPS, ROPA, NCN, CL, DA, AIU) + cross-cutting (REG-EXC Exception, REG-VUL Vuln, REG-CDB Customer Data Breach, REG-DRL Cyber Drill, REG-OUT Material Outsourcing, REG-DSR Data Subject Request, REG-AIM AI Model Inventory, REG-CAP Corrective Action, REG-BCT BC Test Outcomes, REG-DRR DR Test) |
| [`07-document-control/`](07-document-control/) | Master document register (every v2 document catalogued), change log, approval register, archive |

## Phase 1 complete — what's possible next (Phase 2+)

- **Standards depth per framework** — each Section 9 implementation table in [`01-frameworks/`](01-frameworks/) lists additional standards that could be added with operational evidence (e.g., per-cloud-provider standards under CloudRMF; data quality + retention + metadata standards under DGF; AI validation + GenAI security + AI training-data standards under AIGF)
- **SOP depth per framework** — additional SOPs per Section 9 implementation tables (e.g., SOC detection tuning, forensic evidence handling, periodic reassessment SOPs)
- **Per-service DRPs** (PLN-03-x) — subordinate to PLN-03 master DRP, one per critical service
- **Subordinate registers** — REG-NC NACSA Directive Tracker, REG-NCA NCII Audit Findings, REG-CEX Cloud Exit Plans, REG-CRA Cloud Risk Assessment, REG-AIV AI Vendor, REG-AIB AI Bias and Fairness, REG-DQ Data Quality, REG-DL Data Lineage, REG-MD Master Data, REG-TPI TPSP Incident, REG-DIS Customer Disclosure
- **GRC platform format** — structured-data form of v2 content for ingestion into a GRC platform (Archer, ServiceNow GRC, OneTrust, MetricStream) when GIBB selects one
- **Per-policy operational reviews** — substantive content review by GIBB function owners before approval cycle

## Compliance anchors

| Authority | Scope |
|---|---|
| ISO/IEC 27001:2022; ISO/IEC 27002:2022 | ISMS standard + 93 controls |
| ISO/IEC 22301:2019 | BCMS standard |
| ISO/IEC 42001:2023 | AI Management System |
| BNM Risk Management in Technology (RMiT), 28 November 2025 issuance | Primary regulatory mandate |
| Cyber Security Act 2024 (Malaysia) + NACSA Code of Practice | NCII designation |
| BNM Shariah Governance Framework | Islamic-banking overlay |
| BNM Outsourcing / BCM / MCIPD / Operational Risk Reporting PDs | Supporting BNM mandates |
| PDPA 2010; IFSA 2013; FSA 2013; Computer Crimes Act 1997 | Applicable laws |
| COBIT 2019 (incl. Focus Areas); ITIL 4; NIST CSF 2.0; NIST AI RMF; EU AI Act; MAS FEAT; BNM Cloud TRAG; CIS Benchmarks | Reference frameworks |

## Disclaimer

This documentation is illustrative. It is not legal, regulatory, or audit advice. Any organisation adopting it must validate every control against its own risk profile, regulatory obligations, and operating environment. GIBB is a fictional bank used as a worked example.
