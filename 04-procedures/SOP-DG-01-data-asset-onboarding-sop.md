# SOP-DG-01 — Data Asset Onboarding SOP

| | |
|---|---|
| **Document ID** | SOP-DG-01 | **Version** | 1.0 |
| **Owner / Approver** | Data Governance team (under CDO) |
| **Parent policy** | [POL-11](../02-policies/POL-11-data-classification-policy.md) | **Parent framework** | [DGF](../01-frameworks/DGF.md) |

## 1. Purpose
Onboard new data assets into GIBB data governance — classification, ownership, metadata, registration.

## 2. Trigger
New data asset created or acquired (new database, new dataset, new feed, new master / reference data set, new analytical output).

## 3. Procedure

| # | Actor | Action | Output |
|---|---|---|---|
| 1 | Data owner (function head) | Identify new data asset; submit onboarding request | Request |
| 2 | Data Governance team | Acknowledge; assign data steward (if not already assigned) | Steward assigned |
| 3 | Data owner | Classify per [POL-11](../02-policies/POL-11-data-classification-policy.md) — sensitivity + criticality | Classification |
| 4 | Data steward | Capture metadata per [STD-DG-03](../03-standards/STD-DG-03-metadata-standard.md) | Metadata captured |
| 5 | DPO | If personal data — add to [REG-ROPA](../06-registers/REG-ROPA-records-of-processing-activity.md); confirm lawful basis | ROPA entry |
| 6 | Shariah Compliance | If Shariah-relevant — confirm Shariah classification | Shariah review |
| 7 | Data Governance team | Register in [REG-DA](../06-registers/REG-DA-data-asset-register.md) | REG-DA entry |
| 8 | Data steward | Set up quality measurement per [STD-DG-01](../03-standards/STD-DG-01-data-quality-standard.md) | Quality monitoring |
| 9 | Data steward | Document lineage per [STD-DG-03](../03-standards/STD-DG-03-metadata-standard.md) | Lineage |
| 10 | Data owner | Confirm retention rule per [STD-DG-02](../03-standards/STD-DG-02-data-retention-standard.md) (and [STD-CI-02](../03-standards/STD-CI-02-customer-data-retention-standard.md) if customer data) | Retention rule |
| 11 | Data Governance team | Asset is Active status in REG-DA | Activation |

## 4. Procedure — AI training data
Additional steps per [STD-AI-04](../03-standards/STD-AI-04-ai-training-data-standard.md): bias assessment; provenance documentation; AIGC notification.

## 5. Exception handling
Asset created without onboarding (discovered): retrospective onboarding mandatory within 30 days; flagged as control deficiency.

## 6. Evidence
Onboarding request; classification record; metadata; ROPA entry (if applicable); REG-DA entry. Permanent (with asset).

## 7. Document control
| Version | Date | Author | Approver | Change |
|---|---|---|---|---|
| 1.0 | [Effective] | Data Governance team | CDO | Initial |
