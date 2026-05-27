# SOP-CR-03 — Forensic Evidence Handling SOP

| | |
|---|---|
| **Document ID** | SOP-CR-03 | **Version** | 1.0 |
| **Owner / Approver** | Head of SOC + CISO |
| **Parent policy** | [POL-13 §4.5](../02-policies/POL-13-incident-management-policy.md) | **Parent framework** | [CRMF](../01-frameworks/CRMF.md) |
| **Practice** | ISO/IEC 27037:2012 (Digital evidence) |

## 1. Purpose
Operationalise forensic evidence collection, preservation, and chain-of-custody for incidents potentially leading to legal / regulatory / disciplinary proceedings.

## 2. Trigger
Incident classified SEV-1 / SEV-2 with potential legal or regulatory consequence; incident involving suspected criminal activity; insider investigation; NACSA examination requiring evidence.

## 3. Procedure

### Phase 1 — Engagement
| # | Actor | Action | Output |
|---|---|---|---|
| 1 | Incident Commander | Determine forensic engagement scope; identify forensic lead | Engagement decision |
| 2 | Forensic Lead | Engage; review scope with General Counsel | Engagement plan |
| 3 | Forensic Lead | Notify General Counsel of evidence handling regime applied | Counsel notification |

### Phase 2 — Identification
| # | Actor | Action | Output |
|---|---|---|---|
| 4 | Forensic Lead + SOC | Identify all evidence sources — endpoint, network, application, cloud, physical | Evidence inventory |
| 5 | Forensic Lead | Prioritise volatile evidence (memory, network state, ephemeral logs) | Priority list |

### Phase 3 — Collection
| # | Actor | Action | Output |
|---|---|---|---|
| 6 | Forensic technician | Collect per priority — volatile first; documented method | Evidence with chain-of-custody label |
| 7 | Forensic technician | Hash each evidence artefact at collection (SHA-256 minimum) | Hash record |
| 8 | Forensic technician | Sign chain-of-custody form for each artefact | CoC form |

### Phase 4 — Preservation
| # | Actor | Action | Output |
|---|---|---|---|
| 9 | Forensic Lead | Store originals in secure forensic safe / encrypted forensic storage | Storage location recorded |
| 10 | Forensic technician | Work only on forensic copies; never original | Working copies created with hash verification |

### Phase 5 — Analysis
| # | Actor | Action | Output |
|---|---|---|---|
| 11 | Forensic analyst | Conduct analysis on working copy | Analysis findings |
| 12 | Forensic Lead | Document method and findings; verify hash integrity | Analysis report |

### Phase 6 — Reporting / handover
| # | Actor | Action | Output |
|---|---|---|---|
| 13 | Forensic Lead | Provide report to Incident Commander, General Counsel, CCO (for regulator submission if applicable) | Report distributed |
| 14 | Forensic Lead | Handover to law enforcement (if applicable) per General Counsel direction; chain-of-custody transferred | Handover record |

### Phase 7 — Closure
| # | Actor | Action | Output |
|---|---|---|---|
| 15 | Forensic Lead | Retain evidence per General Counsel direction (typically until close of any legal matter) | Retention record |
| 16 | Forensic Lead | Destroy at end of retention with certificate | Destruction certificate |

## 4. Chain-of-custody requirements
- Every evidence artefact: identification, collection date/time, collector, transfer points, storage location, hash verification at each transfer
- No gap in custody; documented signature for every transfer
- Forensic safe access dual-controlled

## 5. External forensic engagement
Material incidents may require external forensic specialists. Engagement per [TPRMF](../01-frameworks/TPRMF.md); pre-approved forensic retainers maintained by CISO.

## 6. Evidence retention
Per [STD-CI-02](../03-standards/STD-CI-02-customer-data-retention-standard.md) for customer-data-related evidence; per General Counsel for legal-hold evidence.

## 7. Document control
| Version | Date | Author | Approver | Change |
|---|---|---|---|---|
| 1.0 | [Effective] | Head of SOC + CISO | CISO | Initial |
