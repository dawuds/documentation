# STD-DG-02 — Data Retention Standard

| | |
|---|---|
| **Document ID** | STD-DG-02 | **Version** | 1.0 |
| **Owner / Approver** | CDO + Legal / CDO |
| **Parent policy** | [POL-11](../02-policies/POL-11-data-classification-policy.md) | **Parent framework** | [DGF](../01-frameworks/DGF.md) |

## 1. Purpose
Specify enterprise data retention beyond customer data — employee, vendor, product, transactional analytics, regulatory reporting, Shariah-Confidential, AI training data.

## 2. Scope
All data assets in [REG-DA](../06-registers/REG-DA-data-asset-register.md). Customer-data retention is in [STD-CI-02](STD-CI-02-customer-data-retention-standard.md).

## 3. Retention schedule

| Data class | Retention | Basis |
|---|---|---|
| Customer data | Per [STD-CI-02](STD-CI-02-customer-data-retention-standard.md) | BNM + PDPA + AMLA |
| Employee data (active) | Duration of employment | Operational |
| Employee data (post-termination) | 7 years | Labour law + dispute window |
| Vendor data | 7 years post-engagement | BNM record-keeping + contract |
| Product reference data (Islamic and conventional) | Permanent (versioned) | Audit + product history |
| Transactional analytics (de-identified) | 7 years | Audit + analytics value |
| AI model training data | Per model lifecycle + 3 years for re-validation | AIGF |
| Regulatory reporting submissions to BNM | Permanent | BNM record-keeping |
| Regulatory reporting submissions to NACSA | Permanent (per Code) | NACSA Code of Practice |
| Board / RMC / Audit Committee minutes | Permanent | Corporate record |
| Shariah Committee deliberations | Permanent | BNM SGF |
| Internal Audit working papers | 7 years post-report | Audit standard |
| Cyber incident records | 7 years; permanent for material per Board judgement | Forensic + audit |
| Cyber threat intelligence | 3 years (operational); permanent for material campaigns | SOC + threat intel value |
| System logs (production) | Per [STD-CR-02 Section 3.6](STD-CR-02-logging-standard.md) | Audit + forensic |
| Backup data | Per [STD-BC-02 Section 3.2](STD-BC-02-backup-and-restoration-standard.md) | Recovery |
| IT change records | 7 years | Audit + forensic |

## 4. Destruction
Per [POL-15 Section 3.7](../02-policies/POL-15-physical-and-environmental-security-policy.md); secure destruction at end of retention; certificate of destruction recorded.

## 5. Legal hold
Per [STD-CI-02 Section 5](STD-CI-02-customer-data-retention-standard.md).

## 6. Long-tail data
Data not explicitly listed above defaults to: business need + 3 years OR regulatory minimum, whichever longer. Data owner classifies on registration to [REG-DA](../06-registers/REG-DA-data-asset-register.md).

## 7. Exceptions
Reduced retention requires CDO + Legal + CCO joint approval.

## 8. Related documents
[STD-CI-02](STD-CI-02-customer-data-retention-standard.md); [POL-11](../02-policies/POL-11-data-classification-policy.md); [STD-DG-01](STD-DG-01-data-quality-standard.md); [STD-CR-02](STD-CR-02-logging-standard.md); [STD-BC-02](STD-BC-02-backup-and-restoration-standard.md); [REG-DA](../06-registers/REG-DA-data-asset-register.md); [SOP-DG-03 Data Destruction SOP](../04-procedures/SOP-DG-03-data-destruction-sop.md)

## 9. References
PDPA 2010 Section 10; AMLA 2001; FSA 2013; IFSA 2013; Labour Act 1955; BNM record-keeping requirements; BNM SGF.

## 10. Document control
| Version | Date | Author | Approver | Change |
|---|---|---|---|---|
| 1.0 | [Effective] | CDO + Legal | CDO | Initial |
