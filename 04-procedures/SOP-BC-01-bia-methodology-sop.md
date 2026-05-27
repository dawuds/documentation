# SOP-BC-01 — BIA Methodology SOP

| | |
|---|---|
| **Document ID** | SOP-BC-01 | **Version** | 1.0 |
| **Owner / Approver** | Head of Business Continuity |
| **Parent standard** | [STD-BC-01](../03-standards/STD-BC-01-recovery-objectives-standard.md) | **Parent policy** | [POL-14](../02-policies/POL-14-business-continuity-policy.md) |

## 1. Purpose
Operationalise BIA execution — identifying critical services, dependencies, impact tolerances. Populates [REG-BIA](../06-registers/REG-BIA-business-impact-analysis-register.md).

## 2. Trigger
Annual BIA cycle; new service onboarding; material service change.

## 3. Procedure

| # | Actor | Action | Output |
|---|---|---|---|
| 1 | Head of BC | Initiate annual BIA cycle; calendar engagements with business heads | BIA programme schedule |
| 2 | Service owner | Inventory services in their domain | Service inventory |
| 3 | Service owner + Head of BC | Assess impact of disruption: financial, customer, regulatory, reputational, Shariah (where applicable) over disruption durations of 4h, 24h, 72h, 1wk, 2wk | Impact assessment grid |
| 4 | Service owner + Head of BC | Derive MTPD: maximum duration before material impact crystallises | MTPD |
| 5 | Service owner + IT (CIO delegate) | Derive RTO and RPO consistent with MTPD per [STD-BC-01](../03-standards/STD-BC-01-recovery-objectives-standard.md) | RTO, RPO |
| 6 | Service owner | Identify dependencies — upstream systems, data, suppliers, people | Dependency map |
| 7 | Service owner | Identify peak demand periods | Peak periods recorded |
| 8 | Service owner | Propose continuity strategy — alternate-site, alternate-supplier, manual workaround, technology failover | Strategy statement |
| 9 | Shariah Compliance (where Shariah-relevant) | Review continuity strategy for Shariah implications | Shariah review record |
| 10 | Head of BC | Compile entry into [REG-BIA](../06-registers/REG-BIA-business-impact-analysis-register.md) | REG-BIA entry |
| 11 | RMC | Approve BIA outputs annually | RMC paper |

## 4. Exception handling
Service owner unable to complete assessment within window: escalate to function head, then COO. Disagreement on RTO/RPO: COO decides; documented dissent.

## 5. Evidence
Impact assessments; dependency maps; REG-BIA entry; RMC approval. Retained 7 years.

## 6. Document control
| Version | Date | Author | Approver | Change |
|---|---|---|---|---|
| 1.0 | [Effective] | Head of BC | Head of BC | Initial |
