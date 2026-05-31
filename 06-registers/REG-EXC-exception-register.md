# REG-EXC — Exception Register

| | |
|---|---|
| **Document ID** | REG-EXC | **Owner** | ISMS Manager (under CISO) |
| **Classification** | Internal | **Cadence** | Continuous |
| **Implements** | TRMF Section 12 (exception management) — cross-framework |

## Purpose
Authoritative record of all documented exceptions to GIBB policies, standards, and procedures. Every exception time-bound; every exception with compensating control; every exception with named approver. Primary input to RMC quarterly exception review.

## Schema

| Field | Type | Description |
|---|---|---|
| `exc_id` | string | `EXC-YYYY-NNN` |
| `affected_document` | reference | The policy / standard / SOP being excepted |
| `exception_type` | enum | Framework principle / Policy / Standard / Procedure |
| `requested_by` | role | Owner of the area requesting exception |
| `request_date` | date | |
| `description` | text | What is being excepted and why |
| `business_justification` | text | Why exception is needed |
| `compensating_control` | text | What reduces residual risk during exception period |
| `approver` | role | Per authority matrix (TRMF Section 12) |
| `approval_date` | date | |
| `start_date` / `end_date` | date | Time-bound; maximum 12 months |
| `renewal_status` | enum | Original / First renewal / Beyond first renewal (RMC required) |
| `linked_risks` | reference | RISK-YYYY-NNN entries in [REG-TR](REG-TR-technology-risk-register.md) |
| `review_cadence` | enum | Monthly / Quarterly per residual risk |
| `closure_action` | text | What is needed to close — patch, replace, etc. |
| `status` | enum | Active / Renewed / Closed / Expired |

## Authority matrix (per TRMF Section 12)

| Exception type | Approver | Max duration | Renewal |
|---|---|---|---|
| Framework principle | Board RMC | 12 months | RMC (one); then Board |
| Policy | RMC | 12 months | RMC (one) |
| Standard | CISO / function head | 12 months | RMC after one |
| Procedure | Process owner | 6 months | Owner (one); then standard exception |

## Worked example — first entries (illustrative)

| exc_id | document | type | requested | description | compensator | approver | end | status |
|---|---|---|---|---|---|---|---|---|
| EXC-2026-001 | STD-AC-01 Section 3.5.3 (urgent leaver MFA disablement timing) | Standard | Head of IAM | Legacy mainframe accounts cannot be disabled within 30 min — limitation of mainframe IAM tooling | Detective monitoring with 1-hour alert; replacement project Q4 2026 | CISO | 2027-03-31 | Active |
| EXC-2026-002 | POL-18 (vuln remediation SLA — High on internal) | Policy | Head of IT Ops | Specific legacy SAP module cannot be patched within SLA due to vendor support cycle | Network segmentation; WAF rule; enhanced monitoring | RMC | 2027-06-30 | Active |
| EXC-2026-003 | STD-CR-01 Section 3.1 (deprecation of 3DES by 2026-12-31) | Standard | Head of Treasury Ops | Legacy SWIFT integration uses 3DES; vendor upgrade scheduled Q1 2027 | TLS tunnel; access restriction | CISO | 2027-03-31 | Active |
| EXC-2026-004 | POL-20 Section 4.8 (RMiT Appendix 10 departure) | Policy | Head of Cloud | Identity provider — single-region service, not available in MY-region | Documented justification; key residency in MY-region cloud KMS | RMC | 2027-12-31 (annual) | Active |

## Maintenance

- New exception requires complete submission with all schema fields populated.
- Monthly: ISMS Manager review of expiring exceptions (30-day lookahead).
- Quarterly: RMC review of all active exceptions; trend analysis.
- Pattern recognition: ≥ 3 exceptions in same area triggers review of underlying document (revise rather than exception).

## Related documents
TRMF Section 12; [REG-TR](REG-TR-technology-risk-register.md); all Layer 2 frameworks (each references this register).
