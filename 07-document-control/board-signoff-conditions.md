# Board sign-off conditions — pre-approval punch list

The v2 suite is **drafted in full** but **not yet Effective**. This document is the punch list of conditions the Board (and RMC, BAC, function heads) must satisfy before the suite goes Effective.

| | |
|---|---|
| **Document ID** | DC-002 |
| **Owner** | Company Secretary (consolidates); CRO + CISO (operates) |
| **Approver** | Board of Directors (final closure of the punch list at the meeting that ratifies the suite) |
| **Classification** | Internal — restricted |
| **Version** | 1.0 |
| **Effective date** | Concurrent with the Board's adoption decision |
| **Implements** | Board governance for ISMS / BCMS / AIMS adoption; ISO 27001 Clause 5.2; ISO 22301 Clause 5.2; ISO 42001 Clause 5.2 |

---

## Why this document exists

The v2 multi-agent review (Board member perspective) gave a **conditional approve** — would not block the suite, but attached four explicit conditions before signing the Information Security Policy (POL-04) and Technology Risk Appetite Statement (POL-03). The CIO review added further pre-adoption renegotiation points. This document consolidates them so the Board can close them in one pass.

Without resolving these, several documents remain factually incomplete (placeholder dates, illustrative numbers without ratification, undated approvals).

---

## Condition register

| # | Condition | Origin | Closes when | Owner | Status |
|---|---|---|---|---|---|
| **C-01** | Replace all `[Effective]` and `[Effective date]` placeholders in approved documents with real dates, and ratify an annual review schedule (which document is due for review in which quarter of which year). | Board review | Master document register all rows have real dates; review calendar published in [07-document-control/](.) | ISMS Manager + CISO | Open |
| **C-02** | Complete the **Board Reporting and Escalation Annex** ([00-architecture/board-reporting-and-escalation-annex.md](../00-architecture/board-reporting-and-escalation-annex.md)) — verify the Chair-notification mechanics (primary, secondary, out-of-band) and the contact list; rehearse at next tabletop. | Board review + IT Gov | Annex Section 3.2 contact list signed off by Board Chair; Section 5 maintenance in place; tested in tabletop | Company Secretary + CISO | **Drafted (this build); awaits contact-list sign-off** |
| **C-03** | **POL-03 Section 4.2 quantitative tolerances** — ratify the numbers as Board appetite or strike "illustrative" and re-issue. The Board cannot approve a policy that calls its own numbers illustrative. | Board review | POL-03 Section 4.2 status changes from "illustrative" to "ratified by Board on YYYY-MM-DD" | CRO + Board | Open |
| **C-04** | **CCO clock attestation** — CCO confirms in writing, at sign-off and at every RMC meeting thereafter, the current authoritative BNM notification clock (under Operational Risk Reporting PD Part C) and the NACSA clock. Format: standing single-page attestation tabled at every RMC. | Board review | First attestation tabled at the RMC meeting following sign-off; cadence established | CCO | Open |
| **C-05** | **Materiality threshold** ratification — confirm or adjust the materiality criteria added to [POL-04 Section 3](../02-policies/POL-04-information-security-policy.md) (customer-impact / operational-financial / regulatory-reputational). The Board adopting POL-04 implicitly ratifies these criteria; explicit ratification in the Board minute is the recommended path. | Board review + materiality update | Board minute records explicit ratification | CISO + CRO + Board | **Drafted; awaits Board ratification** |
| **C-06** | **Approval-authority articulation** ([POL-04 Section 7.1](../02-policies/POL-04-information-security-policy.md)) — confirm the strategic/operational split (Board / RMC / function head). | IT Gov review | Confirmed at sign-off | RMC + Board | **Drafted; awaits ratification** |
| **C-07** | **Toolchain mapping** — every SOP that references a generic capability (IGA / PAM / SOAR / CSPM / EDR / SIEM / IDP / secrets platform / ticketing) must be mapped to the actual GIBB-side tool with named owner before the SOP goes Effective. | CIO review | A toolchain register (or annex to [04-procedures/README.md](../04-procedures/README.md)) is populated and reviewed by Head of IT Ops + CISO | Head of IT Ops + CISO | **Banner drafted; mapping pending** |
| **C-08** | **Role-chart mapping** — every named role in the suite (Head of IAM, Head of SOC, Head of Cloud, AI Governance Committee, Shariah Committee liaison, Chief Data Officer, etc.) must exist in the GIBB org chart with named incumbents or be retitled. | CIO review | Role-to-incumbent table maintained by CHRO + Company Secretary | CHRO + CISO | Open |
| **C-09** | **Legacy core carve-outs** — every legacy system that cannot meet [STD-CM-01 Section 3.4](../03-standards/STD-CM-01-change-management-standard.md) and [STD-CR-01 Section 3.5](../03-standards/STD-CR-01-cryptographic-standard.md) must be registered in [REG-EXC](../06-registers/REG-EXC-exception-register.md) with compensating controls before either standard goes Effective. | CIO review + Tier 3 update | REG-EXC populated for known legacy systems; sign-off by CISO + CIO | CIO + CISO | **Standards updated; REG-EXC entries pending** |
| **C-10** | **Change SLA renegotiation** — Board / CIO to confirm whether to keep STD-CM-01 Section 3.2 SLAs as drafted or compress per the adoption note. | CIO review + Tier 3 update | Decision recorded in [REG-CHG](../06-registers/REG-CHG-change-register.md) maintenance section; STD-CM-01 Section 3.2 footnote retained or removed | CIO + CISO | **Adoption note in document; decision pending** |
| **C-11** | **CSPM SLA model** — confirm business-hours-hard vs 24×7-with-SOAR auto-remediation per the adoption note in [SOP-CL-02](../04-procedures/SOP-CL-02-cspm-operations-sop.md). | CIO review + Tier 3 update | Decision recorded in SOP-CL-02 maintenance section | CISO + Head of Cloud | **Adoption note in document; decision pending** |
| **C-12** | **Documentation FTE budget** — Board / CFO to acknowledge the ~3 FTE-year ongoing documentation cost per [_learning/documentation-maintenance-cost.md](../_learning/documentation-maintenance-cost.md) and either fund it or instruct scope reduction. | CIO review + Tier 3 update | Resourcing decision recorded in RMC minute | CFO + CIO + CISO | **Cost paper drafted; Board decision pending** |
| **C-13** | **Initial REG-GAP population** — complete the baseline RMiT (28 Nov 2025) gap analysis with all applicable clauses tagged Compliant / Partial / Non-compliant / Pending, with remediation plans for non-Compliant. | GRC review | [REG-GAP](../06-registers/REG-GAP-rmit-gap-analysis-register.md) fully populated; CRO + CCO sign-off | 2nd-line Tech Risk + CCO | Open (template in place) |
| **C-14** | **Initial REG-SOA population** — confirm SoA reflects current implementation; rationalise the 6 controls flagged as N during v1; document remaining justification. | ISO 27001 cert path | REG-SOA reviewed by CISO + external auditor pre-cert | CISO | Open (template in place) |
| **C-15** | **Initial REG-OBJ population** — ratify FY2026 objectives at the Management Review and the RMC; remove "illustrative" tag. | ISO 27001 Cl. 6.2 | REG-OBJ entries tagged "ratified" with RMC date | CISO + RMC | Open (template + illustrative entries in place) |
| **C-16** | **Internal Audit Plan (PLN-08) ratification by BAC** — the Audit Universe, 3-year plan, and FY2026 schedule must be ratified by the Board Audit Committee. | RMiT Section 13 | BAC minute records ratification | Chief Internal Auditor + BAC | Open |
| **C-17** | **First Management Review held** ([REG-MR](../06-registers/REG-MR-management-review-register.md)) — within 90 days of suite adoption, conduct the combined ISMS/BCMS/AIMS Management Review covering all Clause 9.3.2 inputs. | ISO 27001/22301/42001 Cl. 9.3 | First entry in REG-MR with full Clause 9.3.3 outputs | CISO + COO + CDO via CRO | Open |
| **C-18** | **Cyber drill scheduled** — the FY2026 mandatory annual cyber drill per RMiT 11.16 is scheduled, Board observation arranged, and tracked in [REG-DRL](../06-registers/REG-DRL-cyber-drill-register.md). | RMiT 11.16 | REG-DRL entry; Board calendar holds date | CISO + CEO | Open |

---

## Maintenance

- This punch list is a **standing item** at every RMC meeting until all conditions are closed.
- Closed conditions remain in the table with a closure date; they are not deleted.
- Where a condition is materially adjusted in scope, the change is recorded in the document control row below.
- The Board makes the **final closure decision** at the meeting that ratifies the suite — i.e., the Board can decide to accept residual open items as known limitations rather than block adoption, provided the residual items are individually documented and risk-rated.

## Related documents

- [POL-04 Information Security Policy](../02-policies/POL-04-information-security-policy.md) (the policy whose Board adoption this punch list gates)
- [POL-03 Technology Risk Appetite Statement](../02-policies/POL-03-technology-risk-appetite-statement.md)
- [Board Reporting and Escalation Annex](../00-architecture/board-reporting-and-escalation-annex.md)
- [_learning/documentation-maintenance-cost.md](../_learning/documentation-maintenance-cost.md)
- [PLN-08 Internal Audit Plan](../05-plans/PLN-08-internal-audit-plan.md)

## Document control

| Version | Date | Author | Reviewer | Approver | Change summary |
|---|---|---|---|---|---|
| 1.0 | 2026-05-30 | Company Secretary + CISO + CRO | RMC | Pending Board | Initial consolidation. Captures Board sign-off conditions (C-01 to C-06), CIO renegotiation points (C-07 to C-12), and operating prerequisites (C-13 to C-18) identified in v2 multi-agent review. |
