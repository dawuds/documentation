# Incident Register

| | |
|---|---|
| **Document ID** | REG-INC |
| **Layer** | Register |
| **Owner** | CISO |
| **Cadence** | Continuous — entry created on every confirmed incident |
| **Implements** | ISO/IEC 27002:2022 controls 5.25, 5.26, 5.27; BNM RMiT (28 Nov 2025) §11.12–11.20 (Cyber Response, Recovery, Reporting); §11.13 (Cyber Incident Response Plan); §11.18 (Cyber Incident Notification to BNM) |
| **Source procedure** | [SOP-08-01 Incident Triage SOP](../03-procedures/incident-triage-sop.md); [PLN-08-01 Incident Response Plan](../04-plans/incident-response-plan.md) |

---

## Purpose

The authoritative record of all confirmed security incidents at General Bank. Captures the timeline, severity, category, materiality, response, notifications, and post-incident learning for each incident. Drives quarterly reporting to the Risk Management Committee.

## Schema

| Field | Type | Description |
|---|---|---|
| `incident_id` | string | `INC-YYYY-NNN` |
| `title` | string | Short title (≤ 120 chars) |
| `category` | enum (one or more) | Per [STD-08-01 §3.6](../02-standards/incident-classification-and-severity-standard.md) |
| `severity` | enum | SEV-1 / SEV-2 / SEV-3 / SEV-4 |
| `material` | bool | Per [STD-08-01 §3.2](../02-standards/incident-classification-and-severity-standard.md) |
| `detection_source` | enum | SIEM / EDR / DLP / User report / External / Other |
| `detected_at` | timestamp | First detection (vs. first acknowledgement) |
| `acknowledged_at` | timestamp | First responder accepted ownership |
| `declared_at` | timestamp | Severity formally classified |
| `contained_at` | timestamp | No further spread possible |
| `eradicated_at` | timestamp | Malicious presence removed |
| `recovered_at` | timestamp | Service fully restored, IoCs cleared |
| `closed_at` | timestamp | Enhanced monitoring period elapsed; PIR scheduled/complete |
| `mttd_minutes` | derived | Detection latency from earliest causal event |
| `mtta_minutes` | derived | `acknowledged_at - detected_at` |
| `mttc_minutes` | derived | `contained_at - detected_at` |
| `incident_commander` | role | Assigned IC |
| `regulator_notified` | bool + ref | If notified, regulator + date |
| `customer_notified` | bool + count | If customers notified, count + date |
| `affected_data_classification` | enum | None / Internal / Confidential / Highly Restricted |
| `affected_customers_count` | int | Where applicable |
| `corrective_actions` | reference | Link to action plan in PIR |
| `pir_complete` | bool | For SEV-1/SEV-2: PIR completed within 15 working days |
| `evidence_location` | reference | Where forensic and timeline evidence is held |
| `notes` | text | Brief narrative |

## Worked example — first entries (sanitised)

| incident_id | title | category | severity | material | detected | declared | contained | recovered | closed | mttd | mtta | mttc | IC | reg. notified | customers notified | PIR | notes |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| INC-2026-001 | Phishing campaign targeting finance team — 14 emails, 0 clicks | phishing | SEV-3 | No | 2026-02-04 09:12 | 2026-02-04 09:42 | 2026-02-04 10:30 | 2026-02-04 11:15 | 2026-02-11 | 30 | 18 | 78 | SOC Shift Lead | No | No | n/a | Generic phishing detected by gateway; sample reached 14 finance mailboxes; 0 clicks. Awareness comms issued. |
| INC-2026-007 | EDR-contained malware on developer endpoint (commodity loader) | malware | SEV-3 | No | 2026-02-19 22:48 | 2026-02-19 23:05 | 2026-02-19 23:20 | 2026-02-20 02:00 | 2026-02-27 | 22 | 17 | 32 | SOC Shift Lead | No | No | n/a | EDR auto-isolated endpoint. User credentials rotated as precaution. No lateral indicators. |
| INC-2026-014 | Targeted phishing campaign — 47 emails to retail banking team, 2 confirmed clicks | phishing | SEV-3 | No | 2026-03-04 08:30 | 2026-03-04 08:45 | 2026-03-04 11:55 | 2026-03-04 12:30 | 2026-03-05 | 15 | 15 | 205 | Head of SOC | No | No | n/a | 2 users clicked; one entered credentials. User account disabled within 8 min of click detection; password reset; MFA factor re-enrolled. No subsequent access from attacker IP space (blocked at perimeter). Pattern shared with sector CERT. |

### Quarterly metrics roll-up (illustrative — 2026 Q1)

| Metric | Value |
|---|---|
| Total incidents | 87 |
| SEV-1 | 0 |
| SEV-2 | 2 |
| SEV-3 | 19 |
| SEV-4 | 66 |
| Material incidents | 0 |
| Regulator notifications | 0 |
| Customer notifications | 0 |
| MTTD (SEV-2 mean) | 47 min |
| MTTA (SEV-2 mean) | 12 min |
| MTTC (SEV-2 mean) | 6h 22min |
| % SEV-1/SEV-2 with PIR completed within 15 working days | 100% (2/2) |
| Most frequent category | phishing (44 / 87) |
| % SOC SLA met (SEV-3+) | 96% (20 / 21) |

## Maintenance

- The IC (or SOC Shift Lead for SEV-3) creates the entry within 30 min of severity confirmation.
- Timestamps are populated as the response progresses, not retrospectively reconstructed.
- The CISO reconciles the register quarterly against the SOC monthly metrics report.
- Closed incidents remain in the register permanently; PIR outcomes are linked from the `corrective_actions` field.
- The register is the source for quarterly RMC reporting and for any external (regulator, certification, internal audit) request.

## Related documents

- **Parent policy:** [POL-08 Incident Management Policy](../01-policies/08-incident-management-policy.md)
- **Standard:** [STD-08-01 Incident Classification & Severity Standard](../02-standards/incident-classification-and-severity-standard.md)
- **Procedure:** [SOP-08-01 Incident Triage SOP](../03-procedures/incident-triage-sop.md)
- **Plan:** [PLN-08-01 Incident Response Plan](../04-plans/incident-response-plan.md)
- **Risk feedback:** [REG-RR Risk Register](risk-register.md)
