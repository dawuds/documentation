# Board Reporting and Escalation Annex

| | |
|---|---|
| **Document ID** | ARCH-002 |
| **Layer** | Architecture annex |
| **Owner** | CISO + CRO + Company Secretary (joint) |
| **Approver** | Board of Directors |
| **Classification** | Internal — restricted |
| **Version** | 1.0 |
| **Effective date** | [Effective] |
| **Next review** | Annual; immediate on framework change or escalation-protocol revision |
| **Implements** | BNM RMiT (28 Nov 2025) Section 8 (Board and Senior Management oversight); Cyber Security Act 2024 + NACSA Code of Practice (NCII Board accountability); ISO/IEC 27001:2022 Clause 9.3 (Management Review at Board / RMC level); BNM Corporate Governance PD |
| **Parent framework(s)** | All 9 frameworks — cross-cutting Board view |

---

## 1. Purpose

To consolidate, in one document for the Board, **what the Board sees, when, in what format, from whom** — across all 9 bank-authored frameworks — and **the escalation protocol** that determines when an event hits the Board Chair, when it hits the RMC, and when it stays below the Board.

Closes the gap raised at the Board / RMC level in the v2 multi-agent review: "each framework has its own Section 11 reporting matrix — they're consistent but not consolidated; I have to assemble it myself across 9 documents."

This annex is the **Board-facing companion** to the framework Section 11 matrices and the [PLN-01 Incident Response Plan](../05-plans/PLN-01-incident-response-plan.md) Section 6 communication table.

---

## 2. Reporting cadence consolidated across the 9 frameworks

### 2.1 Board-level reporting (annual + as-warranted)

| Topic | Frequency | Source framework | Owner |
|---|---|---|---|
| ISMS / BCMS / AIMS combined Management Review attestation | Annual | CRMF / BCMF / AIGF | CISO + COO + CDO (joint via CRO) |
| Technology Risk position vs appetite | Annual + on breach | TRMF | CRO |
| Cyber resilience posture + cyber drill outcome | Annual | CRMF | CISO |
| NCII compliance attestation | Annual | NCIIF | CISO + CCO |
| Material outsourcing posture | Annual + on material new arrangement or exit | TPRMF | CRO + Head of Procurement |
| Cloud risk posture | Annual | CloudRMF | Head of Cloud + CISO |
| Customer information / PDPA / MCIPD posture | Annual + on regulator inquiry | CIMF | DPO + CCO |
| Data governance posture | Annual | DGF | CDO |
| AI governance posture | Annual (from FY2027) | AIGF | CDO + CISO |
| Internal audit attestation (technology audit universe) | Annual | PLN-08 | Chief Internal Auditor |
| Statement of Applicability (ISO 27001 Clause 6.1.3 d) review | Annual | CRMF | CISO |

### 2.2 RMC-level reporting (quarterly + ad-hoc)

| Topic | Frequency | Source framework | Owner |
|---|---|---|---|
| Technology risk register movement | Quarterly | TRMF | CRO |
| Incident metrics + material incidents | Quarterly | CRMF | CISO |
| Vulnerability posture | Quarterly | CRMF | CISO |
| Access review + privileged access | Quarterly | CRMF | Head of IAM |
| Change posture (incl. emergency change ratio) | Quarterly | TRMF | CIO |
| DR test outcomes | Quarterly | BCMF | COO |
| TPSP material reassessment status | Quarterly | TPRMF | Head of TPRM |
| Customer disclosure + DSAR posture | Quarterly | CIMF | DPO |
| NACSA notification and directive tracker | Quarterly | NCIIF | CISO + CCO |
| Awareness + competence KPIs | Quarterly | PLN-07 | CHRO + CISO |
| RMiT gap analysis position | Quarterly | All | CRO + CCO |
| Internal audit issue ageing | Quarterly | PLN-08 | Chief Internal Auditor |
| Information security objectives status | Quarterly | CRMF | CISO |

### 2.3 BAC-level reporting (quarterly)

| Topic | Frequency | Source |
|---|---|---|
| Internal audit issue dashboard + ageing | Quarterly | [REG-AUD](../06-registers/REG-AUD-internal-audit-issues-register.md) |
| NCII audit findings (NACSA) | Quarterly | [REG-NCA](../06-registers/REG-NCA-ncii-audit-findings-register.md) |
| Audit plan progress vs schedule | Quarterly | [PLN-08](../05-plans/PLN-08-internal-audit-plan.md) |
| Co-sourcing arrangements | Annual + on change | PLN-08 |

---

## 3. Escalation protocol — when the Board / Board Chair gets pulled in

This is the **single authoritative source** for "who calls the Chair." Operating detail (call scripts, out-of-band channels) sits in [PLN-01](../05-plans/PLN-01-incident-response-plan.md) Section 4 and [PLN-04](../05-plans/PLN-04-crisis-communications-plan.md).

### 3.1 Standing escalation rules

| Event | Who escalates | To whom | Within | Authority |
|---|---|---|---|---|
| **SEV-1 cyber incident declared** | CISO (IC) | CEO immediately; Board Chair via Company Secretary | **Immediate** (parallel to BNM notification clock) | This annex (Board ratified); [PLN-01 Section 6](../05-plans/PLN-01-incident-response-plan.md) |
| **SEV-2 cyber incident declared (assessed as material per [POL-04 Section 3](../02-policies/POL-04-information-security-policy.md))** | CISO + CRO | RMC Chair within 4 hours; Board Chair brief within 24 hours | 4 h / 24 h | This annex |
| **BNM notification to be made under RMiT 11.18** | CCO | CEO + RMC Chair + Board Chair immediately upon notification dispatch | **Immediate (parallel to BNM dispatch)** | This annex; [PLN-01 Section 6](../05-plans/PLN-01-incident-response-plan.md) |
| **NACSA notification to be made (NCII scope)** | CISO + CCO | CEO + RMC Chair + Board Chair immediately upon notification dispatch | **Immediate** | This annex; [POL-23](../02-policies/POL-23-ncii-operational-policy.md); [PLN-01 Section 6](../05-plans/PLN-01-incident-response-plan.md) |
| **PDPA-reportable personal-data breach** | DPO + CCO | RMC Chair + Board Chair brief | Within 24 hours of materiality determination | This annex; [POL-CI-02 Section 3.3](../02-policies/POL-CI-02-customer-consent-and-disclosure-policy.md) |
| **Activation of BCP at Tier-1 service** | COO | CEO + Board Chair | **Immediate** | [POL-14](../02-policies/POL-14-business-continuity-policy.md); [PLN-02 BCP](../05-plans/PLN-02-business-continuity-plan.md) |
| **Risk appetite breach in any zero-tolerance category** | CRO | RMC Chair within 24 hours; Board if RMC chair determines | 24 h | [POL-03](../02-policies/POL-03-technology-risk-appetite-statement.md) |
| **Material outsourcing — proposed entry, material change, or exit** | Head of Procurement + CRO | RMC for approval; Board notification per BNM Outsourcing PD | Prior to commitment | [POL-10](../02-policies/POL-10-it-vendor-management-policy.md); [POL-19](../02-policies/POL-19-supplier-security-policy.md) |
| **Shariah-related technology non-compliance** | CISO + Shariah Committee liaison | Board (with Shariah Committee in attendance) | At next regular Board sitting unless material | BNM Shariah Governance Framework |
| **Successful red team or pen test breach of Tier-1 control** | CISO | RMC Chair within 48 hours; Board if widespread | 48 h | This annex |
| **Material adverse audit finding (BAC or external)** | CIA | BAC Chair; Board if Critical | At BAC next meeting or sooner if Critical | [PLN-08](../05-plans/PLN-08-internal-audit-plan.md); BAC charter |

### 3.2 Chair-notification mechanics

- **Primary path:** Company Secretary calls the Board Chair on the registered mobile, with a one-page brief sent over the secure messaging channel.
- **Secondary path (Company Secretary unavailable):** the CEO calls the Board Chair directly.
- **Out-of-band:** the on-call card (per [PLN-01 Section 4](../05-plans/PLN-01-incident-response-plan.md)) contains the Board Chair contact, refreshed quarterly.
- **Failure mode:** if the Chair cannot be reached within 30 minutes for an immediate-escalation event, the Vice-Chair is contacted; failing that the Chair of the Board Risk Committee; the failure is logged in [REG-INC](../06-registers/REG-INC-incident-register.md).

### 3.3 What stays below the Board

These remain under management authority and are not Board events unless aggregated patterns emerge:

- Standard exceptions managed through [REG-EXC](../06-registers/REG-EXC-exception-register.md).
- Individual control failures absent material customer / financial / regulatory impact.
- Operational SLA misses.
- Vendor onboarding below materiality threshold.
- Technical patching cadence.
- DR test outcomes not raising new gaps.

---

## 4. Pre-positioned Board agenda content

For quarterly RMC and annual Board meetings, the following pack structure is pre-agreed — the Board does not chase format, the bank delivers format.

### 4.1 Quarterly RMC pack (Technology track)

1. Executive summary (1 page) — material movement since last RMC; this-quarter highlights / lowlights.
2. Risk dashboard (1 page) — top 10 risks; appetite breaches; emerging risks; movement.
3. Incident summary (1 page) — material incidents this quarter, BNM / NACSA notifications, PIR closure rate.
4. Vulnerability + access + change posture (1 page).
5. Third-party + cloud posture (1 page).
6. NCII + RMiT gap position (1 page).
7. Audit issue ageing (1 page).
8. Objective performance vs target (1 page).
9. Resource asks / escalations (1 page).

Pack delivered to RMC members **5 working days** before each meeting; questions taken from members **2 working days** before meeting via Company Secretary.

### 4.2 Annual Board pack (Technology track)

Above quarterly content rolled to annual view, plus:

- Annual cyber drill outcome with executive-team participation and Board observation summary.
- Annual ISMS / BCMS / AIMS Management Review attestation per ISO 27001 / 22301 / 42001 Clause 9.3 (drawing from [REG-MR](../06-registers/REG-MR-management-review-register.md)).
- Forward-look: regulatory horizon, threat landscape, planned investments.

---

## 5. Maintenance

- This annex is reviewed at every annual Board meeting and revised on framework change or protocol revision.
- All 9 framework Section 11 reporting tables are kept consistent with this annex; this annex is authoritative if they diverge.
- The escalation protocol is rehearsed at the annual cyber drill ([PLN-05](../05-plans/PLN-05-cyber-drill-exercise-plan.md)) and on every BCP activation tabletop.

## 6. Related documents

- **Architecture:** [00-architecture/architecture.md](architecture.md)
- **Framework Section 11 reporting tables:** [TRMF](../01-frameworks/TRMF.md), [CRMF](../01-frameworks/CRMF.md), [BCMF](../01-frameworks/BCMF.md), [TPRMF](../01-frameworks/TPRMF.md), [CIMF](../01-frameworks/CIMF.md), [NCIIF](../01-frameworks/NCIIF.md), [CloudRMF](../01-frameworks/CloudRMF.md), [DGF](../01-frameworks/DGF.md), [AIGF](../01-frameworks/AIGF.md)
- **Communication operational detail:** [PLN-01 Section 6](../05-plans/PLN-01-incident-response-plan.md); [PLN-04 Crisis Communications](../05-plans/PLN-04-crisis-communications-plan.md)
- **Risk appetite:** [POL-03 Technology Risk Appetite Statement](../02-policies/POL-03-technology-risk-appetite-statement.md)
- **Materiality:** [POL-04 Section 3 (Material technology incident)](../02-policies/POL-04-information-security-policy.md); [STD-IR-01](../03-standards/STD-IR-01-incident-classification-and-severity-standard.md)
- **Board sign-off conditions:** [07-document-control/board-signoff-conditions.md](../07-document-control/board-signoff-conditions.md)

## 7. Document control

| Version | Date | Author | Reviewer | Approver | Change summary |
|---|---|---|---|---|---|
| 1.0 | 2026-05-30 | CISO + CRO + Company Secretary | RMC | Board of Directors | Initial version. Closes "no consolidated Board Reporting Annex" and "no escalation-to-Chair protocol" gaps identified in v2 multi-agent review (Board member review). |
