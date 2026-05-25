# Privileged Access Review Register

| | |
|---|---|
| **Document ID** | REG-PAR |
| **Layer** | Register |
| **Owner** | Head of Identity & Access Management |
| **Cadence** | **Quarterly** — full review of all privileged accounts |
| **Implements** | ISO/IEC 27002:2022 control 5.18 (Access rights); BNM RMiT (28 Nov 2025) §10.53–10.57 (Access Control), particularly §10.56 (User Access Matrix) and §10.57 (Access Monitoring and Logging) |
| **Source procedure** | [POL-02 §4.4.5](../01-policies/02-access-control-policy.md); [STD-02-01 §3.5](../02-standards/password-and-authentication-standard.md); [SOP-02-01](../03-procedures/joiner-mover-leaver-sop.md) |

---

## Purpose

To provide the auditable evidence record that General Bank conducts the quarterly privileged access reviews required by [POL-02 §4.4.5](../01-policies/02-access-control-policy.md). This is the register an internal or external auditor will request to verify the control is operating, not theoretical.

## Schema

| Field | Type | Description |
|---|---|---|
| `review_id` | string | `PAR-YYYY-QN` (year + quarter) |
| `review_period` | date range | Period under review |
| `total_privileged_accounts_in_scope` | int | Count at review start |
| `accounts_reviewed` | int | Count actually reviewed |
| `coverage_percent` | derived | Reviewed / In-scope |
| `accounts_recertified` | int | Confirmed retain |
| `accounts_modified` | int | Reduced or scope-changed |
| `accounts_revoked` | int | Removed entirely |
| `exceptions_raised` | int | New exceptions logged |
| `escalations` | int | Issues escalated to CISO/RMC |
| `review_started` | date | First review item opened |
| `review_completed` | date | Final item closed |
| `evidence_location` | reference | Where the per-account evidence is held |
| `signed_off_by` | role + name | Head of IAM + CISO |
| `signed_off_date` | date | |
| `notes` | text | Trends, findings, follow-up |

## Worked example — first reviews

| review_id | period | in_scope | reviewed | coverage | recert | modified | revoked | exceptions | escalations | completed | signed off |
|---|---|---|---|---|---|---|---|---|---|---|---|
| PAR-2026-Q1 | 2026-01-01 → 2026-03-31 | 412 | 412 | 100% | 396 | 9 | 7 | 3 | 0 | 2026-03-18 | Head of IAM 2026-03-19; CISO 2026-03-20 |

### Per-application breakdown (PAR-2026-Q1 illustrative)

| Application | Owner | Accounts | Reviewed | Recert | Modified | Revoked |
|---|---|---|---|---|---|---|
| Active Directory — Domain Admins | Head of IT Ops | 12 | 12 | 11 | 0 | 1 (departed staff retained in error from prior quarter — root cause: SOP-02-01 step L3 latency on the day; fixed) |
| Core Banking — Production Admin | Head of Core Banking | 18 | 18 | 17 | 1 | 0 |
| PAM platform admins | Head of IAM | 6 | 6 | 6 | 0 | 0 |
| Cloud — Production Org Admin | Head of Cloud Engineering | 9 | 9 | 8 | 1 | 0 |
| Cloud — Production project IAM admins | Application owners | 84 | 84 | 80 | 2 | 2 |
| Database admins (production estate) | DBA Lead | 47 | 47 | 45 | 1 | 1 |
| Network admins | Head of Network | 28 | 28 | 27 | 0 | 1 |
| SIEM / SOAR admins | Head of SOC | 11 | 11 | 11 | 0 | 0 |
| EDR admins | Head of SOC | 8 | 8 | 8 | 0 | 0 |
| Firewall admins | Head of Network | 14 | 14 | 14 | 0 | 0 |
| HR system admins | CHRO | 7 | 7 | 6 | 1 | 0 |
| Treasury / payments admins | Head of Treasury Ops | 23 | 23 | 21 | 1 | 1 |
| ... (remaining applications) | | 145 | 145 | 142 | 2 | 1 |
| **Total** | | **412** | **412** | **396** | **9** | **7** |

### Notes from PAR-2026-Q1

- The single revocation in Active Directory Domain Admins traced back to a leaver event with delayed disablement. Root cause: SOP-02-01 step L3 (automation) succeeded but a manual back-out by a separate workflow re-enabled the account. Process fix applied; verification scheduled into PAR-2026-Q2.
- Treasury / payments revocation related to a role change where the prior privileged role was not removed at the Mover step. Strengthened the [SOP-02-01 §5.2](../03-procedures/joiner-mover-leaver-sop.md) explicit removal language in the v1.1 minor update.
- Coverage 100% maintained; no overdue reviews.
- No escalations to RMC required this quarter.
- Trend (vs PAR-2025-Q4): 7 revocations (down from 11); reflects the JML mover-step strengthening introduced after PAR-2025-Q3.

## Maintenance

- The review is **executed**, not just **documented**. Each application's reviewer must positively confirm or modify each privileged entitlement; absence of response is treated as "not reviewed" and escalated.
- Quarter-on-quarter trend lines are reviewed by the CISO; sustained increase in revocations or exceptions indicates a process failure upstream.
- Findings feed into the [Risk Register](risk-register.md) where they relate to broader control issues.

## Related documents

- **Parent policy:** [POL-02 Access Control Policy](../01-policies/02-access-control-policy.md)
- **Parent standard:** [STD-02-01 Password & Authentication Standard](../02-standards/password-and-authentication-standard.md)
- **Source procedure:** [SOP-02-01 Joiner / Mover / Leaver SOP](../03-procedures/joiner-mover-leaver-sop.md)
- **SoA:** [REG-SOA](statement-of-applicability.md) — control 5.18
