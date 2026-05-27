# documentation

A worked example of IT governance documentation structure for a Malaysian licensed Islamic bank designated as a National Critical Information Infrastructure (NCII) entity.

## Versions

| Version | Status | Folder | Notes |
|---|---|---|---|
| **v1** | Stable (tagged `v1.0`) | [`v1/`](v1/) | ISO 27001-anchored ISMS for General Bank. Two worked cascades (Access Control, Incident Management). |
| **v2 Phase 1** | Drafted (Sessions 1–6 complete) | (root) | Full IT governance architecture for **General Islamic Bank Berhad (GIBB)** — federated GRC, NCII-designated. Nine bank-authored framework documents (TRMF, CRMF, BCMF, TPRMF, CIMF, NCIIF, CloudRMF, DGF, AIGF), 24 policies, 4 standards, 3 SOPs, 2 plans, 11 registers, document control suite. CRMF cascade re-anchored from v1 in Session 5. All 9 frameworks have at least one cascade policy + register (Session 6). |

## v2 — current state

| Folder | Contents |
|---|---|
| [`_context/`](_context/) | Design decisions (13 ADRs); bank profile; framework stack; seams; glossary; role; outcome |
| [`_templates/`](_templates/) | Six templates (framework, policy, standard, procedure, plan, register) |
| [`00-architecture/`](00-architecture/) | GIBB IT Governance Architecture (ARCH-001) — picture-first opener |
| [`01-frameworks/`](01-frameworks/) | Nine Layer 2 frameworks: TRMF, CRMF, BCMF, TPRMF, CIMF, NCIIF, CloudRMF, DGF, AIGF |
| [`02-policies/`](02-policies/) | 24 Layer 3 policies — TRMF cascade (10) + CRMF cascade re-anchored from v1 (7) + minimum cascade for BCMF/TPRMF/CIMF/NCIIF/CloudRMF/DGF/AIGF (7) |
| [`03-standards/`](03-standards/) | 4 standards — TRMF cascade (STD-CM-01, STD-AM-01) + CRMF cascade (STD-AC-01, STD-IR-01) |
| [`04-procedures/`](04-procedures/) | 3 SOPs — TRMF cascade (SOP-CM-01) + CRMF cascade (SOP-AC-01, SOP-IR-01) |
| [`05-plans/`](05-plans/) | 2 plans — PLN-01 IRP (CRMF, re-anchored from v1) + PLN-02 BCP (BCMF). DRP, Crisis Comms, Cyber Drill, Pandemic — to be built |
| [`06-registers/`](06-registers/) | 11 registers — TRMF (REG-TR) + CRMF (REG-INC, REG-PAR, REG-SOA cross-framework) + 7 framework anchor registers (REG-BIA, REG-TPS, REG-ROPA, REG-NCN, REG-CL, REG-DA, REG-AIU) |
| [`07-document-control/`](07-document-control/) | Master document register, change log, approval register, archive |

## Pending for subsequent sessions

- **BCMF / TPRMF / CIMF / NCIIF / CloudRMF / DGF / AIGF cascades**: Layer 3-6 documents per each framework
- **Remaining standards / SOPs / plans / registers** per each framework's Section 9 implementation table
- **HR Security Policy** (POL-06HR equivalent — was POL-06 in v1) under a future People Risk framework or absorbed into POL-06 Access Control
- **Migration playbook**: how GIBB would migrate from its existing accreted policies to the v2 structure
- **Operational tooling**: ingestion format for a GRC platform if and when GIBB selects one

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
