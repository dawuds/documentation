# STD-TP-03 — TPSP Continuous Monitoring Standard

| | |
|---|---|
| **Document ID** | STD-TP-03 | **Version** | 1.0 |
| **Owner / Approver** | CISO + Head of Procurement / CISO |
| **Parent policy** | [POL-10](../02-policies/POL-10-it-vendor-management-policy.md) | **Parent framework** | [TPRMF](../01-frameworks/TPRMF.md) |
| **RMiT clause(s)** | Section 10.49 (Continuous TPSP Cybersecurity Monitoring) |

## 1. Purpose
Specify how GIBB continuously monitors TPSP security posture per RMiT 10.49.

## 2. Scope
All Tier 0 and Tier 1 TPSPs. Tier 2 monitored on annual sample. Tier 3 monitored on event basis.

## 3. Requirements

### 3.1 Monitoring inputs by TPSP tier

| TPSP tier | Continuous inputs |
|---|---|
| Tier 0 | TPSP incident notifications (24h SLA); attestation expiry tracking; external threat intel naming TPSP; cyber posture monitoring tooling (security ratings service); annual security questionnaire; monthly KCI review |
| Tier 1 | TPSP incident notifications; attestation tracking; threat intel; semi-annual posture review |
| Tier 2 | Attestation tracking; annual posture review |
| Tier 3 | Attestation tracking only |

### 3.2 TPSP incident notification SLA
| Ref | Requirement |
|---|---|
| 3.2.1 | TPSP shall notify GIBB within 24 hours of TPSP's detection of any security incident materially affecting GIBB data or services |
| 3.2.2 | Notification recorded in [REG-TPS](../06-registers/REG-TPS-third-party-service-provider-register.md) `incidents_to_date`; SEV assessment per [STD-IR-01](STD-IR-01-incident-classification-and-severity-standard.md) |
| 3.2.3 | GIBB-side incident response per [PLN-01](../05-plans/PLN-01-incident-response-plan.md) and [SOP-IR-01](../04-procedures/SOP-IR-01-incident-triage-sop.md) |

### 3.3 Attestation monitoring
| Ref | Requirement |
|---|---|
| 3.3.1 | Material TPSP attestations (ISO 27001, SOC 2 Type 2, PCI DSS where applicable) tracked with 90-day pre-expiry alert |
| 3.3.2 | Expired attestation triggers TPSP follow-up; >30 days expired = control deficiency reported to CRO |

### 3.4 External signals
| Ref | Requirement |
|---|---|
| 3.4.1 | TPSP external threat intel (security ratings, breach disclosures) reviewed monthly for Tier 0/1 |
| 3.4.2 | Material adverse signal triggers immediate TPSP engagement and re-assessment |

### 3.5 Annual questionnaire
For Tier 0/1: annual security questionnaire covering: control environment changes, sub-contracting changes, incident summary, BCP test outcomes, ransomware preparedness. Results recorded in [REG-TPS](../06-registers/REG-TPS-third-party-service-provider-register.md).

### 3.6 KCIs
| KCI | Target | Cadence |
|---|---|---|
| Tier 0/1 TPSPs with current attestation | 100% | Monthly |
| TPSP incident notifications met 24h SLA | ≥ 95% | Quarterly |
| Tier 0/1 TPSPs with annual questionnaire returned | 100% | Annual |
| Material adverse signals triaged within 5 business days | 100% | Continuous |

### 3.7 Escalation
| Trigger | Escalation |
|---|---|
| TPSP refuses to provide attestation evidence | CISO + CRO; RMC if material |
| TPSP security incident material to GIBB | Per [PLN-01 IRP](../05-plans/PLN-01-incident-response-plan.md) |
| Pattern of degraded TPSP posture | TPSP review; potential exit per [SOP-TP-03](../04-procedures/SOP-TP-03-tpsp-exit-sop.md) |

## 4. Exceptions
Per [POL-10](../02-policies/POL-10-it-vendor-management-policy.md). Reduced monitoring depth requires CISO + CRO approval.

## 5. Related documents
[STD-TP-01](STD-TP-01-tpsp-due-diligence-standard.md); [STD-TP-02](STD-TP-02-outsourcing-contractual-security-standard.md); [REG-TPS](../06-registers/REG-TPS-third-party-service-provider-register.md); [REG-OUT](../06-registers/REG-OUT-material-outsourcing-register.md); SOP-TP-02 TPSP Periodic Reassessment SOP

## 6. References
BNM RMiT 28 Nov 2025 Section 10.49; BNM Outsourcing PD; ISO/IEC 27036-3.

## 7. Document control
| Version | Date | Author | Approver | Change |
|---|---|---|---|---|
| 1.0 | [Effective] | CISO + Head of Procurement | CISO | Initial |
