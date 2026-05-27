# STD-DG-01 — Data Quality Standard

| | |
|---|---|
| **Document ID** | STD-DG-01 | **Version** | 1.0 |
| **Owner / Approver** | CDO / CDO |
| **Parent policy** | [POL-11](../02-policies/POL-11-data-classification-policy.md) | **Parent framework** | [DGF](../01-frameworks/DGF.md) |
| **Practice** | DAMA-DMBOK 2; ISO 8000 (Data Quality) |

## 1. Purpose
Specify data quality dimensions, target thresholds per data asset class, measurement cadence, and triage thresholds for GIBB data.

## 2. Scope
All data assets registered in [REG-DA](../06-registers/REG-DA-data-asset-register.md).

## 3. Requirements

### 3.1 Quality dimensions

| Dimension | Definition |
|---|---|
| Accuracy | Data correctly represents the real-world entity or event |
| Completeness | All required attributes are populated |
| Consistency | Same data is consistent across systems and time |
| Timeliness | Data is current within its consumption SLA |
| Validity | Data conforms to defined schema / business rules |
| Uniqueness | Each entity has one canonical record |

### 3.2 Target thresholds by data class

| Data class | Accuracy | Completeness | Consistency | Timeliness | Validity | Uniqueness |
|---|---|---|---|---|---|---|
| Customer master | ≥ 99% | ≥ 99% | ≥ 99% | Real-time / daily | ≥ 99% | ≥ 99.5% |
| Transactional | ≥ 99.9% | ≥ 99.9% | 100% (settled state) | Real-time | ≥ 99.9% | 100% |
| Reference data | 100% | 100% | 100% | Per-change | 100% | 100% |
| Analytical / derived | ≥ 95% | ≥ 95% | ≥ 95% | Per-cadence | ≥ 95% | n/a |
| AI training data | Per AIGF | Per AIGF | Per AIGF | Per use case | Per AIGF | Per AIGF |

### 3.3 Measurement cadence

| Class | Cadence |
|---|---|
| Customer master, transactional | Continuous automated |
| Reference data | On-change |
| Analytical / derived | Per-build |
| AI training data | Per-training cycle (with bias / fairness measurement per AIGF) |

### 3.4 Issue triage

| Severity | Definition | SLA |
|---|---|---|
| Critical | Data quality issue affecting Tier 0 service or regulatory reporting | Immediate triage; remediation in 7 days |
| High | Affecting Tier 1 service or material customer experience | Triage within 24h; remediation in 30 days |
| Medium | Affecting Tier 2 service or non-critical analytics | Triage within 5 business days; remediation in 90 days |
| Low | Cosmetic / non-impactful | Backlog |

### 3.5 Root cause categories

Data quality issues categorised at triage: source-system bug / user input error / integration error / definition mismatch / timing error / etc. Feeds back to source-side prevention.

### 3.6 Reporting

| Cadence | Report | Audience |
|---|---|---|
| Monthly | Data quality dashboard | Data Governance Committee |
| Quarterly | Quality trend + critical issues | RMC |
| Annually | Quality posture | Board (as part of TRMF reporting) |

## 4. Exceptions
Per [POL-11](../02-policies/POL-11-data-classification-policy.md). Sustained tolerance of sub-target quality requires CDO + CRO approval.

## 5. Related documents
[POL-11](../02-policies/POL-11-data-classification-policy.md); POL-DG-01 Data Quality Policy (future); [REG-DA](../06-registers/REG-DA-data-asset-register.md); REG-DQ Data Quality Register (future); [DGF](../01-frameworks/DGF.md)

## 6. References
DAMA-DMBOK 2; ISO 8000 series; ISO/IEC 25012 (Data quality model).

## 7. Document control
| Version | Date | Author | Approver | Change |
|---|---|---|---|---|
| 1.0 | [Effective] | CDO | CDO | Initial |
