# General Bank — Information Security Management System

The body of policies, standards, procedures, plans, and registers by which **General Bank** protects information assets entrusted to it by customers, employees, partners, and regulators. The ISMS is established by the Board, governed by the Risk Management Committee, and operated by the Chief Information Security Officer.

The master policy is [**POL-00 Information Security Policy**](01-policies/00-information-security-policy.md), Board-approved 15 January 2026, satisfying ISO/IEC 27001:2022 Clause 5.2.

> **Disclaimer.** This documentation is illustrative — a worked example of best-practice ISMS documentation structure for a Malaysian licensed bank. It is not legal, regulatory, or audit advice. Any organisation adopting it must validate every control against its own risk profile, regulatory obligations, and operating environment. Personnel, systems, and dates are fictional; the regulatory anchors are real.

---

## Scope

This ISMS applies to all information assets owned, processed, transmitted, or stored by General Bank, regardless of location, infrastructure ownership, or processing party; to all personnel (employees, contractors, secondees, third parties); to all systems and services (owned, leased, cloud-hosted, outsourced); and to all locations from which General Bank information is accessed. The Statement of Applicability at [`05-registers/statement-of-applicability.md`](05-registers/statement-of-applicability.md) records the applicability of every ISO/IEC 27002:2022 Annex A control.

## Compliance anchors

| Authority | Status in this ISMS |
|---|---|
| **ISO/IEC 27001:2022** — ISMS requirements | Aligned (certifiable structure) |
| **ISO/IEC 27002:2022** — 93 controls in 4 themes | All 93 applicable per SoA |
| **Bank Negara Malaysia, *Risk Management in Technology (RMiT)*** — 28 November 2025 issuance | Aligned across §8–§18 |
| **Cyber Security Act 2024 (Malaysia)** — NCII regime | Compliance per RMiT §11.4 + NACSA directives |
| Financial Services Act 2013; Personal Data Protection Act 2010; Computer Crimes Act 1997 | Applicable; tracked in Compliance Register |

The canonical citation mapping used by every document in this suite is at [`00-foundations/regulatory-mapping-reference.md`](00-foundations/regulatory-mapping-reference.md).

---

## The suite

| Layer | Folder | What it contains |
|---|---|---|
| **Foundations** | [`00-foundations/`](00-foundations/) | Document hierarchy, tiering model, governance model, lifecycle, regulatory mapping reference |
| **Tier 1 — Policies** | [`01-policies/`](01-policies/) | Master Information Security Policy + 14 supporting policies |
| **Tier 2 — Standards** | [`02-standards/`](02-standards/) | Mandatory, measurable requirements implementing the policies |
| **Tier 3 — Procedures** | [`03-procedures/`](03-procedures/) | Step-by-step operational SOPs |
| **Plans** | [`04-plans/`](04-plans/) | Time-bound, scenario-driven response plans (IRP) |
| **Registers** | [`05-registers/`](05-registers/) | Evidence — SoA, Risk Register, Privileged Access Review Register, Incident Register |
| **Document control** | [`06-document-control/`](06-document-control/) | Master register, change log, approval register, archive |
| **Optional layers** | [`99-optional-layers/`](99-optional-layers/) | Guidance on Charter / Guideline / Baseline / Manual layers (M4) |
| **Templates** | [`_templates/`](_templates/) | Skeletons for authoring new documents |

---

## Two worked cascades

The cascade — principle → standard → procedure → plan → evidence — is the structural pattern by which every domain in the suite is built. Two cascades are fully drafted as worked examples:

| Cascade | Policy | Standard | Procedure | Plan | Register |
|---|---|---|---|---|---|
| **Access Control** | [POL-02](01-policies/02-access-control-policy.md) | [Password & Auth](02-standards/password-and-authentication-standard.md) | [JML SOP](03-procedures/joiner-mover-leaver-sop.md) | — | [Privileged Access Review](05-registers/privileged-access-review-register.md) |
| **Incident Management** | [POL-08](01-policies/08-incident-management-policy.md) | [Classification & Severity](02-standards/incident-classification-and-severity-standard.md) | [Triage SOP](03-procedures/incident-triage-sop.md) | [Incident Response Plan](04-plans/incident-response-plan.md) | [Incident Register](05-registers/incident-register.md) |

---

## Document control

Current state of every document, change history, approval evidence, and archived superseded versions are consolidated in [`06-document-control/`](06-document-control/). The ISMS is subject to internal audit, external certification audit (annual surveillance, triennial recertification), and BNM regulatory examination.

---

## For practitioners learning from this repo

A separate `_learning/` overlay holds reading paths by audience and the extension roadmap (what a complete M3 ISMS would add beyond this worked example). See [`_learning/`](_learning/). The `_learning/` content is **not** part of the ISMS itself.
