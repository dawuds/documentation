# SOP-CI-02 — Customer Data Breach Notification SOP

| | |
|---|---|
| **Document ID** | SOP-CI-02 | **Version** | 1.0 |
| **Owner / Approver** | DPO + CCO + CISO |
| **Parent policy** | [POL-CI-01 Section 4.5](../02-policies/POL-CI-01-customer-data-protection-policy.md); [POL-13](../02-policies/POL-13-incident-management-policy.md) | **Parent framework** | [CIMF](../01-frameworks/CIMF.md); [CRMF](../01-frameworks/CRMF.md) |

## 1. Purpose
Operationalise the assessment, notification, and remediation pathway for incidents potentially involving customer data — coordinating PDPA, BNM, NACSA (if NCII-scope), and customer notifications.

## 2. Trigger
Confirmed or suspected customer data confidentiality breach. Detected via [SOP-IR-01 Incident Triage](SOP-IR-01-incident-triage-sop.md). Trigger event flagged as customer-data-relevant in triage.

## 3. Procedure

### Step 1 — Initial assessment

| # | Actor | Action | Output | SLA |
|---|---|---|---|---|
| 1 | DPO (engaged by CISO from incident triage) | Assess scope: data classes affected, customer count, sensitivity per [STD-CI-01](../03-standards/STD-CI-01-customer-data-classification-standard.md) | Initial impact assessment | ≤ 2 hours from confirmation |
| 2 | DPO + CCO | Determine PDPA notification threshold (sensitive personal data; risk to data subjects) | PDPA threshold decision | ≤ 4 hours |
| 3 | CCO | Determine BNM notification threshold per [STD-IR-01 Section 3.5](../03-standards/STD-IR-01-incident-classification-and-severity-standard.md) and Operational Risk Reporting Part C | BNM threshold decision | ≤ 4 hours |
| 4 | CCO + CISO | If NCII-scope, determine NACSA notification per [STD-NC-01](../03-standards/STD-NC-01-nacsa-notification-standard.md) | NACSA threshold decision | ≤ 4 hours |

### Step 2 — Regulator notification

| # | Actor | Action | Tool | Output | SLA |
|---|---|---|---|---|---|
| 5 | CCO | If BNM material — submit BNM notification | Per BNM channel | BNM notification submitted | Within 4 hours of detection (source-chain caveat per [POL-13 Section 4.4.3](../02-policies/POL-13-incident-management-policy.md)) |
| 6 | CCO | If NACSA NCII — submit NACSA notification | Per NACSA channel | NACSA notification submitted in [REG-NCN](../06-registers/REG-NCN-nacsa-notification-register.md) | Per current NACSA timelines |
| 7 | DPO | If PDPA threshold — assess Commissioner notification (PDPA does not currently mandate breach notification but voluntary best practice + risk-based assessment) | DPO documented assessment | Within 72 hours of awareness |

### Step 3 — Customer notification

| # | Actor | Action | Output | SLA |
|---|---|---|---|---|
| 8 | DPO + Communications Lead + Legal | Decide on customer notification — necessity, scope, channel, content | Customer notification decision | Within 5 business days of confirmation |
| 9 | Communications Lead | Draft customer notice; Legal review; CCO sign-off | Approved customer notice | Per decision |
| 10 | Communications Lead | Issue customer notification | Email / SMS / app secure message / letter | Per timeline approved |
| 11 | Customer Operations | Stand up dedicated customer enquiry handling | Customer enquiry team | Pre-notification |

### Step 4 — Record and remediate

| # | Actor | Action | Output |
|---|---|---|---|
| 12 | DPO | Record in [REG-CDB Customer Data Breach Register](../06-registers/REG-CDB-customer-data-breach-register.md) | Register entry |
| 13 | DPO + CISO | Remediation actions (containment + preventive) | Remediation tracked in [REG-INC](../06-registers/REG-INC-incident-register.md) |
| 14 | DPO | Lessons feed into PIR per [POL-13 Section 4.7](../02-policies/POL-13-incident-management-policy.md) | PIR document |

## 4. Exception handling
Where regulator-imposed gag order or active law-enforcement investigation: customer notification deferred under General Counsel direction; regulator notifications still proceed.

## 5. Evidence
DPO assessment; CCO/BNM/NACSA notification evidence; customer notice copy; remediation evidence. Retained 7 years.

## 6. Document control
| Version | Date | Author | Approver | Change |
|---|---|---|---|---|
| 1.0 | [Effective] | DPO + CCO + CISO | DPO | Initial |
