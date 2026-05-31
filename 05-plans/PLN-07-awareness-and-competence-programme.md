# Awareness and Competence Programme

| | |
|---|---|
| **Document ID** | PLN-07 |
| **Layer** | Plan |
| **Owner** | CHRO + CISO (joint) |
| **Approver** | Risk Management Committee |
| **Classification** | Internal |
| **Version** | 1.0 |
| **Effective date** | [Effective] |
| **Next review** | Annual; immediate on material change to threat landscape or curriculum |
| **Implements** | BNM RMiT (28 Nov 2025) Section 15 (Security Awareness and Education); ISO/IEC 27001:2022 Clause 7.2 (Competence) + Clause 7.3 (Awareness); ISO/IEC 27002:2022 control 6.3 (Information security awareness, education and training); ISO/IEC 22301:2019 Clause 7.2; ISO/IEC 42001:2023 Clause 7.2 (for AIMS-scoped roles) |
| **Parent framework(s)** | [CRMF](../01-frameworks/CRMF.md); [TRMF](../01-frameworks/TRMF.md); [AIGF](../01-frameworks/AIGF.md) (AI competence) |
| **COBIT objective(s)** | APO07 Managed Human Resources; APO13 Managed Security (awareness component); DSS05 Managed Security Services |

---

## 1. Purpose

To define how GIBB builds and maintains the **security awareness and role-specific competence** of all workforce members (employees, contractors, secondees, third-party personnel with access) — meeting the mandatory expectations of BNM RMiT Section 15, ISO 27001 Clauses 7.2/7.3, and the bank's own personnel security policy [POL-HR-01](../02-policies/POL-HR-01-hr-security-policy.md).

Awareness is **continuous** (not annual-only) and **layered** (baseline for all + role-specific for higher-risk roles). The programme is measured, and ineffectiveness is treated as a control failure, not a soft signal.

## 2. Scope

- All employees and contractors with GIBB-system access.
- Secondees and third-party personnel with GIBB-system access (delivered jointly with the supplier per [POL-19](../02-policies/POL-19-supplier-security-policy.md)).
- Board members and senior executives — separate curriculum focused on cyber-resilience oversight, regulatory expectation, and incident-response role.

Out of scope: customer-facing awareness (separate channel under [POL-CI-01](../02-policies/POL-CI-01-customer-data-protection-policy.md)).

## 3. Programme structure

### 3.1 Baseline awareness (all workforce)

| Element | Cadence | Owner | Method |
|---|---|---|---|
| Joiner onboarding security module | Within 30 days of start | CHRO + CISO | LMS — mandatory; manager-tracked |
| Annual refresher | Within 12 months of last completion | CHRO + CISO | LMS — mandatory |
| Phishing simulation | Monthly | CISO | Simulation platform — failures trigger micro-learning |
| Security newsletter | Quarterly | CISO | Internal comms; threat-trend summary, recent incidents (sanitised), reminders |
| Event-driven communications | As warranted | CISO + Corporate Comms | E.g., active threat campaign, incident lessons learned, policy change |

### 3.2 Role-specific competence (higher-risk roles)

| Role family | Specific competence required | Cadence | Owner |
|---|---|---|---|
| Developers | Secure development (OWASP Top 10 + ASVS + supply-chain) | Annual + on language/framework change | Head of Engineering + CISO |
| System administrators / DevOps | Hardening, least-privilege, secrets management, change discipline | Annual | Head of IT Ops + CISO |
| SOC analysts | Detection engineering, IR, forensics | Continuous (cert-tracked); shadow on real incidents | Head of SOC |
| IT operations on-call | Incident triage, escalation, SOP execution | Annual + tabletop participation | Head of IT Ops |
| Customer-facing staff (branch, contact centre, RM) | Social engineering, customer-data handling, account-recovery fraud patterns | Annual + on attack-pattern shift | Head of Distribution + CISO |
| Privileged users (DBAs, network engineers, cloud admins) | Privileged-access discipline, just-in-time, audit-trail integrity | Annual + per access-grant | Head of IAM + CISO |
| HR / payroll | PDPA, MCIPD, banking secrecy as applied to personnel data | Annual | CHRO + DPO + GC |
| Procurement | TPRM, supplier security clauses, MCIPD permitted disclosures | Annual | Head of Procurement + CISO |
| AI use-case owners | AI risk, model validation, bias, fairness, Shariah considerations | Annual; per-use-case at onboarding | CDO + CISO + Shariah Committee liaison |
| NCII-scope roles | NACSA Code of Practice, NCII reporting | Annual | CISO + CCO |
| Senior management + ExCo | Strategic cyber risk, regulator expectation, incident command | Annual; tabletop participation | CISO + CRO |
| Board members | Cyber resilience oversight, NCII obligation, BCM oversight | Annual; cyber drill observation | RMC Chair + CISO |

### 3.3 Continuous reinforcement

- Phishing simulations every month — click rate is a tracked KPI in [REG-OBJ](../06-registers/REG-OBJ-information-security-objectives-register.md).
- Just-in-time reminders at the point of risk (e.g., flagged outbound email with sensitive content; new device login; unusual download).
- "Lessons from the last incident" summaries within 30 days of any SEV-1 / SEV-2 PIR — distributed via the relevant role's comms channel.
- Threat-actor profile briefings to relevant teams when new TTPs against banks appear.

### 3.4 Competence assurance

- Each role family has a **named curriculum** mapped to ISO 27001 Clause 7.2 evidence requirements: identification of competence, provision of training, evaluation of effectiveness, retention of records.
- Records retained in the LMS for the lifetime of the workforce relationship plus statutory retention.
- Effectiveness measured via: (a) completion rates (lagging), (b) simulated-attack performance (lagging), (c) competence assessment at role change (point-in-time), (d) post-incident competence review for human-factor incidents.

## 4. Roles and responsibilities

| Role | R | A | C | I |
|---|---|---|---|---|
| Risk Management Committee | | A | | I |
| CHRO | A (programme delivery) | | C | |
| CISO | A (content + measurement) | | C | |
| Line managers | R (completion of their teams) | | | I |
| HR Business Partners | R (LMS administration) | | | I |
| Internal Audit (3rd line) | | | C (programme effectiveness audit per [PLN-08](PLN-08-internal-audit-plan.md)) | I |

## 5. Effectiveness measurement and reporting

| Metric | Target | Cadence | Reported to |
|---|---|---|---|
| % workforce completed annual baseline within window | ≥ 98% | Monthly | RMC quarterly |
| Phishing simulation click rate | ≤ 4% monthly mean | Monthly | RMC quarterly |
| % role-specific competence current for higher-risk roles | 100% | Quarterly | RMC quarterly |
| % new joiners completed onboarding within 30 days | 100% | Monthly | CHRO + CISO |
| Board cyber competence — annual attestation | 100% | Annual | Board |
| Effectiveness-of-awareness incident contribution | Trend ↓ year-on-year | Annual | RMC + Board |

Underperformance against any baseline KPI is treated as a control deficiency, logged in [REG-CAP](../06-registers/REG-CAP-corrective-action-register.md), and reviewed at the next Management Review per [REG-MR](../06-registers/REG-MR-management-review-register.md).

## 6. Related documents

- **Parent policy:** [POL-HR-01 HR Security Policy](../02-policies/POL-HR-01-hr-security-policy.md) Section 3.3
- **Register:** [REG-AWR Awareness and Competence Register](../06-registers/REG-AWR-awareness-and-competence-register.md)
- **Cross-references:** [REG-OBJ](../06-registers/REG-OBJ-information-security-objectives-register.md) (phishing click-rate KPI); [REG-INC](../06-registers/REG-INC-incident-register.md) (human-factor incidents feed back into curriculum); [PLN-05 Cyber Drill](PLN-05-cyber-drill-exercise-plan.md) (annual exercise); [POL-04](../02-policies/POL-04-information-security-policy.md); [POL-13](../02-policies/POL-13-incident-management-policy.md)

## 7. Document control

| Version | Date | Author | Reviewer | Approver | Change summary |
|---|---|---|---|---|---|
| 1.0 | 2026-05-30 | CHRO + CISO | RMC | Risk Management Committee | Initial version. Closes RMiT Section 15 + ISO 7.2/7.3 evidence gap identified in v2 multi-agent review (GRC: "RMiT Section 15 — required programme. No document exists"). |
