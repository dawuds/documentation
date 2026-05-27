# POL-07 — Change Management Policy

| | |
|---|---|
| **Document ID** | POL-07 |
| **Layer** | Policy (Tier 1) |
| **Version** | 1.0 |
| **Owner** | Chief Information Officer |
| **Approver** | Risk Management Committee |
| **Classification** | Internal |
| **Effective** | [Effective] |
| **Next review** | Annual |
| **Parent framework(s)** | [TRMF](../01-frameworks/TRMF.md) |
| **RMiT clause(s)** | Section 10.11 (Independent Review of System Changes); cross-references Section 10.4–10.16 (System Development and Acquisition); Section 11.5 (cyber control measures for change) |
| **COBIT objective(s)** | BAI06 Managed IT Changes; BAI07 Managed IT Change Acceptance and Transitioning |
| **Practice standard(s)** | ITIL 4 Change Enablement practice; ISO/IEC 27002:2022 control 8.32 (change management) |
| **Additional anchors** | BNM Shariah Governance Framework (Shariah review for product-system changes) |

---

## 1. Purpose

This policy establishes the disciplines under which changes to GIBB technology systems and supporting infrastructure are authorised, assessed for risk, tested, scheduled, communicated, deployed, and recorded. Change management is the single most consequential operational discipline for the prevention of incident, security degradation, and audit finding.

## 2. Scope

**Applies to:** all changes to production technology — applications, infrastructure (server, storage, network), cloud configuration, identity and access systems, security tooling, data pipelines, AI models in production. All change types — standard, normal, major, emergency.

**Does not apply to:** non-production environments under their own controls; routine end-user configuration changes within bank-issued bring-your-own-device parameters.

## 3. Definitions

| Term | Definition |
|---|---|
| **Change** | Any addition, modification, or removal that affects production technology services. |
| **Standard change** | A pre-approved, low-risk, repeatable change with documented procedure. |
| **Normal change** | A change requiring assessment, scheduling, and approval through the standard CAB process. |
| **Major change** | A change with broad impact, complex risk, or business-critical implications, requiring additional governance. |
| **Emergency change** | A change deployed outside normal process to address incident or critical risk; reviewed retrospectively. |
| **Change Advisory Board (CAB)** | The cross-functional body reviewing and authorising normal and major changes. |
| **Forward Schedule of Changes (FSC)** | The published forward schedule of approved changes. |

## 4. Policy statements

### 4.1 Authorisation

- **4.1.1** Every change to production **shall** be authorised through the change management process before deployment. *(Implements RMiT 10.11; ISO/IEC 27002:2022 control 8.32; COBIT BAI06.)*
- **4.1.2** Authorisation level **shall** match change category — standard changes via documented pre-authorisation; normal changes by CAB; major changes by CAB + business sponsor; emergency changes by named on-call authority with mandatory retrospective CAB review.

### 4.3 Risk assessment

- **4.3.1** Every change **shall** be assessed for operational, security, regulatory, customer, and (where applicable) Shariah-compliance impact prior to authorisation.
- **4.3.2** Changes affecting Islamic finance product systems' Shariah-compliance logic **shall** undergo Shariah review per the [POL-01 IT Governance Policy](POL-01-it-governance-policy.md) Section 4.7.
- **4.3.3** Changes affecting Confidential or higher customer data **shall** include privacy impact assessment per [CIMF](../01-frameworks/CIMF.md).

### 4.4 Independent review

- **4.4.1** System changes **shall** be subject to independent review and approval per RMiT 10.11. Independent review is undertaken by a competent person not involved in the change development.

### 4.5 Testing

- **4.5.1** Changes **shall** be tested in non-production environments before production deployment, except for emergency changes under defined emergency-change authority.
- **4.5.2** Production data **shall not** be used in non-production environments without anonymisation or strong access control per [POL-17 Secure Development Policy](POL-17-secure-development-policy.md).

### 4.6 Scheduling and communication

- **4.6.1** Approved changes **shall** be scheduled and published in the Forward Schedule of Changes with sufficient notice for affected business units.
- **4.6.2** Changes affecting customer-facing services **shall** be communicated to customers as per the bank's customer communication standard.

### 4.7 Deployment and rollback

- **4.7.1** Every change **shall** have a documented rollback plan executable within RTO of the affected service.
- **4.7.2** Deployment **shall** be logged with sufficient detail to support post-implementation review and forensic reconstruction.

### 4.8 Emergency change

- **4.8.1** Emergency changes **shall** be limited to genuine emergencies — incident response, critical security vulnerability remediation, regulatory directive with insufficient lead time.
- **4.8.2** Every emergency change **shall** undergo retrospective CAB review within 5 business days, with lessons fed to the change management process.

### 4.9 Post-implementation review

- **4.9.1** Major changes **shall** undergo post-implementation review within 30 days of deployment, assessing whether intended outcomes were achieved and identifying lessons.

## 5. Roles and responsibilities

| Role | R | A | C | I |
|---|---|---|---|---|
| Risk Management Committee | | A | | I |
| CIO | A | | | |
| Head of IT Operations | R | | C | I |
| Change Advisory Board | R | | | I |
| Change initiators (business, IT, vendors) | R | | C | I |
| CISO | | | C (security impact) | I |
| Shariah Compliance | | | C (Shariah-relevant changes) | I |
| Internal Audit | | | C | I |

## 6. Exceptions

Per TRMF Section 12. Bypass of change management requires post-event review and CISO + CIO sign-off, regardless of justification.

## 7. Enforcement

Per TRMF Section 12. Unauthorised changes are control failures reportable to RMC.

## 8. Related documents

- **Parent framework:** [TRMF](../01-frameworks/TRMF.md)
- **Supporting standards:** Change Management Standard (to be drafted); Emergency Change Standard
- **Supporting procedures:** Change Authorisation SOP; Emergency Change SOP; Post-Implementation Review SOP
- **Related policies:** [POL-17](POL-17-secure-development-policy.md); [POL-16](POL-16-operations-security-policy.md); [POL-09](POL-09-it-asset-management-policy.md)

## 9. References

- BNM RMiT, 28 November 2025: Section 10.11; cross-references 10.4–10.16; 11.5
- COBIT 2019 — BAI06 Managed IT Changes; BAI07 Managed IT Change Acceptance and Transitioning
- ITIL 4 — Change Enablement practice
- ISO/IEC 27002:2022 — control 8.32 (change management)
- BNM Shariah Governance Framework

## 10. Document control

| Version | Date | Author | Reviewer | Approver | Change summary |
|---|---|---|---|---|---|
| 1.0 | [Effective] | CIO | RMC | RMC | Initial Effective version |
