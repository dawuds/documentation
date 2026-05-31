# ISMS Scope Statement

| | |
|---|---|
| **Document ID** | POL-04-A (Annex to [POL-04](POL-04-information-security-policy.md)) |
| **Layer** | Policy annex (Tier 1) |
| **Owner** | CISO |
| **Approver** | Board of Directors (as part of POL-04 approval) |
| **Classification** | Internal |
| **Version** | 1.0 |
| **Effective date** | [Effective] |
| **Next review** | Annual; immediate on material change to GIBB organisation, geography, services, technology estate, or applicable regulation |
| **Implements** | ISO/IEC 27001:2022 Clause 4.3 (Determining the scope of the information security management system) |
| **Parent framework(s)** | [CRMF](../01-frameworks/CRMF.md) |

---

## 1. Scope of the GIBB Information Security Management System

The ISMS covers the **end-to-end protection of information** processed, stored, or transmitted by **General Islamic Bank Berhad (GIBB)** in connection with its licensed banking activities under the **Islamic Financial Services Act 2013**, including its designation as a **National Critical Information Infrastructure (NCII)** entity under the **Cyber Security Act 2024**.

### 1.1 Organisational scope

| Included | Excluded (with basis) |
|---|---|
| GIBB Berhad (head office) — all functions and business lines | Subsidiary group entities outside GIBB Berhad — managed under their own ISMS or under contractual ISMS-equivalence per [POL-19](POL-19-supplier-security-policy.md) |
| GIBB Berhad — all branches in Malaysia | n/a |
| GIBB Berhad — all wholly-owned operating subsidiaries scoped under GIBB ISMS | Joint ventures and associates — managed under their own ISMS where applicable |

### 1.2 Service / product scope

All licensed Islamic banking services delivered by GIBB:

- Retail Islamic banking — deposit, financing, payments, cards, digital channels (internet banking, mobile banking).
- Commercial / SME Islamic banking — trade financing, working-capital financing, treasury services.
- Corporate Islamic banking — syndicated financing, capital markets, treasury and FX.
- Islamic wealth management — investment advisory, takaful distribution.
- Treasury and capital markets — for own-book and customer flow.
- Shariah-compliant alternative channels (e.g., zakat, hibah, waqf-linked offerings).

### 1.3 Technology / asset scope

All information assets supporting in-scope services, including:

- Information in any form (digital, paper, in-transit, at-rest, conversational).
- Information systems, applications, databases, and middleware — including the core banking system, customer channels, payment systems, treasury systems, AML and surveillance systems.
- Infrastructure — on-premise data centres (primary + DR), all cloud environments (multi-cloud per [POL-20](POL-20-cloud-acceptable-use-policy.md) and [CloudRMF](../01-frameworks/CloudRMF.md)), workstations, mobile devices, network, storage, identity systems, security systems.
- Outsourced ICT services and third-party service providers per [POL-19](POL-19-supplier-security-policy.md) — included via contractual ISMS-equivalence and continuous monitoring.

### 1.4 Geographic scope

Malaysia (head office and all branches). Cross-border activities (e.g., correspondent banking, cross-border treasury flow, foreign-cloud-hosted services) are included to the extent that they process GIBB information; the cross-border-transfer controls in [POL-CI-02 Section 3.5](POL-CI-02-customer-consent-and-disclosure-policy.md) apply.

### 1.5 Standards within ISMS scope

| Standard | Scope within GIBB |
|---|---|
| ISO/IEC 27001:2022 | The whole bank as scoped above |
| ISO/IEC 22301:2019 (BCMS) | Operated under [BCMF](../01-frameworks/BCMF.md) — overlapping scope with ISMS |
| ISO/IEC 42001:2023 (AIMS) | Operated under [AIGF](../01-frameworks/AIGF.md) — overlapping scope where AI is in scope |

## 2. Interfaces and dependencies (Clause 4.3 b)

The ISMS interfaces with — but does not include — the following, which are managed separately under their own arrangements:

- **Customer-side controls** (e.g., the customer's own device security) — out of GIBB's ISMS scope; addressed via customer education and channel-level controls.
- **Third-party-controlled environments** — within scope only at the contractual boundary; the supplier operates its own ISMS, evidenced per [STD-TP-03](../03-standards/STD-TP-03-tpsp-continuous-monitoring-standard.md).
- **Regulator and law-enforcement systems** receiving notifications under [POL-13](POL-13-incident-management-policy.md) and [POL-CI-02](POL-CI-02-customer-consent-and-disclosure-policy.md) — out of scope.
- **Bursa Malaysia / clearing infrastructure** — out of GIBB's ISMS scope; addressed via membership-level controls.

## 3. Exclusions

The following exclusions are made and justified per Clause 4.3 (the ISMS shall include all in-scope activities; exclusions are limited to genuinely out-of-scope activities):

- Subsidiary group entities outside GIBB Berhad — managed under their own ISMS.
- Customer-side controls — outside GIBB's authority.
- Other licensed entities operating under separate banking licences.

## 4. Maintenance

This scope statement is reviewed at every annual Management Review per [REG-MR](../06-registers/REG-MR-management-review-register.md) and updated immediately on material change to GIBB organisation, services, technology, or applicable regulation. The current version is the authoritative basis for ISO 27001 certification scope.

## 5. Related documents

- **Parent policy:** [POL-04 Information Security Policy](POL-04-information-security-policy.md)
- **Annex sibling:** [POL-04-B Information Security Policy Statement (ISO 27001 Clause 5.2)](POL-04-B-information-security-policy-statement.md)
- **Framework:** [CRMF](../01-frameworks/CRMF.md)
- **Register:** [REG-SOA](../06-registers/REG-SOA-statement-of-applicability.md) (Annex A control map for this scope)

## 6. Document control

| Version | Date | Author | Reviewer | Approver | Change summary |
|---|---|---|---|---|---|
| 1.0 | 2026-05-30 | CISO | RMC | Board of Directors (as POL-04 annex) | Initial version. Created as standalone annex to close ISO 27001 Clause 4.3 evidence gap identified in v2 multi-agent review. |
