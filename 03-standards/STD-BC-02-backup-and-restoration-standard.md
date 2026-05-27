# STD-BC-02 — Backup and Restoration Standard

| | |
|---|---|
| **Document ID** | STD-BC-02 | **Version** | 1.0 |
| **Owner / Approver** | Head of IT Operations / COO |
| **Parent policy** | [POL-14](../02-policies/POL-14-business-continuity-policy.md) | **Parent framework** | [BCMF](../01-frameworks/BCMF.md) |
| **RMiT clause(s)** | Section 10.44; 10.45 (Tamper-Proof Backup and Isolated Recovery) |
| **COBIT** | DSS04 | **Practice** | ISO/IEC 27002:2022 control 8.13 |

## 1. Purpose
Specify backup frequency, retention, storage, encryption, immutability, and restorability testing for GIBB data.

## 2. Scope
All data requiring backup — production system data, configuration, application code, infrastructure-as-code, cryptographic keys (where backup-supported).

## 3. Requirements

### 3.1 Backup frequency

| Data class | Frequency |
|---|---|
| Tier 0 transactional databases | Continuous (sync replication) + snapshot every 15 min |
| Tier 1 transactional databases | Snapshot every 30 min; daily full backup |
| Tier 2 application data | Hourly snapshot; daily full backup |
| Configuration / infrastructure-as-code | On every change; daily consolidation |
| File storage (collaboration, document repositories) | Daily incremental; weekly full |

### 3.2 Retention

| Data class | Retention |
|---|---|
| Tier 0/1 transactional | 30 days hot; 7 years cold (BNM record-keeping aligned) |
| Tier 2 | 14 days hot; 1 year cold |
| Configuration | 90 days |
| Application code | Permanent (git history retained) |

### 3.3 Storage and encryption

| Ref | Requirement |
|---|---|
| 3.3.1 | Backups shall be stored in geographically separate locations from primary. |
| 3.3.2 | Backups shall be encrypted at rest using approved algorithms per [STD-CR-01](STD-CR-01-cryptographic-standard.md). |
| 3.3.3 | Backup transport encryption — TLS 1.2 minimum. |
| 3.3.4 | Backup media handled per [POL-15](../02-policies/POL-15-physical-and-environmental-security-policy.md) and RMiT Appendix 1. |

### 3.4 Tamper-proof / immutable backups

Per RMiT 10.45.

| Ref | Requirement |
|---|---|
| 3.4.1 | At least one backup copy of Tier 0 and Tier 1 data shall be **immutable** (write-once, retention-locked) for the duration of its retention period. |
| 3.4.2 | Immutability shall be enforced at the storage layer (object-lock, WORM media, or equivalent), not application-layer logic. |
| 3.4.3 | Immutable backups shall be stored in **isolated recovery environment** logically separated from primary production and primary backup, with separate access credentials and network segmentation. |
| 3.4.4 | Access to alter immutable backup configuration shall require dual-control approval and shall itself be logged. |

### 3.5 Restorability testing

| Ref | Requirement |
|---|---|
| 3.5.1 | Each Tier 0/1 backup shall be tested for restorability **monthly** via automated restore-and-validate. |
| 3.5.2 | Tier 2 backups tested **quarterly**. |
| 3.5.3 | Full disaster-recovery restoration test per critical service **annually** (per [STD-BC-01 §3.6](STD-BC-01-recovery-objectives-standard.md)). |
| 3.5.4 | Test failures shall trigger investigation; root cause and remediation tracked. |

### 3.6 Backup integrity

| Ref | Requirement |
|---|---|
| 3.6.1 | Backups shall include integrity check (checksum or hash). |
| 3.6.2 | Periodic integrity verification independent of restore test. |

### 3.7 Recovery of cryptographic keys

| Ref | Requirement |
|---|---|
| 3.7.1 | Cryptographic key backup follows the key-management requirements of [STD-CR-01](STD-CR-01-cryptographic-standard.md) — separated from data backup, dual-control. |

## 4. Exceptions
Per [POL-14](../02-policies/POL-14-business-continuity-policy.md).

## 5. Related documents
[POL-14](../02-policies/POL-14-business-continuity-policy.md); [STD-BC-01](STD-BC-01-recovery-objectives-standard.md); [STD-CR-01](STD-CR-01-cryptographic-standard.md); [POL-15](../02-policies/POL-15-physical-and-environmental-security-policy.md); SOP-BC-02 Backup Operation SOP; SOP-BC-03 Tamper-Proof Backup Verification SOP

## 6. References
BNM RMiT 28 Nov 2025 §10.44; 10.45; Appendix 1; ISO/IEC 27002:2022 control 8.13; ISO/IEC 22301:2019.

## 7. Document control
| Version | Date | Author | Approver | Change |
|---|---|---|---|---|
| 1.0 | [Effective] | Head of IT Ops | COO | Initial |
