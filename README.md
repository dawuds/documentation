# documentation

A worked example of IT governance documentation structure for a Malaysian licensed Islamic bank designated as a National Critical Information Infrastructure (NCII) entity.

## Versions

| Version | Status | Folder | Notes |
|---|---|---|---|
| **v1** | Stable (tagged `v1.0`) | [`v1/`](v1/) | ISO 27001-anchored ISMS for General Bank. Two worked cascades (Access Control, Incident Management). |
| **v2 Phase 1** | Drafted (Sessions 1–4 complete) | (root) | Full IT governance architecture for **General Islamic Bank Berhad (GIBB)** — federated GRC, NCII-designated. Nine bank-authored framework documents (TRMF, CRMF, BCMF, TPRMF, CIMF, NCIIF, CloudRMF, DGF, AIGF), 10 TRMF-origin policies, 2 standards, 1 SOP, 1 register, document control suite. |

## v2 — current state

| Folder | Contents |
|---|---|
| [`_context/`](_context/) | Design decisions (13 ADRs); bank profile; framework stack; seams; glossary; role; outcome |
| [`_templates/`](_templates/) | Six templates (framework, policy, standard, procedure, plan, register) |
| [`00-architecture/`](00-architecture/) | GIBB IT Governance Architecture (ARCH-001) — picture-first opener |
| [`01-frameworks/`](01-frameworks/) | Nine Layer 2 frameworks: TRMF, CRMF, BCMF, TPRMF, CIMF, NCIIF, CloudRMF, DGF, AIGF |
| [`02-policies/`](02-policies/) | 10 TRMF-origin Layer 3 policies (POL-01, POL-02, POL-03, POL-07, POL-08, POL-09, POL-15, POL-16, POL-17, POL-22) |
| [`03-standards/`](03-standards/) | Two standards (STD-CM-01, STD-AM-01) demonstrating the TRMF cascade |
| [`04-procedures/`](04-procedures/) | One SOP (SOP-CM-01) demonstrating the TRMF cascade |
| [`05-plans/`](05-plans/) | Placeholders for plans (IRP, BCP, DRP, Crisis Comms, Cyber Drill, Pandemic) |
| [`06-registers/`](06-registers/) | Technology Risk Register (REG-TR) |
| [`07-document-control/`](07-document-control/) | Master document register, change log, approval register, archive |

## Pending for subsequent phases

- **CRMF cascade**: re-anchor v1 InfoSec content (14 policies, 2 standards, 2 SOPs, IRP, registers) under CRMF
- **BCMF / TPRMF / CIMF / NCIIF / CloudRMF / DGF / AIGF cascades**: Layer 3-6 documents per each framework
- **Remaining standards / SOPs / plans / registers** per the TRMF Section 9 implementation tables
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
