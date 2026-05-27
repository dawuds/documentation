# STD-CI-01 — Customer Data Classification Standard

| | |
|---|---|
| **Document ID** | STD-CI-01 | **Version** | 1.0 |
| **Owner / Approver** | DPO / DPO |
| **Parent policy** | [POL-CI-01](../02-policies/POL-CI-01-customer-data-protection-policy.md); [POL-11](../02-policies/POL-11-data-classification-policy.md) | **Parent framework** | [CIMF](../01-frameworks/CIMF.md) |
| **Additional anchors** | BNM MCIPD; PDPA 2010 |

## 1. Purpose
Specify the customer-data-specific classification scheme overlay over the enterprise scheme in [POL-11](../02-policies/POL-11-data-classification-policy.md), and the per-class handling controls required under MCIPD and PDPA.

## 2. Scope
All customer information processed by GIBB.

## 3. Requirements

### 3.1 Customer data classification overlay

| Customer data class | Examples | Enterprise classification |
|---|---|---|
| Customer identifiers (basic) | Name, address, contact | Confidential |
| Customer financial data | Account balances, transactions, financing details | Confidential |
| Customer authentication data | Passwords, PINs, biometric templates, MFA secrets | Highly Restricted |
| Sensitive personal data per PDPA | Health, religious, political, financial-distress info | Highly Restricted |
| Customer behavioural data | Channel usage, transaction patterns | Confidential |
| Shariah-confidential customer data | Customer-specific Shariah deliberation, fatwa requests | Shariah-Confidential |

### 3.2 Handling requirements per class

(In addition to enterprise handling per [POL-11](../02-policies/POL-11-data-classification-policy.md).)

| Class | Encryption at rest | Encryption in transit | Access control | Audit logging |
|---|---|---|---|---|
| Customer identifiers | Required | TLS 1.2+ | RBAC + business-need | Per [STD-CR-02](STD-CR-02-logging-standard.md) |
| Customer financial | Required | TLS 1.2+ | RBAC + segregation of duties | Full access logging |
| Customer authentication | Required (hashed for passwords) | TLS 1.2+ | Tier-0 access only | Full access logging + monitoring |
| Sensitive personal | Required | TLS 1.2+ | Need-to-know + explicit consent record | Full access logging |
| Shariah-confidential | Required | TLS 1.2+ | Shariah Committee + named officers | Full access logging + Shariah Committee notification |

### 3.3 Aggregation rule

Aggregated customer data inherits the highest class of components. E.g., a report containing name + authentication metadata → Highly Restricted.

### 3.4 Tokenisation and masking

| Ref | Requirement |
|---|---|
| 3.4.1 | Customer identifiers in non-production environments shall be masked or tokenised per [POL-17 §4.7](../02-policies/POL-17-secure-development-policy.md). |
| 3.4.2 | Customer financial data in analytics environments shall be de-identified where the analytical purpose does not require identification. |

### 3.5 Cross-border transfer

| Ref | Requirement |
|---|---|
| 3.5.1 | Transfer of any customer data class outside Malaysia requires PDPA Section 129 basis recorded in [REG-ROPA](../06-registers/REG-ROPA-records-of-processing-activity.md). |

## 4. Exceptions
Per [POL-CI-01](../02-policies/POL-CI-01-customer-data-protection-policy.md).

## 5. Related documents
[POL-CI-01](../02-policies/POL-CI-01-customer-data-protection-policy.md); [POL-11](../02-policies/POL-11-data-classification-policy.md); [STD-CR-01](STD-CR-01-cryptographic-standard.md); [REG-ROPA](../06-registers/REG-ROPA-records-of-processing-activity.md); [CIMF](../01-frameworks/CIMF.md)

## 6. References
BNM MCIPD; PDPA 2010; BNM RMiT §12.

## 7. Document control
| Version | Date | Author | Approver | Change |
|---|---|---|---|---|
| 1.0 | [Effective] | DPO | DPO | Initial |
