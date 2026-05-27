# [Framework Title]

| | |
|---|---|
| **Document ID** | [TRMF / CRMF / BCMF / TPRMF / CIMF / NCIIF / CloudRMF / DGF / AIGF] |
| **Version** | [N.N] |
| **Owner** | [Role(s)] |
| **Approver** | Board Risk Management Committee |
| **Effective** | [YYYY-MM-DD] |
| **Next review** | [YYYY-MM-DD — annual + on regulatory change] |
| **Classification** | Internal |
| **RMiT clause(s)** | [Section N.N or N.N–N.M, 28 Nov 2025 issuance] |
| **COBIT objective(s)** | [EDMxx / APOxx / BAIxx / DSSxx / MEAxx] |
| **Practice standard(s)** | [ISO 27001:2022 / ITIL 4 / ISO 22301:2019 / ISO 42001:2023 / etc.] |
| **Additional anchors** | [NACSA / MCIPD / SGF / Cloud TRAG / NIST AI RMF / PDPA / IFSA / etc.] |

---

## 1. Foreword

[Short Board / RMC sign-off statement establishing the framework. 2–4 sentences. Names the authority under which the framework is established and the binding nature of its principles.]

---

## 2. Purpose

[One paragraph. Why this framework exists. The outcome it drives. The regulatory and business rationale for it being a bank-authored framework rather than an embedded chapter of another document.]

---

## 3. Scope

**In scope.** [Specific list — assets, processes, geographies, business lines, personnel categories, third parties.]

**Out of scope.** [Explicit exclusions. "Everything not listed above" is not a scope.]

---

## 4. Definitions

| Term | Definition |
|---|---|
| [Term specific to this framework] | [Definition; cite source where standardised] |

[Cross-reference the master glossary at `../_context/glossary.md` for terms used across multiple frameworks. Define here only what is specific to this framework or where this framework's usage differs from common.]

---

## 5. Governance

### 5.1 Three-line model

| Line | Function | Responsibility in this framework |
|---|---|---|
| 1st | [Operating function(s)] | [Operate controls; produce evidence] |
| 2nd | [Risk / Compliance function(s)] | [Challenge; oversee; measure] |
| 3rd | Internal Audit | [Independent assurance] |

### 5.2 RACI

| Activity | Board / RMC | CRO | CISO | [Other role] |
|---|---|---|---|---|
| Approve framework | A | C | C | I |
| Operate framework | I | A | R | R |
| Independent review | I | C | C | A (Internal Audit) |

R = Responsible · A = Accountable · C = Consulted · I = Informed

### 5.3 Approval authority

| Action | Authority |
|---|---|
| Approve this framework (major version) | Board Risk Management Committee |
| Approve minor revisions | [Owner role] |
| Approve exceptions | [Per Section 12] |

---

## 6. Framework principles

The following principles are mandatory across the scope of this framework. Each uses **shall** and binds at the principle level. Operational requirements cascade through Layers 3–6.

- **6.1** [Principle 1]. *(Implements [RMiT clause]; [COBIT objective]; [practice standard clause].)*
- **6.2** [Principle 2]. *(Implements …)*
- …

[6–10 principles, each one paragraph maximum. Each anchored to a specific regulatory clause and COBIT objective.]

---

## 7. Framework structure

[Description of the framework model itself. Diagram preferred (mermaid or ASCII). Names the components, how they interact, and how they relate to the framework's lifecycle in Section 8.]

```mermaid
flowchart TB
    [framework structure diagram]
```

---

## 8. Lifecycle / operating model

[How the framework operates as a continuous cycle. Examples:
- Risk frameworks: Identify → Assess → Treat → Monitor → Report
- Cyber resilience: IPDRR (Identify, Protect, Detect, Respond, Recover)
- Business Continuity: BIA → RTO/RPO setting → Strategy → Implementation → Testing → Maintenance
- Data Governance: Define → Capture → Steward → Use → Retire]

### 8.1 [Phase 1 name]

- **Objective:** [What this phase delivers]
- **Activities:** [Bullet list]
- **Inputs:** [What feeds into this phase]
- **Outputs:** [What this phase produces — typically registers, reports, decisions]
- **Owner:** [Role]
- **Cadence:** [Continuous / monthly / quarterly / annual]

### 8.2 [Phase 2 name]

…

---

## 9. Implementation requirements

This framework cascades into the following document set. Each item below is mandatory and named here.

### 9.1 Policies (Layer 3)

| Policy ID | Title | Owner | Status |
|---|---|---|---|
| POL-XX | [Policy title] | [Role] | [Effective / In development] |

### 9.2 Standards (Layer 4)

| Standard ID | Title | Owner | Status |
|---|---|---|---|
| STD-XX | [Standard title] | CISO / [function head] | [Effective / In development] |

### 9.3 Procedures / SOPs (Layer 5)

| SOP ID | Title | Owner | Status |
|---|---|---|---|
| SOP-XX | [SOP title] | [Process owner] | [Effective / In development] |

### 9.4 Plans

| Plan ID | Title | Owner | Status |
|---|---|---|---|
| PLN-XX | [Plan title] | [CISO / COO / etc.] | [Effective / In development] |

### 9.5 Registers (Layer 6 — evidence)

| Register ID | Title | Owner | Cadence |
|---|---|---|---|
| REG-XX | [Register title] | [Process owner] | [Continuous / quarterly / etc.] |

---

## 10. Performance measurement

### 10.1 Key Risk Indicators (KRIs)

| KRI | Definition | Target / threshold | Reporting cadence | Owner |
|---|---|---|---|---|
| [KRI name] | [What it measures] | [Numeric or qualitative target] | [Cadence] | [Role] |

### 10.2 Key Control Indicators (KCIs)

| KCI | Control measured | Target | Reporting cadence | Owner |
|---|---|---|---|---|
| [KCI name] | [Control it evidences] | [Target] | [Cadence] | [Role] |

### 10.3 Key Performance Indicators (KPIs)

| KPI | Definition | Target | Reporting cadence | Owner |
|---|---|---|---|---|
| [KPI name] | [What it measures] | [Target] | [Cadence] | [Role] |

---

## 11. Reporting and escalation

### 11.1 Reporting cadence

| Audience | Content | Cadence | Owner |
|---|---|---|---|
| Board | [Summary report] | Annual + on material event | [Role] |
| Board Risk Management Committee | [Detailed report] | Quarterly | [Role] |
| [Other committee] | […] | […] | […] |
| Senior management | [Operating metrics] | Monthly | [Role] |

### 11.2 Escalation triggers

| Trigger | Authority to escalate to | Channel | SLA |
|---|---|---|---|
| [Event class] | [Role / body] | [Channel] | [Time-bound] |

---

## 12. Exceptions

Documented deviations from this framework's principles or its cascading documents require approval per the matrix below. Every exception is logged in the Exception Register, time-bound, and accompanied by a compensating control.

| Exception type | Approver | Maximum duration | Renewal authority |
|---|---|---|---|
| Framework principle exception | Board Risk Management Committee | 12 months | RMC (one renewal) |
| Policy exception | RMC | 12 months | RMC (one renewal) |
| Standard exception | CISO / function head | 12 months | RMC after one renewal |

---

## 13. Independent review

| Review | Frequency | Owner |
|---|---|---|
| Internal Audit | Per audit plan; minimum every [N] years for this framework | Internal Audit |
| External certification (where applicable) | Per certification cycle | [Function] |
| Regulator examination (BNM / NACSA) | Per regulator schedule | CCO + [Function head] |
| Independent assurance review | [When commissioned by RMC] | External assurance provider |

Findings from any independent review are tracked through the framework's corrective action register and reported to RMC quarterly.

---

## 14. Related frameworks

This framework interacts with the following bank-authored frameworks. Each relationship is governed by the seams defined in `../_context/seams.md`.

| Related framework | Relationship | Cross-statement |
|---|---|---|
| [Framework] | [Peer / parent / child / overlap] | [Stated seam resolution] |

---

## 15. References

### 15.1 Regulatory (Layer 0)

- BNM Risk Management in Technology (RMiT), policy document, 28 November 2025 issuance (BNM/RH/PD 028-100) — clauses [list]
- [Other BNM PDs as applicable]
- [Other Malaysian statutes as applicable]

### 15.2 Reference frameworks (Layer 1)

- COBIT 2019 — objectives [list]
- [ISO standards with editions]
- [NIST publications]
- [Other reference frameworks]

### 15.3 Internal cross-references

- [Repo-internal documents this framework references]

---

## 16. Document control

| Version | Date | Author | Reviewer | Approver | Change summary |
|---|---|---|---|---|---|
| 0.1–0.9 | [drafting period] | [Role] | [2nd line review] | — | Drafting cycle |
| 1.0 | [date] | [Author role] | RMC | Board Risk Management Committee | Initial Effective version |
