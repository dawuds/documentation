# REG-NC — NACSA Directive Tracker

| | |
|---|---|
| **Document ID** | REG-NC | **Owner** | CCO + CISO |
| **Cadence** | Continuous (per NACSA issuance) | **Parent framework** | [NCIIF](../01-frameworks/NCIIF.md) |

## Purpose
Authoritative tracker of all NACSA directives applicable to GIBB, with acknowledgement and implementation status.

## Schema
| Field | Description |
|---|---|
| `nc_id` | `NC-YYYY-NNN` |
| `directive_reference` | NACSA reference + issue date |
| `directive_subject` | Short subject |
| `applicability_to_gibb` | Universal / Conditional / N/A with reason |
| `received_date` | |
| `acknowledged_date` | Per Code timeline |
| `implementation_deadline` | NACSA-specified |
| `implementation_status` | Not started / In progress (%) / Implemented / N/A |
| `implementing_documents` | v2 documents updated to reflect directive |
| `evidence_link` | reference |
| `compliance_attestation` | If required by directive |
| `status` | Active / Superseded / Withdrawn |

## Worked example
| nc_id | reference | subject | applicability | implemented | status |
|---|---|---|---|---|---|
| NC-2026-001 | NACSA-CoP-v2.1 (2026-02-15) | Code of Practice update — enhanced incident reporting requirements | Universal | Implemented (POL-23, STD-NC-01, SOP-NC-01 updated) | Active |
| NC-2026-002 | NACSA Sector Directive FS-2026-03 | Quantum-safe cryptography readiness assessment due 2027 | Universal | In progress (Crypto post-quantum migration plan per [STD-CR-01 Section 3.7](../03-standards/STD-CR-01-cryptographic-standard.md)) | Active |
| NC-2026-003 | NACSA TIBER-MY framework guidance | Threat Intelligence-Based Ethical Red Teaming — voluntary alignment | Conditional (high-risk NCII; GIBB opts in) | In progress | Active |

## Related documents
[POL-23](../02-policies/POL-23-ncii-operational-policy.md); [REG-NCN](REG-NCN-nacsa-notification-register.md); [REG-CAP](REG-CAP-corrective-action-register.md); [NCIIF](../01-frameworks/NCIIF.md)
