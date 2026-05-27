# REG-DRL — Cyber Drill Register

| | |
|---|---|
| **Document ID** | REG-DRL | **Owner** | CISO |
| **Classification** | Internal | **Cadence** | Per exercise |
| **Parent framework** | [CRMF](../01-frameworks/CRMF.md) |
| **Source procedure** | [SOP-CR-01](../04-procedures/SOP-CR-01-cyber-drill-exercise-sop.md) |
| **Implements** | RMiT 11.16 (Annual Cyber Drill Exercise) evidence |

## Purpose
Authoritative record of every cyber drill exercise at GIBB — tabletop, functional, full drill, red team. Primary evidence of RMiT 11.16 annual cyber drill compliance, examined by BNM.

## Schema

| Field | Description |
|---|---|
| `drl_id` | `DRL-YYYY-NNN` |
| `exercise_name` | Title |
| `exercise_type` | Tabletop / Functional / Full drill (RMiT 11.16) / Joint / Red team |
| `scenario` | Scenario class (ransomware, insider, etc.) |
| `scope` | Systems / functions exercised |
| `executive_participation` | bool — for RMiT 11.16 full drill, must be Yes |
| `external_facilitator` | bool + provider name |
| `planned_date` / `executed_date` | dates |
| `duration` | hours / days |
| `participants` | count + roles |
| `objectives` | Listed from drill charter |
| `mttd_target` / `mttd_achieved` | per STD-IR-01 |
| `mttc_target` / `mttc_achieved` | per STD-IR-01 |
| `bnm_notification_simulated` | bool |
| `nacsa_notification_simulated` | bool (if NCII-scope scenario) |
| `out_of_band_comms_tested` | bool (RMiT 11.15) |
| `shariah_implications_exercised` | bool (if scenario Shariah-relevant) |
| `findings_count` | int |
| `findings_summary` | text |
| `action_items_count` | int |
| `action_items_open` | int |
| `action_items_overdue` | int |
| `rmc_reported` | date |
| `rmit_11_16_satisfied` | bool — for the annual full drill |
| `status` | Planned / In progress / Debrief / Closed |

## Worked example — first entries (illustrative)

| drl_id | exercise | type | scenario | executive | date | mttd | mttc | findings | rmit_11_16 | status |
|---|---|---|---|---|---|---|---|---|---|---|
| DRL-2026-Q1-01 | Q1 Tabletop — Insider abuse | Tabletop | Insider | No | 2026-03-18 | n/a (simulated) | n/a | 4 (3 closed, 1 open) | n/a | Closed |
| DRL-2026-Q2-01 | Q2 Tabletop — Ransomware | Tabletop | Ransomware | No | 2026-06-12 | n/a | n/a | 6 (2 closed, 4 open) | n/a | In progress |
| **DRL-2026-FULL** | **Annual Cyber Drill 2026 — Destructive ransomware affecting tier-0 production estate** | **Full drill (RMiT 11.16)** | Ransomware | **Yes (full executive engagement)** | 2026-09-15 to 2026-09-16 (2 days) | 35 min (target ≤ 30) | 5h 12min (target ≤ 4h) | 18 (containment success; recovery exceeded target; out-of-band comms passed; BNM notification simulated within 4h) | **Yes — RMiT 11.16 satisfied** | Debrief |
| DRL-2026-Q3-01 | Q3 Tabletop — Supplier compromise (TPSP-0001 IaaS) | Tabletop | Supplier compromise | No | 2026-09-25 | n/a | n/a | (pending) | n/a | Planned |
| DRL-2026-RED-01 | Annual Red Team Operation | Red team | (per scope) | (selective) | 2026-08-01 to 2026-09-15 (6-week operation) | n/a (covert) | n/a | (in scope) | n/a | In progress |

## Maintenance

- CISO creates entry at exercise planning; updates through execution, debrief, closure.
- RMiT 11.16 satisfaction explicitly flagged on annual full drill row; auditor-checkable.
- Action items tracked to closure; overdue items reported to RMC.
- Permanent retention.

## Related documents
[SOP-CR-01](../04-procedures/SOP-CR-01-cyber-drill-exercise-sop.md); [PLN-05](../05-plans/PLN-05-cyber-drill-exercise-plan.md); [PLN-01 IRP](../05-plans/PLN-01-incident-response-plan.md); [REG-INC](REG-INC-incident-register.md).
