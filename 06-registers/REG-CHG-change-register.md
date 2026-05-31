# Change Register

| | |
|---|---|
| **Document ID** | REG-CHG |
| **Layer** | Register |
| **Owner** | Head of IT Operations (operating); CIO (accountable) |
| **Cadence** | Continuous — entry per change ticket; 30-day post-implementation review cycle |
| **Implements** | ISO/IEC 27002:2022 control 8.32 (Change management); ITIL 4 Change Enablement practice; BNM RMiT (28 Nov 2025) Section 10.5–10.11 (Project Management, System Development Lifecycle, and Change Management); particularly Section 10.10 (Change Management) and Section 10.11 (Independent Review of Changes) |
| **Source procedure** | [SOP-CM-01 Change Authorisation SOP](../04-procedures/SOP-CM-01-change-authorisation-sop.md); [SOP-CM-02 Emergency Change SOP](../04-procedures/SOP-CM-02-emergency-change-sop.md); [STD-CM-01 Change Management Standard](../03-standards/STD-CM-01-change-management-standard.md) |
| **Parent framework(s)** | [TRMF](../01-frameworks/TRMF.md) |
| **COBIT objective(s)** | BAI06 Managed IT Changes; BAI07 Managed IT Change Acceptance and Transitioning |

---

## Purpose

The authoritative evidence record that GIBB operates change management as specified by [POL-07 Change Management Policy](../02-policies/POL-07-change-management-policy.md) and [STD-CM-01](../03-standards/STD-CM-01-change-management-standard.md). The register **closes the BAI06 cascade** — without it, an examiner asking "show me the last 90 days of changes with independent-reviewer sign-off" has nowhere to look.

In a production environment this is typically a view over the change-ticket system (ServiceNow, Jira, Remedy). The register defined here is the canonical schema and the source of truth for control evidence. Where the ticket system is the system of record, this register is the **GRC-side mirror** maintained by automation.

## Schema

| Field | Type | Description |
|---|---|---|
| `change_id` | string | `CHG-YYYY-NNNNN` |
| `title` | string | Short description |
| `type` | enum | `Normal` / `Standard` / `Emergency` |
| `risk_class` | enum | Per [STD-CM-01 Section 3.2](../03-standards/STD-CM-01-change-management-standard.md) — `Low` / `Medium` / `High` / `Critical` |
| `affected_systems` | array | Asset IDs from [REG-DA](REG-DA-data-asset-register.md) and CMDB |
| `customer_facing` | bool | Triggers CEO/delegate approval per [POL-07 Section 4.3](../02-policies/POL-07-change-management-policy.md) |
| `requestor` | role | Who is asking for the change |
| `sponsor` | role | Accountable owner of the affected service |
| `independent_reviewer` | role | **Required per RMiT Section 10.11** — name + date — must NOT be the requestor or implementer |
| `security_review` | role + date | CISO delegate sign-off where security-impacting |
| `shariah_review` | role + date | Where the change affects a Shariah-compliant product (per [POL-07 Section 4.5](../02-policies/POL-07-change-management-policy.md)) |
| `cab_decision` | enum + date | `Approved` / `Rejected` / `Deferred` / `Conditional` + CAB minutes link |
| `scheduled_window_start` | timestamp | When the change is planned to deploy |
| `scheduled_window_end` | timestamp | Deployment window end |
| `actual_deployment_start` | timestamp | Actually-deployed start |
| `actual_deployment_end` | timestamp | Actually-deployed end |
| `outcome` | enum | `Success` / `Success-with-issues` / `Backed-out` / `Failed` |
| `incident_caused` | bool + ref | Link to [REG-INC](REG-INC-incident-register.md) if the change caused a SEV-2+ incident |
| `pir_required` | bool | `True` for all Emergency + all `Backed-out`/`Failed` + sample of Normal/Standard |
| `pir_complete` | bool | Within 30 days of `actual_deployment_end` |
| `pir_outcome` | text | Lessons learned; corrective actions; link to action plan |
| `notification_to_fsc` | bool + date | For customer-facing changes per RMiT digital services notification convention |
| `notes` | text | Brief narrative |

## Worked example — first entries (illustrative)

| change_id | title | type | risk | indep. reviewer | sec. review | CAB decision | window | outcome | incident | PIR | notes |
|---|---|---|---|---|---|---|---|---|---|---|---|
| CHG-2026-00041 | Internet banking — TLS 1.3 enforcement | Normal | Medium | Senior Network Architect (B. Lim) — 2026-02-02 | CISO delegate — 2026-02-02 | Approved 2026-02-03 | 2026-02-08 02:00–04:00 | Success | No | Pending (PIR-2026-00041) | Phased over 4 weekends; no customer impact observed. |
| CHG-2026-00067 | Core banking — quarterly patch bundle | Normal | High | Core Banking SME (R. Tan) — 2026-02-14 | CISO delegate — 2026-02-14 | Approved 2026-02-15 | 2026-02-22 22:00 – 2026-02-23 02:00 | Success | No | Complete 2026-03-20 — no findings | Includes one HIGH-severity vendor patch. |
| CHG-2026-00098 | Customer portal — feature release `m2.7` | Standard | Low | Tech lead pre-approved standard model | n/a (no security delta) | Standard model pre-approved | 2026-03-02 10:00–10:30 | Success | No | Standard sampling — not required this cycle | One of 12 std model deployments in Q1. |
| CHG-2026-00104 | Core banking — emergency patch CVE-2026-XXXX | Emergency | Critical | Head of IT Ops (post-implementation) — 2026-03-04 | CISO — 2026-03-03 | Emergency authority — 2026-03-03 | 2026-03-03 16:30–17:15 | Success-with-issues | No | Complete 2026-03-30 — corrective: improve pre-prod CVE intel feed | Patch released by vendor 2026-03-03 06:00; KEV-listed; deployed within 11 hours of release. |
| CHG-2026-00131 | Cloud landing zone — region failover test | Normal | Medium | Cloud Architect (peer team) — 2026-03-18 | CISO delegate — 2026-03-18 | Approved with conditions 2026-03-19 | 2026-03-29 04:00–06:00 | Backed-out | INC-2026-021 (SEV-3) | Complete 2026-04-25 — corrective: pre-flight checklist updated | Failover succeeded; failback exposed an unmonitored DNS dependency; rolled back; no customer impact. |

### Quarterly metrics roll-up (illustrative — 2026 Q1)

| Metric | Value |
|---|---|
| Total changes | 412 |
| Normal | 217 |
| Standard | 188 |
| Emergency | 7 |
| Customer-facing | 38 |
| % with Independent Reviewer documented | 100% (Normal + Emergency) |
| % completed within scheduled window | 96% |
| % Backed-out | 1.2% (5 / 412) |
| % Failed | 0.2% (1 / 412) |
| Change-caused incidents (SEV-2+) | 1 |
| Emergency change ratio | 1.7% (target < 3%) |
| % PIRs completed within 30 days (Emergency + Failed/Backed-out) | 100% (8/8) |

## Maintenance

- Change tickets are the system of record. The register is the canonical schema; ticket-system extracts must conform.
- Independent reviewer field is **mandatory and non-bypassable** for `Normal` and `Emergency` changes. Standard model changes inherit the standing review.
- PIR completion within 30 days is monitored as a control KPI; outliers are escalated to CIO weekly.
- Quarterly metrics roll-up feeds RMC; annual roll-up feeds Board through TRMF Section 11 reporting.
- Where the change ticket records a backed-out or failed change with customer impact, the link to [REG-INC](REG-INC-incident-register.md) is mandatory.

## Related documents

- **Parent policy:** [POL-07 Change Management Policy](../02-policies/POL-07-change-management-policy.md)
- **Standard:** [STD-CM-01 Change Management Standard](../03-standards/STD-CM-01-change-management-standard.md)
- **Procedures:** [SOP-CM-01 Change Authorisation SOP](../04-procedures/SOP-CM-01-change-authorisation-sop.md); [SOP-CM-02 Emergency Change SOP](../04-procedures/SOP-CM-02-emergency-change-sop.md)
- **Cross-references:** [REG-INC](REG-INC-incident-register.md) (change-caused incidents); [REG-VUL](REG-VUL-vulnerability-register.md) (vulnerability remediation tracked through change); [REG-EXC](REG-EXC-exception-register.md) (deviations from STD-CM-01); [REG-CAP](REG-CAP-corrective-action-register.md) (PIR-driven corrective actions)

## Document control

| Version | Date | Author | Reviewer | Approver | Change summary |
|---|---|---|---|---|---|
| 1.0 | 2026-05-30 | Head of IT Operations | CIO | CIO | Initial version. Closes BAI06 cascade per v2 multi-agent review finding (IT Governance Expert + CIO agreed: cascade ends at SOP with no register; this register is the canonical control evidence). |
