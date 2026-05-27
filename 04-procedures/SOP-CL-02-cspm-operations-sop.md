# SOP-CL-02 — CSPM Operations SOP

| | |
|---|---|
| **Document ID** | SOP-CL-02 | **Version** | 1.0 |
| **Owner / Approver** | Head of Cloud + Head of SOC |
| **Parent standard** | [STD-CL-01 §3.5](../03-standards/STD-CL-01-cloud-security-standard.md) | **Parent policy** | [POL-20](../02-policies/POL-20-cloud-acceptable-use-policy.md) |

## 1. Purpose
Operationalise Cloud Security Posture Management — continuous monitoring of cloud configuration against baseline per [STD-CL-02](../03-standards/STD-CL-02-cloud-landing-zone-standard.md).

## 2. Trigger
Continuous. CSPM tooling generates findings; humans triage.

## 3. Procedure — finding triage

| # | Actor | Action | SLA |
|---|---|---|---|
| 1 | CSPM tooling | Generate finding (deviation from baseline or known-bad pattern) | Continuous |
| 2 | SOC analyst | Review finding; classify severity per [STD-CR-03](../03-standards/STD-CR-03-vulnerability-triage-standard.md) | ≤ 1 hour from generation for Critical; ≤ 4 hours for High |
| 3 | SOC analyst | Identify affected cloud account / workload / business owner | At classification |
| 4 | SOC analyst | Triage: false positive / acceptable risk / actionable | Per severity |
| 5 | Cloud Engineer (workload owner) | Remediate per [STD-CR-03 §3.3](../03-standards/STD-CR-03-vulnerability-triage-standard.md) timeline | Per timeline |
| 6 | SOC analyst | Verify remediation via CSPM re-scan | Within 24 hours of remediation |
| 7 | SOC analyst | Close finding | At verification |

## 4. Procedure — baseline drift

| # | Actor | Action |
|---|---|---|
| 1 | Head of Cloud | Periodic review of CSPM findings volume by category |
| 2 | Head of Cloud | Identify systemic drift patterns (e.g., recurring landing zone deviations) |
| 3 | Head of Cloud + CISO | Update [STD-CL-02](../03-standards/STD-CL-02-cloud-landing-zone-standard.md) baseline or remediation tooling |

## 5. Procedure — new finding-type incorporation

| # | Actor | Action |
|---|---|---|
| 1 | Head of Cloud + CISO | When CSPM vendor adds new finding types — review applicability |
| 2 | Head of Cloud + CISO | Enable new finding types; calibrate severity |
| 3 | SOC | Onboard new finding types into triage workflow |

## 6. Reporting
Monthly: SOC + Cloud joint report — findings volume, severity distribution, remediation SLA performance, drift patterns. To CISO + Head of Cloud; quarterly to RMC.

## 7. Evidence
CSPM finding tickets; remediation records; re-scan verification. Retained per [STD-CR-02 §3.6](../03-standards/STD-CR-02-logging-standard.md).

## 8. Document control
| Version | Date | Author | Approver | Change |
|---|---|---|---|---|
| 1.0 | [Effective] | Head of Cloud + Head of SOC | Head of Cloud | Initial |
