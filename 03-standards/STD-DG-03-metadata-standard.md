# STD-DG-03 — Metadata Standard

| | |
|---|---|
| **Document ID** | STD-DG-03 | **Version** | 1.0 |
| **Owner / Approver** | CDO / CDO |
| **Parent policy** | [POL-11](../02-policies/POL-11-data-classification-policy.md) | **Parent framework** | [DGF](../01-frameworks/DGF.md) |
| **Practice** | DAMA-DMBOK 2; ISO/IEC 11179 |

## 1. Purpose
Specify mandatory metadata for data assets at GIBB — business definitions, technical metadata, operational metadata.

## 2. Scope
All data assets registered in [REG-DA](../06-registers/REG-DA-data-asset-register.md).

## 3. Metadata categories

### 3.1 Business metadata
- Business name (recognisable by business owner)
- Business definition (1-2 sentence plain-language)
- Business owner role
- Business glossary terms applied
- Use cases
- Sensitivity classification per [POL-11](../02-policies/POL-11-data-classification-policy.md)

### 3.2 Technical metadata
- Physical data type (database, schema, table, column — or file structure)
- Source system / lineage origin
- Format (relational, JSON, document, binary)
- Schema reference (DDL, JSON schema, etc.)
- Volume indicator
- Update frequency

### 3.3 Operational metadata
- Owner role + steward role
- Quality score (per [STD-DG-01](STD-DG-01-data-quality-standard.md))
- Last quality assessment date
- Lineage status (documented / partial / none)
- Last access timestamp (for analytical use)
- Retention rule applied

### 3.4 Governance metadata
- Personal data flag (PDPA scope)
- Sensitive personal data flag
- Shariah-Confidential flag
- Cross-border flag
- AI training use flag
- ROPA reference (if personal data)

## 4. Capture and maintenance

| Activity | Owner | Cadence |
|---|---|---|
| Initial metadata capture | Data owner at asset registration | On registration |
| Business definition validation | Data steward + business owner | Annual |
| Technical metadata refresh | Data steward + IT | Quarterly automated where possible |
| Quality + lineage + access metrics | Auto-updated | Continuous |
| Governance flags | DPO / Shariah Compliance / DGF team | On material change |

## 5. Metadata storage
Centralised metadata catalogue (data catalogue platform); single source of truth for all metadata categories.

## 6. Exceptions
Per [POL-11](../02-policies/POL-11-data-classification-policy.md).

## 7. Related documents
[STD-DG-01](STD-DG-01-data-quality-standard.md); [STD-DG-02](STD-DG-02-data-retention-standard.md); [REG-DA](../06-registers/REG-DA-data-asset-register.md); [SOP-DG-01 Data Asset Onboarding SOP](../04-procedures/SOP-DG-01-data-asset-onboarding-sop.md)

## 8. References
DAMA-DMBOK 2; ISO/IEC 11179 (Metadata registries).

## 9. Document control
| Version | Date | Author | Approver | Change |
|---|---|---|---|---|
| 1.0 | [Effective] | CDO | CDO | Initial |
