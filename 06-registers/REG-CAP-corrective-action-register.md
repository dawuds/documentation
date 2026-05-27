# REG-CAP — Corrective Action Register

| | |
|---|---|
| **Document ID** | REG-CAP | **Owner** | CRO (consolidates from all sources) |
| **Cadence** | Continuous | **Parent framework** | [TRMF](../01-frameworks/TRMF.md) |
| **Implements** | RMiT Section 9.2(g) continuous monitoring; ISO/IEC 27001:2022 Clause 10.1 (Nonconformity and corrective action) |

## Purpose
Unified register of corrective actions arising from any source — Internal Audit, BNM examination, NACSA findings, ISO 27001 surveillance, incident PIRs, exception expiries, drill outcomes, KRI breaches. Tracks remediation to closure across the cascade.

## Schema

| Field | Description |
|---|---|
| `cap_id` | `CAP-YYYY-NNNN` |
| `source` | Internal Audit / BNM / NACSA / ISO surveillance / Incident PIR / Drill / KRI / Other |
| `source_reference` | Audit finding ID / examination report ref / etc. |
| `description` | Finding / gap / required action |
| `severity` | Critical / High / Medium / Low |
| `business_impact` | text |
| `responsible_role` | Action owner |
| `function_area` | CRMF / TRMF / BCMF / TPRMF / CIMF / NCIIF / CloudRMF / DGF / AIGF / Cross |
| `linked_risks` | [REG-TR](REG-TR-technology-risk-register.md) RISK-IDs |
| `committed_date` | Original due date |
| `revised_date` | If extended |
| `progress_status` | Not started / In progress (%) / Complete / Verified closed |
| `evidence_required_for_closure` | text |
| `closure_evidence_link` | reference |
| `verifier` | Role |
| `verified_date` | date |
| `overdue` | bool |
| `escalation_status` | Per overdue duration |
| `status` | Open / In progress / Closed / Verified closed |

## Worked example — first entries (illustrative)

| cap_id | source | description | severity | owner | due | status |
|---|---|---|---|---|---|---|
| CAP-2026-0023 | Internal Audit FY2026 | CMDB completeness 88% (target 95%) | Medium | Head of IT Ops | 2026-09-30 | In progress (40%) |
| CAP-2026-0024 | BNM Examination 2026 | Cloud landing zone documentation gap | High | Head of Cloud | 2026-07-15 | In progress (60%) |
| CAP-2026-0025 | Cyber Drill 2025 — annual | Out-of-band communication contact list 28% out-of-date | High | Head of Corp Comms + CISO | 2026-06-30 | Verified closed (2026-05-20) |
| CAP-2026-0026 | INC-2026-014 PIR | Phishing simulation cadence — current quarterly insufficient | Medium | CISO | 2026-08-31 | In progress (monthly cadence rolled out from Q2) |
| CAP-2026-0027 | ISO 27001 surveillance | Vendor risk assessment refresh on 2 Tier-1 TPSPs overdue | Medium | Head of Procurement | 2026-04-30 | Verified closed (2026-04-22) |
| CAP-2026-0028 | NACSA examination finding | Specific control under Code of Practice §X.Y requires evidence enhancement | High | CISO + CCO | 2026-09-30 | In progress |
| CAP-2026-0029 | KRI breach — REG-TR | Material risks above appetite > 5 in Q1 | High | CRO | 2026-06-30 | In progress (treatment plans for 3 of 7 in execution) |

## Maintenance
- Source functions create entries; CRO consolidates.
- Weekly Action Owner status update for High and Critical.
- Monthly CRO consolidated reporting to ExCo.
- Quarterly RMC review.
- Overdue High/Critical: automatic CRO escalation.

## Related documents
All Layer 2 frameworks; [REG-TR](REG-TR-technology-risk-register.md); [REG-INC](REG-INC-incident-register.md); [REG-EXC](REG-EXC-exception-register.md); Internal Audit findings; BNM examination reports; NACSA findings.
