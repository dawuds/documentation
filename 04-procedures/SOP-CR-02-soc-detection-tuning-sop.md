# SOP-CR-02 — SOC Detection Tuning SOP

| | |
|---|---|
| **Document ID** | SOP-CR-02 | **Version** | 1.0 |
| **Owner / Approver** | Head of SOC |
| **Parent standard** | [STD-CR-02](../03-standards/STD-CR-02-logging-standard.md) | **Parent policy** | [POL-16](../02-policies/POL-16-operations-security-policy.md); [POL-13](../02-policies/POL-13-incident-management-policy.md) |

## 1. Purpose
Maintain detection-use-case quality — false-positive management, new-rule development, sunset of stale rules.

## 2. Trigger
- Recurring false positive (≥ 5 per week from a single rule)
- New threat intelligence requiring detection coverage
- Post-incident lesson (detection gap identified)
- Quarterly rule-portfolio review

## 3. Procedure

| # | Actor | Action | Output |
|---|---|---|---|
| 1 | SOC analyst | Identify rule needing attention (false positives or detection gap); raise tuning ticket | Tuning ticket |
| 2 | Detection Engineer | Investigate; classify (tune existing / replace / sunset / new rule) | Classification |
| 3 | Detection Engineer | Develop / update rule in non-production SIEM | Rule artefact |
| 4 | Detection Engineer | Test against historical data + simulated attacker behaviour | Test results |
| 5 | SOC Lead | Review and approve before production deployment | Approval |
| 6 | Detection Engineer | Deploy to production SIEM | Production rule |
| 7 | SOC analyst | Monitor for 30 days post-deployment for false-positive / true-positive balance | Tuning report |
| 8 | Detection Engineer | Update tuning ticket; close or iterate | Closure |

## 4. Quarterly portfolio review
| Activity | Owner |
|---|---|
| Inventory all detection rules with metrics (firing rate, true-positive rate) | Detection Engineer |
| Identify stale rules (no firing in 6 months) and high-false-positive rules | Detection Engineer |
| Sunset decisions documented | SOC Lead |
| Coverage gaps mapped to MITRE ATT&CK | Detection Engineer |
| Report to CISO | Head of SOC |

## 5. Evidence
Tuning tickets; rule artefacts in source control; test results; tuning report. Retained 7 years.

## 6. Document control
| Version | Date | Author | Approver | Change |
|---|---|---|---|---|
| 1.0 | [Effective] | Head of SOC | Head of SOC | Initial |
