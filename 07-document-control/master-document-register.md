# Master Document Register

Single source of truth for every document in the v2 ISMS / IT governance suite. One row per document. Current state only — for change history see [`change-log.md`](change-log.md); for archived prior versions see [`archive/`](archive/).

| | |
|---|---|
| **Owner** | ISMS Manager |
| **Cadence** | Continuous |
| **Implements** | ISO/IEC 27001:2022 Clause 7.5; BNM RMiT 9.2(h) |
| **Last updated** | 2026-05-27 |

---

## Status legend

| Status | Meaning |
|---|---|
| Draft | Being written; not authoritative |
| In Review | Out for 2nd-line / stakeholder review |
| Pending Approval | Review complete; awaiting approver sign-off |
| Approved | Approved but not yet effective |
| **Effective** | Live and authoritative |
| Under Revision | Material update being prepared while current version remains Effective |
| Superseded | Replaced by later version (see archive) |
| Retired | No longer applicable (see archive) |

---

## v2 Architecture (00-architecture)

| ID | Title | Version | Status | Owner | Approver | Effective | Next review |
|---|---|---|---|---|---|---|---|
| ARCH-001 | [GIBB IT Governance Architecture](../00-architecture/architecture.md) | 1.0 | Draft | CRO + CISO | Board Risk Management Committee | [Effective] | Annual |

---

## v2 Layer 2 — Frameworks (01-frameworks)

| ID | Title | Version | Status | Owner | Approver | Effective | Next review |
|---|---|---|---|---|---|---|---|
| TRMF | [Technology Risk Management Framework](../01-frameworks/TRMF.md) | 1.0 | Draft | CRO + Head of TRM | Board RMC | [Effective] | Annual |
| CRMF | [Cyber Risk Management Framework](../01-frameworks/CRMF.md) | 1.0 | Draft | CISO | Board RMC | [Effective] | Annual |
| BCMF | [Business Continuity Management Framework](../01-frameworks/BCMF.md) | 1.0 | Draft | COO | Board RMC | [Effective] | Annual |
| TPRMF | [Third Party Risk Management Framework](../01-frameworks/TPRMF.md) | 1.0 | Draft | Head of Procurement + CRO | Board RMC | [Effective] | Annual |
| CIMF | [Customer Information Management Framework](../01-frameworks/CIMF.md) | 1.0 | Draft | DPO + CCO | Board RMC | [Effective] | Annual |
| NCIIF | [NCII Compliance Framework](../01-frameworks/NCIIF.md) | 1.0 | Draft | CISO + CCO | Board RMC | [Effective] | Annual |
| CloudRMF | [Cloud Risk Management Framework](../01-frameworks/CloudRMF.md) | 1.0 | Draft | Head of Cloud + CISO | Board RMC | [Effective] | Annual |
| DGF | [Data Governance Framework](../01-frameworks/DGF.md) | 1.0 | Draft | CDO | Board RMC | [Effective] | Annual |
| AIGF | [AI Governance Framework](../01-frameworks/AIGF.md) | 1.0 | Draft | CDO + CISO | Board RMC | [Effective] | Annual |

---

## v2 Layer 3 — Policies (02-policies)

| ID | Title | Version | Status | Owner | Approver | Effective | Next review | Parent framework |
|---|---|---|---|---|---|---|---|---|
| POL-01 | [IT Governance Policy](../02-policies/POL-01-it-governance-policy.md) | 1.0 | Draft | CIO + CRO | **Board of Directors** | [Effective] | Annual | TRMF |
| POL-02 | [Technology Risk Management Policy](../02-policies/POL-02-technology-risk-management-policy.md) | 1.0 | Draft | CRO | RMC | [Effective] | Annual | TRMF |
| POL-03 | [Technology Risk Appetite Statement](../02-policies/POL-03-technology-risk-appetite-statement.md) | 1.0 | Draft | CRO | **Board of Directors** | [Effective] | Annual | TRMF |
| **POL-04** | [Information Security Policy](../02-policies/POL-04-information-security-policy.md) | 1.0 (re-anchored from v1) | Draft | CISO | **Board of Directors** | [Effective] | Annual | **CRMF** |
| **POL-05** | [Acceptable Use Policy](../02-policies/POL-05-acceptable-use-policy.md) | 1.0 (re-anchored from v1) | Draft | CISO | RMC | [Effective] | Annual | **CRMF** |
| **POL-06** | [Access Control Policy](../02-policies/POL-06-access-control-policy.md) | 1.0 (re-anchored from v1) | Draft | CISO | RMC | [Effective] | Annual | **CRMF** |
| POL-07 | [Change Management Policy](../02-policies/POL-07-change-management-policy.md) | 1.0 | Draft | CIO | RMC | [Effective] | Annual | TRMF |
| POL-08 | [Capacity and Performance Management Policy](../02-policies/POL-08-capacity-and-performance-management-policy.md) | 1.0 | Draft | CIO | RMC | [Effective] | Annual | TRMF / BCMF |
| POL-09 | [IT Asset Management Policy](../02-policies/POL-09-it-asset-management-policy.md) | 1.0 | Draft | CIO + CDO | RMC | [Effective] | Annual | TRMF / DGF |
| **POL-10** | [IT Vendor Management Policy](../02-policies/POL-10-it-vendor-management-policy.md) | 1.0 | Draft | Head of Procurement + CRO | RMC | [Effective] | Annual | **TPRMF** |
| **POL-11** | [Data Classification and Handling Policy](../02-policies/POL-11-data-classification-policy.md) | 1.0 | Draft | CDO + DPO | RMC | [Effective] | Annual | **DGF / CIMF** |
| **POL-12** | [Cryptography Policy](../02-policies/POL-12-cryptography-policy.md) | 1.0 (re-anchored from v1) | Draft | CISO | RMC | [Effective] | Annual | **CRMF** |
| **POL-13** | [Incident Management Policy](../02-policies/POL-13-incident-management-policy.md) | 1.0 (re-anchored from v1) | Draft | CISO | RMC | [Effective] | Annual | **CRMF** |
| POL-15 | [Physical and Environmental Security Policy](../02-policies/POL-15-physical-and-environmental-security-policy.md) | 1.0 | Draft | Head of Facilities + CISO | RMC | [Effective] | Annual | TRMF / BCMF |
| POL-16 | [Operations Security Policy](../02-policies/POL-16-operations-security-policy.md) | 1.0 | Draft | CIO + CISO | RMC | [Effective] | Annual | TRMF / CRMF |
| POL-17 | [Secure Development Policy](../02-policies/POL-17-secure-development-policy.md) | 1.0 | Draft | Head of Engineering + CISO | RMC | [Effective] | Annual | TRMF / CRMF |
| **POL-18** | [Vulnerability and Patch Management Policy](../02-policies/POL-18-vulnerability-management-policy.md) | 1.0 (re-anchored from v1) | Draft | CISO | RMC | [Effective] | Annual | **CRMF** |
| **POL-19** | [Supplier and Third-Party Security Policy](../02-policies/POL-19-supplier-security-policy.md) | 1.0 (re-anchored from v1) | Draft | CISO + Procurement | RMC | [Effective] | Annual | **TPRMF + CRMF** |
| **POL-20** | [Cloud Acceptable Use Policy](../02-policies/POL-20-cloud-acceptable-use-policy.md) | 1.0 | Draft | Head of Cloud + CISO | RMC | [Effective] | Annual | **CloudRMF** |
| **POL-21** | [AI Acceptable Use Policy](../02-policies/POL-21-ai-acceptable-use-policy.md) | 1.0 | Draft | CDO + CISO | RMC | [Effective] | Annual | **AIGF** |
| POL-22 | [IT Compliance Policy](../02-policies/POL-22-it-compliance-policy.md) | 1.0 | Draft | CCO | RMC | [Effective] | Annual | TRMF |
| **POL-23** | [NCII Operational Policy](../02-policies/POL-23-ncii-operational-policy.md) | 1.0 | Draft | CISO + CCO | RMC | [Effective] | Annual | **NCIIF** |
| **POL-CI-01** | [Customer Data Protection Policy](../02-policies/POL-CI-01-customer-data-protection-policy.md) | 1.0 | Draft | DPO + CCO | RMC | [Effective] | Annual | **CIMF** |
| **POL-HR-01** | [HR Security Policy](../02-policies/POL-HR-01-hr-security-policy.md) | 1.0 (re-anchored from v1 POL-06) | Draft | CHRO + CISO | RMC | [Effective] | Annual | TRMF / CRMF (joint) |

---

## v2 Layer 4 — Standards (03-standards)

| ID | Title | Version | Status | Owner | Approver | Effective | Next review | Parent policy |
|---|---|---|---|---|---|---|---|---|
| STD-CM-01 | [Change Management Standard](../03-standards/STD-CM-01-change-management-standard.md) | 1.0 | Draft | CIO | CIO | [Effective] | Annual | POL-07 |
| STD-AM-01 | [IT Asset Management Standard](../03-standards/STD-AM-01-it-asset-management-standard.md) | 1.0 | Draft | CIO + CDO | CIO | [Effective] | Annual | POL-09 |
| **STD-AC-01** | [Password & Authentication Standard](../03-standards/STD-AC-01-password-and-authentication-standard.md) | 1.0 (re-anchored from v1) | Draft | CISO | CISO | [Effective] | Annual | **POL-06** |
| **STD-IR-01** | [Incident Classification & Severity Standard](../03-standards/STD-IR-01-incident-classification-and-severity-standard.md) | 1.0 (re-anchored from v1) | Draft | CISO | CISO | [Effective] | Annual | **POL-13** |
| **STD-CR-01** | [Cryptographic Standard](../03-standards/STD-CR-01-cryptographic-standard.md) | 1.0 | Draft | CISO | CISO | [Effective] | Annual | **POL-12** |
| **STD-CR-02** | [Logging Standard](../03-standards/STD-CR-02-logging-standard.md) | 1.0 | Draft | CISO + Head of SOC | CISO | [Effective] | Annual | **POL-16 (CRMF + TRMF)** |
| **STD-CR-03** | [Vulnerability Triage Standard](../03-standards/STD-CR-03-vulnerability-triage-standard.md) | 1.0 | Draft | CISO | CISO | [Effective] | Annual | **POL-18** |
| **STD-BC-01** | [Recovery Objectives Standard](../03-standards/STD-BC-01-recovery-objectives-standard.md) | 1.0 | Draft | COO + CIO | COO | [Effective] | Annual | **POL-14** |
| **STD-BC-02** | [Backup and Restoration Standard](../03-standards/STD-BC-02-backup-and-restoration-standard.md) | 1.0 | Draft | Head of IT Ops | COO | [Effective] | Annual | **POL-14** |
| **STD-TP-01** | [TPSP Due Diligence Standard](../03-standards/STD-TP-01-tpsp-due-diligence-standard.md) | 1.0 | Draft | CRO + CISO | CRO | [Effective] | Annual | **POL-10, POL-19** |
| **STD-CI-01** | [Customer Data Classification Standard](../03-standards/STD-CI-01-customer-data-classification-standard.md) | 1.0 | Draft | DPO | DPO | [Effective] | Annual | **POL-CI-01, POL-11** |
| **STD-NC-01** | [NACSA Notification Standard](../03-standards/STD-NC-01-nacsa-notification-standard.md) | 1.0 | Draft | CCO + CISO | CCO | [Effective] | Annual | **POL-23** |
| **STD-CL-01** | [Cloud Security Standard](../03-standards/STD-CL-01-cloud-security-standard.md) | 1.0 | Draft | Head of Cloud + CISO | CISO | [Effective] | Annual | **POL-20** |
| **STD-DG-01** | [Data Quality Standard](../03-standards/STD-DG-01-data-quality-standard.md) | 1.0 | Draft | CDO | CDO | [Effective] | Annual | **POL-11** |
| **STD-AI-01** | [AI Use Case Risk Classification Standard](../03-standards/STD-AI-01-ai-use-case-risk-classification-standard.md) | 1.0 | Draft | AI Governance Committee | AIGC | [Effective] | Annual + on AI PD | **POL-21** |
| **STD-CL-02** | [Cloud Landing Zone Standard](../03-standards/STD-CL-02-cloud-landing-zone-standard.md) | 1.0 | Draft | Head of Cloud | CISO | [Effective] | Annual | POL-20 |
| **STD-CL-03** | [Cloud Data Residency Standard](../03-standards/STD-CL-03-cloud-data-residency-standard.md) | 1.0 | Draft | CISO + DPO | CISO | [Effective] | Annual | POL-20, POL-CI-01 |
| **STD-TP-02** | [Outsourcing Contractual Security Standard](../03-standards/STD-TP-02-outsourcing-contractual-security-standard.md) | 1.0 | Draft | Legal + CISO | Legal | [Effective] | Annual | POL-10, POL-19 |
| **STD-TP-03** | [TPSP Continuous Monitoring Standard](../03-standards/STD-TP-03-tpsp-continuous-monitoring-standard.md) | 1.0 | Draft | CISO + Head of Procurement | CISO | [Effective] | Annual | POL-10 |
| **STD-CI-02** | [Customer Data Retention Standard](../03-standards/STD-CI-02-customer-data-retention-standard.md) | 1.0 | Draft | DPO + Legal | DPO | [Effective] | Annual | POL-CI-01 |
| **STD-CI-03** | [Customer Authentication Standard](../03-standards/STD-CI-03-customer-authentication-standard.md) | 1.0 | Draft | CISO + DPO | CISO | [Effective] | Annual | POL-CI-01, POL-06 |
| **STD-NC-02** | [NCII Audit Standard](../03-standards/STD-NC-02-ncii-audit-standard.md) | 1.0 | Draft | Internal Audit + CISO | Head of Internal Audit | [Effective] | Annual | POL-23 |
| **STD-DG-02** | [Data Retention Standard](../03-standards/STD-DG-02-data-retention-standard.md) | 1.0 | Draft | CDO + Legal | CDO | [Effective] | Annual | POL-11 |
| **STD-DG-03** | [Metadata Standard](../03-standards/STD-DG-03-metadata-standard.md) | 1.0 | Draft | CDO | CDO | [Effective] | Annual | POL-11 |
| **STD-AI-02** | [AI Model Validation Standard](../03-standards/STD-AI-02-ai-model-validation-standard.md) | 1.0 | Draft | Model Risk function | CRO | [Effective] | Annual + on AI PD | POL-21 |
| **STD-AI-03** | [Generative AI Security Standard](../03-standards/STD-AI-03-genai-security-standard.md) | 1.0 | Draft | CISO + Data Science | CISO | [Effective] | Annual + on AI PD | POL-21 |
| **STD-AI-04** | [AI Training Data Standard](../03-standards/STD-AI-04-ai-training-data-standard.md) | 1.0 | Draft | CDO + DPO | CDO | [Effective] | Annual + on AI PD | POL-21, POL-11 |

---

## v2 Layer 5 — Procedures (04-procedures)

| ID | Title | Version | Status | Owner | Approver | Effective | Next review | Parent standard |
|---|---|---|---|---|---|---|---|---|
| SOP-CM-01 | [Change Authorisation SOP](../04-procedures/SOP-CM-01-change-authorisation-sop.md) | 1.0 | Draft | Head of IT Operations | Head of IT Operations | [Effective] | Annual | STD-CM-01 |
| **SOP-AC-01** | [Joiner / Mover / Leaver SOP](../04-procedures/SOP-AC-01-joiner-mover-leaver-sop.md) | 1.0 (re-anchored from v1) | Draft | Head of IAM | Head of IAM | [Effective] | Annual | **STD-AC-01** |
| **SOP-IR-01** | [Incident Triage SOP](../04-procedures/SOP-IR-01-incident-triage-sop.md) | 1.0 (re-anchored from v1) | Draft | Head of SOC | Head of SOC | [Effective] | Annual | **STD-IR-01** |
| **SOP-CM-02** | [Emergency Change SOP](../04-procedures/SOP-CM-02-emergency-change-sop.md) | 1.0 | Draft | Head of IT Ops | Head of IT Ops | [Effective] | Annual | STD-CM-01 |
| **SOP-CR-01** | [Cyber Drill Exercise SOP](../04-procedures/SOP-CR-01-cyber-drill-exercise-sop.md) | 1.0 | Draft | CISO + Head of SOC | CISO | [Effective] | Annual | STD-IR-01 (RMiT 11.16) |
| **SOP-CI-02** | [Customer Data Breach Notification SOP](../04-procedures/SOP-CI-02-customer-data-breach-notification-sop.md) | 1.0 | Draft | DPO + CCO + CISO | DPO | [Effective] | Annual | POL-CI-01 + POL-13 |
| **SOP-NC-01** | [NACSA Incident Notification SOP](../04-procedures/SOP-NC-01-nacsa-incident-notification-sop.md) | 1.0 | Draft | CCO + CISO | CCO | [Effective] | Annual + on NACSA Code update | STD-NC-01 |
| **SOP-BC-01** | [BIA Methodology SOP](../04-procedures/SOP-BC-01-bia-methodology-sop.md) | 1.0 | Draft | Head of BC | Head of BC | [Effective] | Annual | STD-BC-01 |
| **SOP-TP-01** | [TPSP Onboarding SOP](../04-procedures/SOP-TP-01-tpsp-onboarding-sop.md) | 1.0 | Draft | Head of Procurement | Head of Procurement + CRO | [Effective] | Annual | STD-TP-01 |
| **SOP-CL-01** | [Cloud Service Onboarding SOP](../04-procedures/SOP-CL-01-cloud-service-onboarding-sop.md) | 1.0 | Draft | Head of Cloud + CISO | CISO | [Effective] | Annual | STD-CL-01 |
| **SOP-AI-01** | [AI Use Case Onboarding SOP](../04-procedures/SOP-AI-01-ai-use-case-onboarding-sop.md) | 1.0 | Draft | AI Governance | AIGC | [Effective] | Annual + on AI PD | STD-AI-01 |
| **SOP-CR-02** | [SOC Detection Tuning SOP](../04-procedures/SOP-CR-02-soc-detection-tuning-sop.md) | 1.0 | Draft | Head of SOC | Head of SOC | [Effective] | Annual | STD-CR-02 |
| **SOP-CR-03** | [Forensic Evidence Handling SOP](../04-procedures/SOP-CR-03-forensic-evidence-handling-sop.md) | 1.0 | Draft | Head of SOC + CISO | CISO | [Effective] | Annual | POL-13 |
| **SOP-BC-02** | [Backup Operation SOP](../04-procedures/SOP-BC-02-backup-operation-sop.md) | 1.0 | Draft | Head of IT Ops | Head of IT Ops | [Effective] | Annual | STD-BC-02 |
| **SOP-BC-03** | [Tamper-Proof Backup Verification SOP](../04-procedures/SOP-BC-03-tamper-proof-backup-verification-sop.md) | 1.0 | Draft | Head of IT Ops + CISO | Head of IT Ops | [Effective] | Monthly cycle | STD-BC-02 §3.4 |
| **SOP-TP-02** | [TPSP Periodic Reassessment SOP](../04-procedures/SOP-TP-02-tpsp-periodic-reassessment-sop.md) | 1.0 | Draft | TPRM team | CRO | [Effective] | Annual | STD-TP-01 §3.4 |
| **SOP-TP-03** | [TPSP Exit SOP](../04-procedures/SOP-TP-03-tpsp-exit-sop.md) | 1.0 | Draft | Head of Procurement + CRO | Head of Procurement | [Effective] | Annual | STD-TP-02 |
| **SOP-CI-01** | [Data Subject Access Request SOP](../04-procedures/SOP-CI-01-dsar-sop.md) | 1.0 | Draft | DPO | DPO | [Effective] | Annual | POL-CI-01 §4.4 |
| **SOP-CI-03** | [Customer Consent Capture SOP](../04-procedures/SOP-CI-03-customer-consent-capture-sop.md) | 1.0 | Draft | DPO | DPO | [Effective] | Annual | POL-CI-01 §4.1 |
| **SOP-NC-02** | [NACSA Examination Response SOP](../04-procedures/SOP-NC-02-nacsa-examination-response-sop.md) | 1.0 | Draft | CCO + CISO | CCO | [Effective] | Annual | STD-NC-02 |
| **SOP-CL-02** | [CSPM Operations SOP](../04-procedures/SOP-CL-02-cspm-operations-sop.md) | 1.0 | Draft | Head of Cloud + Head of SOC | Head of Cloud | [Effective] | Annual | STD-CL-01 §3.5 |
| **SOP-CL-03** | [Cloud Exit Validation SOP](../04-procedures/SOP-CL-03-cloud-exit-validation-sop.md) | 1.0 | Draft | Head of Cloud | Head of Cloud + Procurement | [Effective] | Annual | POL-20 §4.7 |
| **SOP-DG-01** | [Data Asset Onboarding SOP](../04-procedures/SOP-DG-01-data-asset-onboarding-sop.md) | 1.0 | Draft | Data Governance team | CDO | [Effective] | Annual | POL-11 |
| **SOP-DG-02** | [Data Quality Triage SOP](../04-procedures/SOP-DG-02-data-quality-triage-sop.md) | 1.0 | Draft | Data Governance team | CDO | [Effective] | Annual | STD-DG-01 |
| **SOP-DG-03** | [Data Destruction SOP](../04-procedures/SOP-DG-03-data-destruction-sop.md) | 1.0 | Draft | Data Governance + IT Ops | CDO + Head of IT Ops | [Effective] | Annual | STD-DG-02, STD-CI-02 |
| **SOP-AI-02** | [AI Model Validation SOP](../04-procedures/SOP-AI-02-model-validation-sop.md) | 1.0 | Draft | Model Risk function | CRO | [Effective] | Annual + on AI PD | STD-AI-02 |
| **SOP-AI-03** | [AI Vendor Assessment SOP](../04-procedures/SOP-AI-03-ai-vendor-assessment-sop.md) | 1.0 | Draft | AI Governance + TPRM | AIGC | [Effective] | Annual + on AI PD | POL-21 §4.8 |

---

## v2 Plans (05-plans)

| ID | Title | Version | Status | Owner | Approver | Effective | Next review | Parent framework |
|---|---|---|---|---|---|---|---|---|
| **PLN-01** | [Incident Response Plan](../05-plans/PLN-01-incident-response-plan.md) | 1.0 (re-anchored from v1) | Draft | CISO | RMC | [Effective] | Annual + post-event | **CRMF** |
| **PLN-02** | [Business Continuity Plan](../05-plans/PLN-02-business-continuity-plan.md) | 1.0 | Draft | COO | RMC | [Effective] | Annual + post-event | **BCMF** |
| **PLN-03** | [Disaster Recovery Plan (master)](../05-plans/PLN-03-disaster-recovery-plan.md) | 1.0 | Draft | Head of IT Ops | COO + CIO | [Effective] | Annual + post-event | **BCMF + TRMF** |
| **PLN-04** | [Crisis Communications Plan](../05-plans/PLN-04-crisis-communications-plan.md) | 1.0 | Draft | Head of Corp Comms | RMC | [Effective] | Annual | **CRMF + BCMF** |
| **PLN-05** | [Cyber Drill Exercise Plan (RMiT 11.16)](../05-plans/PLN-05-cyber-drill-exercise-plan.md) | 1.0 | Draft | CISO | RMC | [Effective] | Annual | **CRMF** |
| **PLN-06** | [Pandemic / Workforce Disruption Plan](../05-plans/PLN-06-pandemic-workforce-disruption-plan.md) | 1.0 | Draft | COO + CHRO | RMC | [Effective] | Annual | **BCMF** |
| **PLN-03-CB** | [Core Banking DRP](../05-plans/PLN-03-CB-core-banking-drp.md) | 1.0 | Draft | Head of IT Ops + Head of Core Banking | COO + CIO | [Effective] | Annual | BCMF / TRMF (per-service DRP) |
| **PLN-03-IB** | [Internet Banking DRP](../05-plans/PLN-03-IB-internet-banking-drp.md) | 1.0 | Draft | Head of IT Ops + Head of Digital Channels | COO + CIO | [Effective] | Annual | BCMF / TRMF (per-service DRP) |
| **PLN-03-PMT** | [Payment Systems DRP](../05-plans/PLN-03-PMT-payment-systems-drp.md) | 1.0 | Draft | Head of IT Ops + Head of Treasury Ops | COO + CIO | [Effective] | Annual | BCMF / TRMF (per-service DRP) |

---

## v2 Layer 6 — Registers (06-registers)

| ID | Title | Owner | Cadence | Parent framework |
|---|---|---|---|---|
| REG-TR | [Technology Risk Register](../06-registers/REG-TR-technology-risk-register.md) | CRO (Head of TRM operates) | Continuous | TRMF |
| **REG-INC** | [Incident Register](../06-registers/REG-INC-incident-register.md) (re-anchored from v1) | CISO | Continuous | **CRMF** |
| **REG-PAR** | [Privileged Access Review Register](../06-registers/REG-PAR-privileged-access-review-register.md) (re-anchored from v1) | Head of IAM | Quarterly | **CRMF** |
| **REG-SOA** | [Statement of Applicability](../06-registers/REG-SOA-statement-of-applicability.md) (re-anchored from v1) | CISO | Annual + on change | **TRMF + CRMF** (cross-framework; ISO 27001 mandated) |
| **REG-BIA** | [Business Impact Analysis Register](../06-registers/REG-BIA-business-impact-analysis-register.md) | Head of BC (under COO) | Annual per service | **BCMF** |
| **REG-TPS** | [Third-Party Service Provider Register](../06-registers/REG-TPS-third-party-service-provider-register.md) | Head of Procurement + CRO | Continuous | **TPRMF** |
| **REG-ROPA** | [Records of Processing Activity](../06-registers/REG-ROPA-records-of-processing-activity.md) | DPO | Continuous | **CIMF** |
| **REG-NCN** | [NACSA Notification Register](../06-registers/REG-NCN-nacsa-notification-register.md) | CCO + CISO | Per event | **NCIIF** |
| **REG-CL** | [Cloud Service Register](../06-registers/REG-CL-cloud-service-register.md) | Head of Cloud + CISO | Continuous | **CloudRMF** |
| **REG-DA** | [Data Asset Register](../06-registers/REG-DA-data-asset-register.md) | CDO | Continuous | **DGF** |
| **REG-AIU** | [AI Use Case Register](../06-registers/REG-AIU-ai-use-case-register.md) | AI Governance Committee (CDO) | Continuous | **AIGF** |
| **REG-EXC** | [Exception Register](../06-registers/REG-EXC-exception-register.md) | ISMS Manager (under CISO) | Continuous | Cross-framework (TRMF Section 12) |
| **REG-VUL** | [Vulnerability Register](../06-registers/REG-VUL-vulnerability-register.md) | CISO | Continuous | **CRMF** |
| **REG-CDB** | [Customer Data Breach Register](../06-registers/REG-CDB-customer-data-breach-register.md) | DPO + CCO | Per event | **CIMF + CRMF** |
| **REG-DRL** | [Cyber Drill Register](../06-registers/REG-DRL-cyber-drill-register.md) | CISO | Per exercise | **CRMF** (RMiT 11.16 evidence) |
| **REG-OUT** | [Material Outsourcing Register](../06-registers/REG-OUT-material-outsourcing-register.md) | Head of Procurement + CCO | Continuous | **TPRMF** |
| **REG-DSR** | [Data Subject Request Register](../06-registers/REG-DSR-data-subject-request-register.md) | DPO | Continuous | **CIMF** |
| **REG-AIM** | [AI Model Inventory](../06-registers/REG-AIM-ai-model-inventory.md) | Data Science (CDO) | Continuous | **AIGF** |
| **REG-CAP** | [Corrective Action Register](../06-registers/REG-CAP-corrective-action-register.md) | CRO | Continuous | Cross-framework |
| **REG-BCT** | [BC Test Outcomes Register](../06-registers/REG-BCT-bc-test-outcomes-register.md) | Head of BC (COO) | Per test | **BCMF** |
| **REG-DRR** | [DR Test Register](../06-registers/REG-DRR-dr-test-register.md) | Head of IT Ops | Per test | **BCMF + TRMF** |
| **REG-NC** | [NACSA Directive Tracker](../06-registers/REG-NC-nacsa-directive-tracker.md) | CCO + CISO | Continuous | NCIIF |
| **REG-NCA** | [NCII Audit Findings Register](../06-registers/REG-NCA-ncii-audit-findings-register.md) | Internal Audit + CISO | Per audit | NCIIF |
| **REG-CEX** | [Cloud Exit Plan Register](../06-registers/REG-CEX-cloud-exit-plan-register.md) | Head of Cloud + Procurement | Annual review | CloudRMF / TPRMF |
| **REG-CRA** | [Cloud Risk Assessment Register](../06-registers/REG-CRA-cloud-risk-assessment-register.md) | Head of Cloud + CISO | Per assessment | CloudRMF |
| **REG-AIV** | [AI Vendor Register](../06-registers/REG-AIV-ai-vendor-register.md) | AI Governance + TPRM | Continuous | AIGF / TPRMF |
| **REG-AIB** | [AI Bias and Fairness Register](../06-registers/REG-AIB-ai-bias-and-fairness-register.md) | AI Governance | Continuous | AIGF |
| **REG-DQ** | [Data Quality Register](../06-registers/REG-DQ-data-quality-register.md) | Data Governance team | Continuous | DGF |
| **REG-DL** | [Data Lineage Register](../06-registers/REG-DL-data-lineage-register.md) | Data Governance team | Continuous (tooling-generated) | DGF |
| **REG-MD** | [Master Data Register](../06-registers/REG-MD-master-data-register.md) | CDO + CIO | Continuous | DGF |
| **REG-TPI** | [TPSP Incident Register](../06-registers/REG-TPI-tpsp-incident-register.md) | CISO + CRO | Per incident | TPRMF / CRMF |
| **REG-DIS** | [Customer Disclosure Register](../06-registers/REG-DIS-customer-disclosure-register.md) | DPO + CCO | Per disclosure | CIMF |

---

## v2 Templates (_templates)

| ID | Title | Status |
|---|---|---|
| TPL-FRA | [Framework template](../_templates/framework-template.md) | Effective |
| TPL-POL | [Policy template](../_templates/policy-template.md) | Effective |
| TPL-STD | [Standard template](../_templates/standard-template.md) | Effective |
| TPL-SOP | [Procedure template](../_templates/procedure-template.md) | Effective |
| TPL-PLN | [Plan template](../_templates/plan-template.md) | Effective |
| TPL-REG | [Register template](../_templates/register-template.md) | Effective |

---

## v1 snapshot (locked)

v1 documents are not actively maintained. They are accessible at [`../v1/`](../v1/) for reference and (in subsequent v2 sessions) re-anchoring of InfoSec-domain content under CRMF. The v1.0 git tag preserves the v1 build at its final state.

---

## Pending in Phase 1 (build sessions following Session 4)

The following documents are scoped for future sessions:

**CRMF cascade** — Layer 3 policies (POL-04 Information Security, POL-05 Acceptable Use, POL-06 Access Control, POL-12 Cryptography, POL-13 Incident Management, POL-18 Vulnerability Management, POL-19 Supplier Security) re-anchored from v1; STD password-and-authentication and incident-classification-and-severity re-anchored from v1; SOPs JML and Incident Triage re-anchored from v1; PLN-01 IRP re-anchored from v1; REG-INC, REG-PAR re-anchored from v1.

**Other framework cascades** — Layer 3-6 documents per CRMF, BCMF, TPRMF, CIMF, NCIIF, CloudRMF, DGF, AIGF.

**Other v2 Layer 2 cascade exemplars** — STD-CM-02, SOP-CM-02 (Emergency Change), Capacity Standard, etc.

---

## Maintenance

The ISMS Manager reviews this register **monthly** to identify documents approaching their next-review date (60-day lookahead). The CISO reviews **quarterly** as part of the ISMS Management Review (ISO/IEC 27001:2022 Clause 9.3).

A document past its next-review date is a **control deficiency** and reported through the same channel as a control failure — not as an administrative oversight.
