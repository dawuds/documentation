# documentation

A worked example of IT governance documentation structure for a Malaysian licensed Islamic bank designated as a National Critical Information Infrastructure (NCII) entity.

## Versions

| Version | Status | Folder | Notes |
|---|---|---|---|
| **v1** | Stable (tagged `v1.0`) | [`v1/`](v1/) | ISO 27001-anchored ISMS for General Bank. Two worked cascades (Access Control, Incident Management). |
| **v2 Phase 1 + 2** | **Drafted in full — complete** | (root) | Full IT governance architecture for **General Islamic Bank Berhad (GIBB)** — federated GRC, NCII-designated. **Nine bank-authored frameworks + 25 policies + 27 standards + 27 SOPs + 9 plans + 32 registers + document control suite + migration playbook + GRC platform format.** Every framework has full cascade depth (Framework → Policy → Standard → SOP → Plan → Register), with cross-cutting registers, per-service DRPs, and adjacent learning / migration / tooling material. |

## v2 — current state

| Folder | Contents |
|---|---|
| [`_context/`](_context/) | Design decisions (13 ADRs); bank profile; framework stack; seams; glossary; role; outcome |
| [`_templates/`](_templates/) | Six templates (framework, policy, standard, procedure, plan, register) |
| [`_learning/`](_learning/) | Migration playbook + GRC platform ingestion format (v2 additions); v1 reading paths + extension roadmap remain at v1/_learning/ |
| [`00-architecture/`](00-architecture/) | GIBB IT Governance Architecture (ARCH-001) — picture-first opener |
| [`01-frameworks/`](01-frameworks/) | Nine Layer 2 frameworks: TRMF, CRMF, BCMF, TPRMF, CIMF, NCIIF, CloudRMF, DGF, AIGF |
| [`02-policies/`](02-policies/) | **25 Layer 3 policies** |
| [`03-standards/`](03-standards/) | **27 standards** — TRMF (2), CRMF (5), BCMF (2), TPRMF (3), CIMF (3), NCIIF (2), CloudRMF (3), DGF (3), AIGF (4) |
| [`04-procedures/`](04-procedures/) | **27 SOPs** — across all cascades incl. forensic evidence handling, cyber drill, BIA, backup operations, TPSP lifecycle, DSAR, customer breach notification, NACSA notification & examination response, CSPM operations, cloud exit validation, data asset/quality/destruction, AI model validation, AI vendor assessment |
| [`05-plans/`](05-plans/) | **9 plans** — PLN-01 IRP, PLN-02 BCP, PLN-03 master DRP + PLN-03-CB/-IB/-PMT per-service DRPs, PLN-04 Crisis Comms, PLN-05 Cyber Drill, PLN-06 Pandemic |
| [`06-registers/`](06-registers/) | **32 registers** — framework anchors + cross-cutting registers + subordinate registers (NACSA Directive Tracker, NCII Audit Findings, Cloud Exit, Cloud Risk Assessment, AI Vendor, AI Bias and Fairness, Data Quality, Data Lineage, Master Data, TPSP Incident, Customer Disclosure) |
| [`07-document-control/`](07-document-control/) | Master document register (every v2 document catalogued), change log, approval register, archive |

## Build complete

All deferred items from prior phases have been completed. The next steps for GIBB to make this operational are:

- **Per-document approval cycle** under GIBB governance (Board for POL-00 / POL-01 / POL-03 / ARCH-001; RMC for the supporting suite; CISO / function heads for standards; process owners for SOPs)
- **Substantive content review** by GIBB function owners against actual operating model — terminology, role titles, system references, regulatory clock numerals
- **GRC platform selection** if going beyond markdown — see [`_learning/grc-platform-format.md`](_learning/grc-platform-format.md) for ingestion model
- **Migration execution** if GIBB is moving from an accreted current state — see [`_learning/migration-playbook.md`](_learning/migration-playbook.md) for 12–18 month plan
- **First operational cycles** — first annual cyber drill (RMiT 11.16); first BNM examination under v2; first Internal Audit cycle under v2; first NACSA examination

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
