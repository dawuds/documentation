# STD-CM-01 — Change Management Standard

| | |
|---|---|
| **Document ID** | STD-CM-01 |
| **Layer** | Standard (Tier 2) |
| **Version** | 1.0 |
| **Owner** | Chief Information Officer |
| **Approver** | CIO |
| **Classification** | Internal |
| **Effective** | [Effective] |
| **Next review** | Annual or on material toolchain change |
| **Parent policy** | [POL-07 Change Management Policy](../02-policies/POL-07-change-management-policy.md) |
| **Parent framework(s)** | [TRMF](../01-frameworks/TRMF.md) |
| **RMiT clause(s)** | Section 10.11; cross-references 10.4–10.16 |
| **COBIT objective(s)** | BAI06; BAI07 |
| **Practice standard(s)** | ITIL 4 Change Enablement; ISO/IEC 27002:2022 control 8.32 |

---

## 1. Purpose

This standard operationalises [POL-07 Change Management Policy](../02-policies/POL-07-change-management-policy.md) into measurable, mandatory requirements for change categorisation, approval, testing, scheduling, deployment, and review.

## 2. Scope

All changes to production technology as defined in POL-07.

## 3. Requirements

### 3.1 Change categorisation

| Ref | Requirement | Measurement / evidence |
|---|---|---|
| 3.1.1 | Every change **shall** be categorised at submission as Standard, Normal, Major, or Emergency. | Change ticket; categorisation field mandatory |
| 3.1.2 | Standard changes **shall** be drawn from a pre-authorised catalogue. The catalogue is reviewed annually. | Standard change catalogue (CAB-maintained) |

### 3.2 Authorisation thresholds

| Change type | Approver | SLA — submission to approval |
|---|---|---|
| Standard | Pre-authorised | n/a |
| Normal | CAB | 5 business days |
| Major | CAB + business sponsor + CISO | 10 business days |
| Emergency | Named on-call authority (Head of IT Ops / CISO / CIO delegate) | ≤ 1 hour |

### 3.3 Risk assessment

| Ref | Requirement | Evidence |
|---|---|---|
| 3.3.1 | Every Normal and Major change **shall** have a documented risk assessment covering operational, security, regulatory, customer, and (where applicable) Shariah-compliance impact. | Risk assessment field in change ticket |
| 3.3.2 | Changes to internet-facing systems **shall** include CISO security sign-off. | Security review field |
| 3.3.3 | Changes affecting Islamic finance product systems' Shariah logic **shall** include Shariah Committee approval. | Shariah approval field |

### 3.4 Testing

| Ref | Requirement | Evidence |
|---|---|---|
| 3.4.1 | Normal and Major changes **shall** be tested in a non-production environment representative of production. | Test results attached to change |
| 3.4.2 | Test scope **shall** include functional, regression, security (per [POL-17](../02-policies/POL-17-secure-development-policy.md)), and (where applicable) performance. | Test plan |
| 3.4.3 | Test data **shall not** be live production data unless anonymised or under documented exception with strong access control. | Data masking attestation |

### 3.5 Independent review

| Ref | Requirement | Evidence |
|---|---|---|
| 3.5.1 | Per RMiT 10.11, system changes **shall** undergo independent review by a competent person not involved in development. | Independent review sign-off |

### 3.6 Scheduling

| Ref | Requirement | Evidence |
|---|---|---|
| 3.6.1 | Approved changes **shall** appear in the Forward Schedule of Changes with ≥ 5 business days notice for affected business units (≥ 24 hours for Emergency). | FSC publication |
| 3.6.2 | Changes to customer-facing services **shall** be communicated to customers per the bank's customer communication standard. | Customer notice |

### 3.7 Rollback

| Ref | Requirement | Evidence |
|---|---|---|
| 3.7.1 | Every Normal and Major change **shall** have a documented rollback plan, executable within service RTO. | Rollback plan field |
| 3.7.2 | Rollback **shall** be tested for Major changes prior to production deployment. | Rollback test record |

### 3.8 Deployment

| Ref | Requirement | Evidence |
|---|---|---|
| 3.8.1 | Deployment **shall** be logged with timestamps and named deployer. | Deployment log |
| 3.8.2 | Production access for deployment **shall** follow [POL-06 Access Control Policy](../v1/01-policies/02-access-control-policy.md) (re-anchored under CRMF in future session). | Access log |

### 3.9 Emergency change

| Ref | Requirement | Evidence |
|---|---|---|
| 3.9.1 | Emergency changes **shall** be limited to: incident response, critical security vulnerability remediation, regulatory directive with insufficient lead time. | Emergency justification field |
| 3.9.2 | Every emergency change **shall** undergo retrospective CAB review within 5 business days. | Retrospective CAB minute |

### 3.10 Post-implementation review

| Ref | Requirement | Evidence |
|---|---|---|
| 3.10.1 | Major changes **shall** undergo post-implementation review within 30 days, assessing outcomes and lessons. | PIR document |

### 3.11 Change-related incident attribution

| Ref | Requirement | Evidence |
|---|---|---|
| 3.11.1 | Incidents attributed to a recent change **shall** trigger investigation into the change process — categorisation, testing, approval. Pattern findings drive process improvement. | Incident-to-change correlation analysis |

## 4. Exceptions

Per [POL-07](../02-policies/POL-07-change-management-policy.md) and TRMF Section 12. Bypass of any requirement in this standard requires CISO + CIO sign-off.

## 5. Related documents

- **Parent policy:** [POL-07](../02-policies/POL-07-change-management-policy.md)
- **Implementing procedures:** SOP-CM-01 Change Authorisation SOP (Session 3 build); SOP-CM-02 Emergency Change SOP

## 6. References

- BNM RMiT 28 November 2025 — Section 10.11; 10.4–10.16
- COBIT 2019 — BAI06; BAI07
- ITIL 4 — Change Enablement
- ISO/IEC 27002:2022 — control 8.32

## 7. Document control

| Version | Date | Author | Reviewer | Approver | Change summary |
|---|---|---|---|---|---|
| 1.0 | [Effective] | CIO | Head of IT Ops, CISO | CIO | Initial Effective |
