# Statement of Applicability (SoA)

| | |
|---|---|
| **Document ID** | REG-SOA |
| **Layer** | Register |
| **Owner** | CISO |
| **Approver** | Risk Management Committee |
| **Classification** | Internal |
| **Version** | 1.0 |
| **Effective date** | 2026-02-01 |
| **Next review** | 2027-02-01 (annual or on material change) |
| **Implements** | ISO/IEC 27001:2022 Clause 6.1.3 d — Statement of Applicability |
| **Parent framework(s)** | [CRMF](../01-frameworks/CRMF.md) (the SoA is the canonical ISO 27001 Annex A control map for the ISMS) |
| **COBIT objective(s)** | APO13 Managed Security; DSS05 Managed Security Services |

---

## Purpose

The Statement of Applicability is the **mandatory ISO/IEC 27001:2022 record** of which controls from Annex A (the 93 controls of ISO/IEC 27002:2022) are applicable to GIBB's ISMS, why each is included or excluded, and how it is implemented. It is one of the first documents reviewed by external auditors and by regulators.

Annex A organises controls into four themes: **Organisational (37)**, **People (8)**, **Physical (14)**, **Technological (34)** — total **93**.

---

## How to read this register

| Column | Meaning |
|---|---|
| **Ctl** | ISO/IEC 27002:2022 control number |
| **Title** | Control title |
| **App.** | Applicable? — Yes / No |
| **Justification** | If excluded — why; if included — risk basis |
| **Implementation** | Which policy / standard / procedure / plan / register implements it |
| **Owner** | Accountable role |

> The table below is the **complete SoA** — all 93 controls — populated to a level suitable as a working template. In a real ISMS this register is the **most-edited document**, updated whenever a control's implementation evidence changes.

---

## Theme 1 — Organisational controls (5.1 to 5.37)

| Ctl | Title | App. | Justification | Implementation | Owner |
|---|---|---|---|---|---|
| 5.1 | Policies for information security | Y | Mandatory. | [POL-04](../02-policies/POL-04-information-security-policy.md) and supporting suite | CISO |
| 5.2 | Information security roles and responsibilities | Y | Mandatory. | [POL-04 Section 7](../02-policies/POL-04-information-security-policy.md); all supporting policies | CISO |
| 5.3 | Segregation of duties | Y | Material risk in banking. | [POL-06 Section 4.2.3](../02-policies/POL-06-access-control-policy.md) | CISO |
| 5.4 | Management responsibilities | Y | Mandatory. | [POL-04 Section 7](../02-policies/POL-04-information-security-policy.md) | CISO |
| 5.5 | Contact with authorities | Y | Required for incident escalation. | [POL-13 Section 4.4](../02-policies/POL-13-incident-management-policy.md); [PLN-01](../05-plans/PLN-01-incident-response-plan.md) | CCO + CISO |
| 5.6 | Contact with special interest groups | Y | Threat intel and sector CERT participation. | CISO operational practice | CISO |
| 5.7 | Threat intelligence | Y | Required for proactive defence. | CISO operational practice; SOC tooling | Head of SOC |
| 5.8 | Information security in project management | Y | Required for change discipline. | [POL-17 Section 3.1](../02-policies/POL-17-secure-development-policy.md); project management standards | Head of Engineering |
| 5.9 | Inventory of information and other associated assets | Y | Foundation of all controls. | [POL-09 Section 3.1](../02-policies/POL-09-it-asset-management-policy.md) | Head of IT Ops |
| 5.10 | Acceptable use | Y | Required. | [POL-05](../02-policies/POL-05-acceptable-use-policy.md) | CISO |
| 5.11 | Return of assets | Y | Required. | [POL-09 Section 3.5](../02-policies/POL-09-it-asset-management-policy.md); [SOP-AC-01 Section 5.3](../04-procedures/SOP-AC-01-joiner-mover-leaver-sop.md) | Head of IT Ops |
| 5.12 | Classification of information | Y | Required. | [POL-11 Section 4.1](../02-policies/POL-11-data-classification-policy.md) | CISO |
| 5.13 | Labelling of information | Y | Required. | [POL-11 Section 4.2](../02-policies/POL-11-data-classification-policy.md) | CISO |
| 5.14 | Information transfer | Y | Required for customer / regulator / partner exchange. | [POL-11](../02-policies/POL-11-data-classification-policy.md); [POL-12](../02-policies/POL-12-cryptography-policy.md); transfer standard | CISO |
| 5.15 | Access control | Y | Mandatory. | [POL-06 Section 4.2](../02-policies/POL-06-access-control-policy.md) | CISO |
| 5.16 | Identity management | Y | Mandatory. | [POL-06 Section 4.1](../02-policies/POL-06-access-control-policy.md); [SOP-AC-01](../04-procedures/SOP-AC-01-joiner-mover-leaver-sop.md) | Head of IAM |
| 5.17 | Authentication information | Y | Mandatory. | [POL-06 Section 4.3](../02-policies/POL-06-access-control-policy.md); [STD-AC-01](../03-standards/STD-AC-01-password-and-authentication-standard.md) | CISO |
| 5.18 | Access rights | Y | Mandatory. | [POL-06 Section 4.4](../02-policies/POL-06-access-control-policy.md); [REG-PAR](REG-PAR-privileged-access-review-register.md) | Head of IAM |
| 5.19 | Information security in supplier relationships | Y | Material outsourcing dependencies. | [POL-19 Section 3.1](../02-policies/POL-19-supplier-security-policy.md) | CISO |
| 5.20 | Addressing information security within supplier agreements | Y | BNM RMiT Section 10.46–10.49. | [POL-19 Section 3.2](../02-policies/POL-19-supplier-security-policy.md) | CISO |
| 5.21 | Managing information security in the ICT supply chain | Y | Material risk. | [POL-19 Section 3.4](../02-policies/POL-19-supplier-security-policy.md) | CISO |
| 5.22 | Monitoring, review and change management of supplier services | Y | Material risk. | [POL-19 Section 3.5](../02-policies/POL-19-supplier-security-policy.md) | CISO |
| 5.23 | Information security for use of cloud services | Y | Multi-cloud operating model. | [POL-19 Section 3.3](../02-policies/POL-19-supplier-security-policy.md); cloud security baseline | CISO |
| 5.24 | Information security incident management planning and preparation | Y | Mandatory. | [POL-13 Section 4.1](../02-policies/POL-13-incident-management-policy.md); [PLN-01](../05-plans/PLN-01-incident-response-plan.md) | CISO |
| 5.25 | Assessment and decision on information security events | Y | Mandatory. | [POL-13 Section 4.2](../02-policies/POL-13-incident-management-policy.md); [STD-IR-01](../03-standards/STD-IR-01-incident-classification-and-severity-standard.md); [SOP-IR-01](../04-procedures/SOP-IR-01-incident-triage-sop.md) | CISO |
| 5.26 | Response to information security incidents | Y | Mandatory. | [POL-13 Section 4.3](../02-policies/POL-13-incident-management-policy.md); [PLN-01](../05-plans/PLN-01-incident-response-plan.md) | CISO |
| 5.27 | Learning from information security incidents | Y | Mandatory. | [POL-13 Section 4.7](../02-policies/POL-13-incident-management-policy.md) | CISO |
| 5.28 | Collection of evidence | Y | Required for regulatory / legal proceedings. | [POL-13 Section 4.5](../02-policies/POL-13-incident-management-policy.md); IRP Appendix B | CISO |
| 5.29 | Information security during disruption | Y | Required for resilience. | [POL-14 Section 3.2](../02-policies/POL-14-business-continuity-policy.md) | COO |
| 5.30 | ICT readiness for business continuity | Y | BNM RMiT Section 10.24–10.28; Section 10.32; Section 10.44–10.45. | [POL-14 Section 3.3](../02-policies/POL-14-business-continuity-policy.md) | COO + Head of IT Ops |
| 5.31 | Legal, statutory, regulatory and contractual requirements | Y | Mandatory. | [POL-22 Section 3.1](../02-policies/POL-22-it-compliance-policy.md) | CCO |
| 5.32 | Intellectual property rights | Y | Required. | [POL-22 Section 3.4](../02-policies/POL-22-it-compliance-policy.md) | CCO |
| 5.33 | Protection of records | Y | Records retention obligations. | [POL-22 Section 3.2](../02-policies/POL-22-it-compliance-policy.md); records retention schedule | CCO |
| 5.34 | Privacy and protection of PII | Y | PDPA 2010. | [POL-22 Section 3.3](../02-policies/POL-22-it-compliance-policy.md); records of processing activity | DPO |
| 5.35 | Independent review of information security | Y | Required by ISO 27001 and BNM RMiT Section 13 (Technology Audits); Section 14 (External Party Assurance); Section 18 (Assessment and Gap Analysis). | [POL-22 Section 3.5](../02-policies/POL-22-it-compliance-policy.md); internal audit plan | Internal Audit |
| 5.36 | Compliance with policies, rules and standards for information security | Y | Required. | [POL-22 Section 3.6](../02-policies/POL-22-it-compliance-policy.md) | CCO + CISO |
| 5.37 | Documented operating procedures | Y | Required. | All Tier 3 SOPs; document control in [06-document-control](../07-document-control/) | Process owners |

## Theme 2 — People controls (6.1 to 6.8)

| Ctl | Title | App. | Justification | Implementation | Owner |
|---|---|---|---|---|---|
| 6.1 | Screening | Y | Required. | [POL-HR-01 Section 3.1](../02-policies/POL-HR-01-hr-security-policy.md) | CHRO |
| 6.2 | Terms and conditions of employment | Y | Required. | [POL-HR-01 Section 3.2](../02-policies/POL-HR-01-hr-security-policy.md) | CHRO |
| 6.3 | Information security awareness, education and training | Y | Required. | [POL-HR-01 Section 3.3](../02-policies/POL-HR-01-hr-security-policy.md) | CHRO + CISO |
| 6.4 | Disciplinary process | Y | Required. | [POL-HR-01 Section 3.4](../02-policies/POL-HR-01-hr-security-policy.md) | CHRO |
| 6.5 | Responsibilities after termination or change of employment | Y | Required. | [POL-HR-01 Section 3.5](../02-policies/POL-HR-01-hr-security-policy.md); [SOP-AC-01 Section 5.3](../04-procedures/SOP-AC-01-joiner-mover-leaver-sop.md) | CHRO + Head of IAM |
| 6.6 | Confidentiality or non-disclosure agreements | Y | Required. | [POL-HR-01 Section 3.2.2](../02-policies/POL-HR-01-hr-security-policy.md) | CHRO + GC |
| 6.7 | Remote working | Y | Hybrid workforce. | [POL-15 Section 3.8](../02-policies/POL-15-physical-and-environmental-security-policy.md); remote work standard | CISO |
| 6.8 | Information security event reporting | Y | Required. | [POL-13 Section 4.2.3](../02-policies/POL-13-incident-management-policy.md); [POL-05 Section 3.7](../02-policies/POL-05-acceptable-use-policy.md) | CISO |

## Theme 3 — Physical controls (7.1 to 7.14)

| Ctl | Title | App. | Justification | Implementation | Owner |
|---|---|---|---|---|---|
| 7.1 | Physical security perimeters | Y | Required. | [POL-15 Section 3.1](../02-policies/POL-15-physical-and-environmental-security-policy.md) | Head of Facilities |
| 7.2 | Physical entry | Y | Required. | [POL-15 Section 3.1](../02-policies/POL-15-physical-and-environmental-security-policy.md) | Head of Facilities |
| 7.3 | Securing offices, rooms and facilities | Y | Required. | [POL-15 Section 3.1](../02-policies/POL-15-physical-and-environmental-security-policy.md) | Head of Facilities |
| 7.4 | Physical security monitoring | Y | Required. | Facilities monitoring standard | Head of Facilities |
| 7.5 | Protecting against physical and environmental threats | Y | Required. | [POL-15 Section 3.3, Section 3.6](../02-policies/POL-15-physical-and-environmental-security-policy.md) | Head of Facilities |
| 7.6 | Working in secure areas | Y | Required. | [POL-15 Section 3.4](../02-policies/POL-15-physical-and-environmental-security-policy.md) | Head of Facilities |
| 7.7 | Clear desk and clear screen | Y | Required. | [POL-15 Section 3.5](../02-policies/POL-15-physical-and-environmental-security-policy.md) | CISO |
| 7.8 | Equipment siting and protection | Y | Required. | [POL-15 Section 3.3](../02-policies/POL-15-physical-and-environmental-security-policy.md) | Head of Facilities + Head of IT Ops |
| 7.9 | Security of assets off-premises | Y | Hybrid workforce; mobile estate. | [POL-15 Section 3.8](../02-policies/POL-15-physical-and-environmental-security-policy.md); mobile device standard | CISO |
| 7.10 | Storage media | Y | Required. | Media handling standard; [POL-15 Section 3.7](../02-policies/POL-15-physical-and-environmental-security-policy.md) | CISO |
| 7.11 | Supporting utilities | Y | Required for data centres (BNM RMiT Section 10.24–10.28). | [POL-15 Section 3.6](../02-policies/POL-15-physical-and-environmental-security-policy.md); BNM RMiT Section 10.25 (DC Redundancy) | Head of Facilities |
| 7.12 | Cabling security | Y | Required. | [POL-15 Section 3.3](../02-policies/POL-15-physical-and-environmental-security-policy.md) | Head of Facilities |
| 7.13 | Equipment maintenance | Y | Required. | IT operations standard | Head of IT Ops |
| 7.14 | Secure disposal or re-use of equipment | Y | Required. | [POL-15 Section 3.7](../02-policies/POL-15-physical-and-environmental-security-policy.md); NIST SP 800-88 baseline | Head of IT Ops |

## Theme 4 — Technological controls (8.1 to 8.34)

| Ctl | Title | App. | Justification | Implementation | Owner |
|---|---|---|---|---|---|
| 8.1 | User endpoint devices | Y | Required. | [POL-05 Section 3.3](../02-policies/POL-05-acceptable-use-policy.md); endpoint standard | CISO |
| 8.2 | Privileged access rights | Y | Mandatory. | [POL-06 Section 4.4](../02-policies/POL-06-access-control-policy.md); [STD-AC-01 Section 3.1](../03-standards/STD-AC-01-password-and-authentication-standard.md) | Head of IAM |
| 8.3 | Information access restriction | Y | Required. | [POL-06](../02-policies/POL-06-access-control-policy.md); [POL-11](../02-policies/POL-11-data-classification-policy.md) | CISO |
| 8.4 | Access to source code | Y | Required for engineering estate. | [POL-06 Section 4.2.4](../02-policies/POL-06-access-control-policy.md); [POL-17 Section 3.8](../02-policies/POL-17-secure-development-policy.md) | Head of Engineering |
| 8.5 | Secure authentication | Y | Mandatory. | [POL-06 Section 4.3](../02-policies/POL-06-access-control-policy.md); [STD-AC-01](../03-standards/STD-AC-01-password-and-authentication-standard.md) | CISO |
| 8.6 | Capacity management | Y | Required for service availability. | [POL-16 Section 3.2](../02-policies/POL-16-operations-security-policy.md) | Head of IT Ops |
| 8.7 | Protection against malware | Y | Required. | [POL-16 Section 3.3](../02-policies/POL-16-operations-security-policy.md) | Head of IT Ops |
| 8.8 | Management of technical vulnerabilities | Y | Required. | [POL-18](../02-policies/POL-18-vulnerability-management-policy.md) | CISO |
| 8.9 | Configuration management | Y | Required. | Configuration management standard | Head of IT Ops |
| 8.10 | Information deletion | Y | Required for data lifecycle. | [POL-11 Section 4.5](../02-policies/POL-11-data-classification-policy.md); records retention schedule | CISO + DPO |
| 8.11 | Data masking | Y | Required for non-production environments. | [POL-17 Section 3.6](../02-policies/POL-17-secure-development-policy.md); data masking standard | Head of Engineering |
| 8.12 | Data leakage prevention | Y | BNM RMiT Section 10.44(d) + Appendix 1 (sensitive media); Section 12 (Digital Services). | [POL-11](../02-policies/POL-11-data-classification-policy.md); DLP standard | CISO |
| 8.13 | Information backup | Y | BNM RMiT Section 10.44 (Backup); Section 10.45 (Tamper-Proof Backup). | [POL-16 Section 3.4](../02-policies/POL-16-operations-security-policy.md) | Head of IT Ops |
| 8.14 | Redundancy of information processing facilities | Y | BNM RMiT Section 10.24–10.28 (DC Resilience); Section 10.32 (HA Requirements). | [POL-14 Section 3.3](../02-policies/POL-14-business-continuity-policy.md) | Head of IT Ops |
| 8.15 | Logging | Y | Required. | [POL-16 Section 3.5](../02-policies/POL-16-operations-security-policy.md); logging standard | Head of SOC |
| 8.16 | Monitoring activities | Y | BNM RMiT Section 11.9 (SOC); Section 11.10 (Threat Intel); Section 11.11 (Anomalous Activity). | [POL-16 Section 3.6](../02-policies/POL-16-operations-security-policy.md) | Head of SOC |
| 8.17 | Clock synchronization | Y | Required for forensics. | [POL-16 Section 3.7](../02-policies/POL-16-operations-security-policy.md) | Head of IT Ops |
| 8.18 | Use of privileged utility programs | Y | Required. | [POL-06 Section 4.4](../02-policies/POL-06-access-control-policy.md); endpoint standard | CISO |
| 8.19 | Installation of software on operational systems | Y | Required. | [POL-05 Section 3.3](../02-policies/POL-05-acceptable-use-policy.md); change management standard | Head of IT Ops |
| 8.20 | Networks security | Y | Required. | BNM RMiT Section 10.36–10.43 (Network Resilience); network security baseline | Head of IT Ops |
| 8.21 | Security of network services | Y | Required. | Network security baseline | Head of IT Ops |
| 8.22 | Segregation of networks | Y | Required. | Network segmentation standard | Head of IT Ops |
| 8.23 | Web filtering | Y | Required. | Endpoint and network standard | CISO |
| 8.24 | Use of cryptography | Y | Required. | [POL-12](../02-policies/POL-12-cryptography-policy.md); cryptographic standard | CISO |
| 8.25 | Secure development life cycle | Y | Required. | [POL-17 Section 3.1](../02-policies/POL-17-secure-development-policy.md) | Head of Engineering |
| 8.26 | Application security requirements | Y | Required. | [POL-17 Section 3.2](../02-policies/POL-17-secure-development-policy.md) | Head of Engineering |
| 8.27 | Secure system architecture and engineering principles | Y | Required. | [POL-17 Section 3.3](../02-policies/POL-17-secure-development-policy.md) | Head of Engineering |
| 8.28 | Secure coding | Y | Required. | [POL-17 Section 3.4](../02-policies/POL-17-secure-development-policy.md); secure coding standard | Head of Engineering |
| 8.29 | Security testing in development and acceptance | Y | Required. | [POL-17 Section 3.5](../02-policies/POL-17-secure-development-policy.md) | Head of Engineering |
| 8.30 | Outsourced development | Y | Material outsourcing. | [POL-17 Section 3.7](../02-policies/POL-17-secure-development-policy.md); [POL-19](../02-policies/POL-19-supplier-security-policy.md) | Head of Engineering + CISO |
| 8.31 | Separation of development, test and production environments | Y | Required. | [POL-17 Section 3.6](../02-policies/POL-17-secure-development-policy.md) | Head of Engineering |
| 8.32 | Change management | Y | Required. | [POL-16 Section 3.1](../02-policies/POL-16-operations-security-policy.md); change management standard | Head of IT Ops |
| 8.33 | Test information | Y | Required. | [POL-17 Section 3.6](../02-policies/POL-17-secure-development-policy.md); data masking standard | Head of Engineering |
| 8.34 | Protection of information systems during audit testing | Y | Required during pen-test and audit windows. | Audit testing protocol; CISO sign-off | CISO + Internal Audit |

---

## Summary

- **Total Annex A controls:** 93
- **Applicable:** 93
- **Excluded:** 0

In this worked example, all 93 controls are applicable. In practice, a bank may exclude a small number (e.g., a control specific to a deployment model not used). Every exclusion **must** be justified and approved; auditors will challenge unjustified exclusions and any exclusion based on convenience rather than absence-of-risk.

## Maintenance

The SoA is reviewed:

- **Annually** as part of the ISMS Management Review (ISO/IEC 27001:2022 Clause 9.3).
- **On material change** — new or removed business activity, new or removed regulatory obligation, material organisational change.
- **On audit finding** — if internal or external audit identifies a control whose implementation or applicability has changed.

Every change to the SoA generates rows in [06-document-control](../07-document-control/) per the standard document-control workflow.

---

## v2 re-anchoring (2026-05-28)

This document was re-anchored as part of the v2 build (Session 5) per [DEC-001](../_context/decisions.md). Substantive content preserved from the v1 snapshot at [`../v1/`](../v1/). Changes applied:

- Document ID updated to v2 numbering convention
- **Parent framework(s)** and **COBIT objective(s)** added to metadata block
- Bank name normalised from "General Bank" to **GIBB** (General Islamic Bank Berhad)
- Internal cross-references migrated from v1 paths to v2 paths
- v1 sister-document references updated to v2 document IDs

Pending formal GIBB approval under v2. The Effective and Next review dates above are inherited from the v1 1.x lifecycle and will be updated when this document is approved under v2 governance.
