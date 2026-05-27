# GRC platform ingestion format

How the v2 content can be structured for ingestion into a GRC platform (Archer, ServiceNow GRC, OneTrust, MetricStream, ProcessUnity, LogicGate, or equivalent) when GIBB selects one.

← [_learning home](README.md) · [Repo home](../README.md)

> **Source.** Addresses [Q-010 in open-questions.md](../_context/open-questions.md) — GRC tooling. This is implementation guidance, not part of the ISMS itself.

---

## 1. Why this matters

When a bank adopts a GRC platform, content needs to map onto the platform's object model. Most platforms expose similar primitives:

- **Authorities** (regulations, standards) → Layer 0 + Layer 1
- **Policies** → Layer 3
- **Standards / Procedures** → Layer 4 + Layer 5
- **Controls** → derived from policy/standard requirements
- **Control assessments** → from registers
- **Risks** → REG-TR + risk-related registers
- **Issues / Findings** → REG-CAP + audit registers
- **Evidence** → registers + linked artefacts

Markdown documents are not directly ingestible. The v2 content needs **structured-data extraction** to populate the platform.

---

## 2. Recommended canonical object model

The objects below are intentionally vendor-neutral. Most GRC platforms support them under different naming.

### 2.1 Authority

```yaml
authority:
  id: AUTH-001
  type: regulation | standard | framework
  name: "BNM Risk Management in Technology"
  acronym: "BNM RMiT"
  version: "28 November 2025"
  issuer: "Bank Negara Malaysia"
  jurisdiction: "Malaysia"
  reference: "BNM/RH/PD 028-100"
  scope_applicability_filter: "licensed_FI"
  retrieved_url: "https://www.bnm.gov.my/..."
  clauses:
    - clause_id: "AUTH-001-S8"
      hierarchy: "Section 8 — Governance"
      sub_clauses:
        - clause_id: "AUTH-001-S8.1"
          text: "Board approval of technology risk appetite..."
```

GIBB authorities to ingest:
- BNM RMiT (28 Nov 2025) — Section 8 through 18 + Appendices 1-11
- Cyber Security Act 2024 + NACSA Code of Practice
- BNM Outsourcing PD; BCM PD; MCIPD; Operational Risk Reporting PD; Shariah Governance Framework; Cloud TRAG
- PDPA 2010; IFSA 2013; FSA 2013; Computer Crimes Act 1997
- ISO/IEC 27001:2022; ISO/IEC 27002:2022; ISO/IEC 22301:2019; ISO/IEC 42001:2023
- COBIT 2019 (with Focus Areas)
- ITIL 4
- NIST CSF 2.0; NIST AI RMF 1.0 + GenAI Profile; NIST SP 800-61/63B/88/57
- EU AI Act 2024; MAS FEAT

### 2.2 Framework (bank-authored)

```yaml
framework:
  id: TRMF
  name: "Technology Risk Management Framework"
  layer: 2
  owner_role: "CRO + Head of Technology Risk Management"
  approver_role: "Board Risk Management Committee"
  effective_date: "[Effective]"
  next_review: "Annual + on regulatory change"
  authorities_implemented:
    - clause: AUTH-001-S9.2
      coverage: "full"
    - clause: AUTH-001-S9.1
      coverage: "full"
    # ...
  cobit_objectives:
    - "EDM03"
    - "APO12"
    - "APO01"
  practice_standards:
    - "ISO 31000:2018"
    - "ISO/IEC 27005:2022"
  source_document: "01-frameworks/TRMF.md"
```

Repeat for: TRMF, CRMF, BCMF, TPRMF, CIMF, NCIIF, CloudRMF, DGF, AIGF.

### 2.3 Policy

```yaml
policy:
  id: POL-04
  name: "Information Security Policy"
  layer: 3
  version: "1.0"
  parent_framework: CRMF
  owner_role: "CISO"
  approver_role: "Board of Directors"
  effective_date: "[Effective]"
  next_review: "Annual"
  shall_statements:
    - statement_id: POL-04.6.1.1
      text: "Information security shall be governed by the Board..."
      implements_clauses:
        - AUTH-001-S8.1
        - AUTH-001-S8.2
      cobit_objectives:
        - APO13
  source_document: "02-policies/POL-04-information-security-policy.md"
```

Each `shall` statement becomes a candidate control statement.

### 2.4 Standard

```yaml
standard:
  id: STD-AC-01
  name: "Password & Authentication Standard"
  layer: 4
  parent_policy: POL-06
  parent_framework: CRMF
  owner_role: "CISO"
  measurable_requirements:
    - req_id: STD-AC-01.3.2.1
      text: "Standard workforce account passwords shall be a minimum of 14 characters."
      measurement: "IDP policy configuration; quarterly evidence extract"
      implements_clauses:
        - AUTH-001-S10.55
```

### 2.5 Procedure

```yaml
procedure:
  id: SOP-AC-01
  name: "Joiner / Mover / Leaver SOP"
  layer: 5
  parent_standard: STD-AC-01
  parent_policy: POL-06
  parent_framework: CRMF
  process_owner: "Head of IAM"
  triggers:
    - "Workday Person event"
    - "Workday status change"
  steps:
    - step_id: J1
      actor: "HR Business Partner"
      action: "Create Person record in Workday"
      tool: "Workday"
      output: "personId issued"
      sla_hours: 0  # immediate
```

### 2.6 Plan

```yaml
plan:
  id: PLN-01
  name: "Incident Response Plan"
  parent_framework: CRMF
  parent_policy: POL-13
  owner_role: "CISO"
  activation_authority: "CISO (SEV-1) / Head of SOC (SEV-2)"
  phases:
    - phase_id: 5.1
      name: "Preparation"
    - phase_id: 5.2
      name: "Detection and Analysis"
    # ...
```

### 2.7 Register / Control assessment

```yaml
register:
  id: REG-PAR
  name: "Privileged Access Review Register"
  parent_framework: CRMF
  parent_standard: STD-AC-01
  parent_policy: POL-06
  cadence: "quarterly"
  owner_role: "Head of IAM"
  entries:
    - entry_id: PAR-2026-Q1
      period_start: "2026-01-01"
      period_end: "2026-03-31"
      accounts_in_scope: 412
      accounts_reviewed: 412
      coverage: 1.00
      recertified: 396
      modified: 9
      revoked: 7
      signed_off_by: "Head of IAM 2026-03-19; CISO 2026-03-20"
```

### 2.8 Risk

```yaml
risk:
  id: RISK-2026-001
  title: "Ransomware affecting production estate via initial-access broker chain"
  category: "Cyber"
  owner_role: "CISO"
  inherent_likelihood: 5
  inherent_impact: 5
  inherent_rating: 25
  controls_in_place: ["EDR coverage 100%", "Tamper-proof backups", "Network segmentation", ...]
  residual_likelihood: 3
  residual_impact: 4
  residual_rating: 12
  treatment: "Treat"
  target_residual_rating: 6
  acceptance_authority: "RMC"
  status: "In Treatment"
  linked_frameworks: ["TRMF", "CRMF"]
```

### 2.9 Issue / Finding

```yaml
issue:
  id: CAP-2026-0023
  source: "Internal Audit FY2026"
  source_reference: "IA-FY2026-Finding-23"
  description: "CMDB completeness 88% (target 95%)"
  severity: "Medium"
  owner_role: "Head of IT Operations"
  function_area: "TRMF"
  committed_date: "2026-09-30"
  progress_status: "In progress (40%)"
  linked_risks: []
  linked_controls: ["STD-AM-01.3.7.1"]
```

### 2.10 Exception

```yaml
exception:
  id: EXC-2026-001
  affected_document: "STD-AC-01"
  exception_type: "standard"
  description: "Legacy mainframe accounts cannot be disabled within 30 min..."
  compensating_control: "Detective monitoring with 1-hour alert; replacement project Q4 2026"
  approver_role: "CISO"
  start_date: "2026-04-01"
  end_date: "2027-03-31"
  status: "Active"
```

---

## 3. Cross-references — relationship objects

GRC platforms model relationships explicitly:

- `framework.contains.policy` (parent-child)
- `policy.contains.standard` (parent-child)
- `standard.contains.procedure` (parent-child)
- `procedure.populates.register` (operational)
- `policy.implements.clause` (mapped to authority)
- `risk.affects.framework` (taxonomy)
- `issue.relates_to.control` (finding)
- `exception.deviates_from.standard` (exception)

---

## 4. Extraction approach

For each v2 markdown document:
1. Parse the **metadata table** at the top → object identification + relationships
2. Parse the **shall statements** (or measurable requirements) → control statements
3. Parse the **schema** in registers → register field model
4. Parse the **worked example** rows → seed entries
5. Output structured data per the model above

Tooling options:
- Custom Python script using `python-markdown` or `mistune` to parse markdown into AST, then extract structured fields by section
- Markdown frontmatter (YAML at top of each file) extension to encode metadata in machine-readable form
- LLM-based extraction (compute-heavy but flexible)

---

## 5. Recommended sequence to load into a GRC platform

| Phase | Load |
|---|---|
| 1 | Authorities (Layer 0 + Layer 1) |
| 2 | Frameworks (Layer 2) |
| 3 | Policies (Layer 3) with framework relationships |
| 4 | Standards (Layer 4) with policy relationships and measurement criteria |
| 5 | Procedures (Layer 5) with standard relationships and step model |
| 6 | Plans with framework relationships and phase model |
| 7 | Registers with their schemas |
| 8 | Worked-example seed entries |
| 9 | Risks (REG-TR) with framework / control linkages |
| 10 | Issues / findings (REG-CAP, REG-NCA, REG-VUL) |
| 11 | Exceptions (REG-EXC) with affected-document linkages |
| 12 | Ongoing: register entries (operational data) |

---

## 6. Caveats

- **Object model varies per platform.** The model above is canonical; vendor-specific mappings will be needed.
- **Workflow logic is platform-specific** and should be re-implemented per the platform's workflow engine.
- **Permission model** (who can edit policies, who can attest controls, who can close exceptions) — needs platform configuration aligned to the federated GRC structure per [bank-profile.md](../_context/bank-profile.md).
- **Reporting and dashboards** typically build out post-load; v2 metric definitions in framework Section 10 are starting points.

---

## 7. Build / buy / SaaS considerations

| Approach | Trade-offs |
|---|---|
| Major GRC platform (Archer / ServiceNow GRC / OneTrust / MetricStream) | Full lifecycle support; expensive; integration effort substantial; provider lock-in concerns |
| Mid-tier (LogicGate, AuditBoard, ProcessUnity) | Focused functionality; lower cost; possibly less depth on some areas |
| Open-source (Eramba, Risk Cloud) | Lower licence cost; integration / maintenance effort higher |
| Custom-built on document repository + ticketing | Maximum flexibility; high custodial cost; not recommended for Tier-2 NCII bank |

GIBB selection criteria typically: regulator-recognised, support for federated GRC operating model, Malaysian / regional sensitivity (BNM, NACSA dialect), Shariah-overlay capability or extension, AI / cloud governance depth.

This is platform selection, not v2 content design. v2 content is platform-agnostic by intent.
