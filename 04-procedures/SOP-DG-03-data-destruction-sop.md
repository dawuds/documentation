# SOP-DG-03 — Data Destruction SOP

| | |
|---|---|
| **Document ID** | SOP-DG-03 | **Version** | 1.0 |
| **Owner / Approver** | Data Governance team + Head of IT Operations |
| **Parent standard** | [STD-DG-02](../03-standards/STD-DG-02-data-retention-standard.md); [STD-CI-02](../03-standards/STD-CI-02-customer-data-retention-standard.md); [POL-15 §3.7](../02-policies/POL-15-physical-and-environmental-security-policy.md) |
| **Parent framework** | [DGF](../01-frameworks/DGF.md); [CIMF](../01-frameworks/CIMF.md) |
| **Practice** | NIST SP 800-88 Rev. 1 |

## 1. Purpose
Securely destroy data at end of retention period; verify and document destruction.

## 2. Trigger
- Retention period reached per applicable retention standard
- Customer DSAR consent-withdrawal cascade (per [SOP-CI-01](SOP-CI-01-dsar-sop.md))
- Hardware decommissioning per [POL-09 §4.4](../02-policies/POL-09-it-asset-management-policy.md)
- Data asset retirement

## 3. Procedure — digital data destruction

| # | Actor | Action |
|---|---|---|
| 1 | Data steward | Confirm data has reached end of retention (no legal hold; no business need extension) |
| 2 | Data steward + Legal | Confirm no legal hold or pending litigation |
| 3 | Data steward | Identify all locations holding data (primary, backups, archives, derived datasets) per [REG-DA](../06-registers/REG-DA-data-asset-register.md) lineage |
| 4 | IT Operations | Execute destruction — cryptographic erasure (preferred for cloud) or overwriting per NIST SP 800-88 |
| 5 | IT Operations | Verify destruction (sample read attempts; metadata verification) |
| 6 | IT Operations | Generate destruction certificate with date, method, evidence |
| 7 | Data steward | Update [REG-DA](../06-registers/REG-DA-data-asset-register.md) status |
| 8 | DPO (if personal data) | Update [REG-ROPA](../06-registers/REG-ROPA-records-of-processing-activity.md) |

## 4. Procedure — physical media destruction

Per [POL-15 §3.7](../02-policies/POL-15-physical-and-environmental-security-policy.md) and NIST SP 800-88 Rev. 1 — physical destruction (shredding, degaussing) or sanitisation aligned to media type + classification.

## 5. Procedure — TPSP data destruction
Per [SOP-TP-03 §3 Phase 3](SOP-TP-03-tpsp-exit-sop.md) — TPSP destruction certificate obtained.

## 6. Special handling — Shariah-Confidential
Destruction of Shariah-Confidential data requires Shariah Committee notification; retention is typically permanent (per [STD-DG-02 §3](../03-standards/STD-DG-02-data-retention-standard.md)).

## 7. Evidence
Destruction certificates; verification records; REG-DA + REG-ROPA updates. Permanent (proves destruction was performed).

## 8. Document control
| Version | Date | Author | Approver | Change |
|---|---|---|---|---|
| 1.0 | [Effective] | Data Governance + IT Ops | CDO + Head of IT Ops | Initial |
