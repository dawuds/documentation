# REG-MD — Master Data Register

| | |
|---|---|
| **Document ID** | REG-MD | **Owner** | CDO + CIO |
| **Cadence** | Continuous | **Parent framework** | [DGF](../01-frameworks/DGF.md) |

## Purpose
Authoritative inventory of GIBB master and reference data assets — single source of truth for the entities shared across multiple systems (customers, products, accounts, counterparties) and the codes / taxonomies that classify them.

## Schema
| Field | Description |
|---|---|
| `md_id` | `MD-NNN` |
| `master_data_type` | Customer / Product / Account / Counterparty / Branch / Employee / Reference codes |
| `system_of_record` | Authoritative system per type |
| `data_owner` | Role |
| `data_steward` | Role |
| `consuming_systems` | Multi reference |
| `change_process` | Documented procedure for changes |
| `change_approval_authority` | Role |
| `data_quality_score` | Per [STD-DG-01](../03-standards/STD-DG-01-data-quality-standard.md) |
| `shariah_relevant` | bool (Islamic product reference data) |
| `last_reconciliation` | date |
| `next_reconciliation` | date |

## Worked example
| md_id | type | system_of_record | owner | consuming | shariah | quality | status |
|---|---|---|---|---|---|---|---|
| MD-001 | Customer | Core banking — CIF module | Head of Customer Operations | All customer-facing + AML + analytics | Y | 99.2% | Active |
| MD-002 | Product (Islamic) | Product master system | Head of Product (Islamic) | Core banking; digital channels; reporting | Y (Shariah Committee approved) | 100% | Active |
| MD-003 | Account | Core banking — accounts module | Head of Operations | All transactional + statements + reporting | Y (Islamic + conventional) | 99.9% | Active |
| MD-004 | Country / currency / sukuk type codes | Reference data system | CDO | All systems consuming codes | Y (sukuk taxonomy) | 100% | Active |
| MD-005 | Branch | Branch master | Head of Branch Operations | All branch-aware systems | n/a | 100% | Active |
| MD-006 | Employee (HRIS authoritative) | Workday | CHRO | IDP federation; payroll; access control | n/a | 99.8% | Active |
| MD-007 | Counterparty (institutional / treasury) | Treasury system | Head of Treasury | Treasury + payments + risk | n/a | 99.5% | Active |

## Maintenance
- Quarterly reconciliation: each master data set re-reconciled across consuming systems for drift
- Material discrepancy triggers data quality investigation per [SOP-DG-02](../04-procedures/SOP-DG-02-data-quality-triage-sop.md)
- New master data domain registered before consumption begins

## Related documents
[STD-DG-01](../03-standards/STD-DG-01-data-quality-standard.md); [REG-DA](REG-DA-data-asset-register.md); [REG-DL](REG-DL-data-lineage-register.md); POL-DG-02 Master Data Management Policy (future)
