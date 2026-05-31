# POL-CI-02 — Customer Consent and Disclosure Policy

| | |
|---|---|
| **Document ID** | POL-CI-02 |
| **Layer** | Policy (Tier 1) |
| **Version** | 1.0 |
| **Owner** | Data Protection Officer + Chief Compliance Officer (joint) |
| **Approver** | Risk Management Committee |
| **Classification** | Internal |
| **Effective** | [Effective] |
| **Next review** | Annual + on PDPA, MCIPD or BNM permitted-disclosure change |
| **Parent framework(s)** | [CIMF](../01-frameworks/CIMF.md) |
| **RMiT clause(s)** | Section 12 (Digital Services); Section 13 (External Party Reliance — disclosure of customer data to TPSPs) |
| **COBIT objective(s)** | APO14 Managed Data; DSS06 Managed Business Process Controls |
| **Practice standard(s)** | ISO/IEC 27701:2019 (PIMS); ISO/IEC 29184:2020 (Online privacy notices and consent) |
| **Additional anchors** | BNM Management of Customer Information and Permitted Disclosures (MCIPD), particularly Appendices 1 (Permitted Disclosures) and 4 (Customer Consent); Personal Data Protection Act 2010 (PDPA), particularly Sections 6, 8, 38–44; Financial Services Act 2013 Section 134 (banking secrecy); Islamic Financial Services Act 2013 Section 146; BNM Shariah Governance Framework (Shariah-confidential customer data) |

---

## 1. Purpose

To define how GIBB obtains, records, manages, and honours customer consent, and how GIBB discloses customer information to permitted third parties — within the boundaries of MCIPD, PDPA 2010, FSA 2013 Section 134 / IFSA 2013 Section 146 (banking secrecy), and Shariah governance obligations. Sibling of [POL-CI-01](POL-CI-01-customer-data-protection-policy.md): POL-CI-01 governs the *data*; POL-CI-02 governs the *customer choice and disclosure boundary*.

## 2. Scope

All customer-data processing requiring consent under PDPA; all disclosures of customer information outside GIBB (to TPSPs, regulators, courts, law enforcement, group entities, marketing partners); all consent capture mechanisms (digital, paper, voice).

## 3. Policy statements

### 3.1 Lawful basis and consent

- **3.1.1** Customer data shall be processed only on a documented lawful basis under PDPA Section 6 — consent, contractual necessity, legal obligation, vital interests, or legitimate interest (where balanced against customer rights).
- **3.1.2** Where consent is the basis, it shall be **freely given, specific, informed, and unambiguous** — captured in plain Bahasa Malaysia and English, with the purpose stated separately from terms of service, and recorded in a tamper-evident system. *(Aligned with ISO/IEC 29184:2020.)*
- **3.1.3** Consent for sensitive personal data (PDPA Section 40) shall be **explicit** and separate from general consent.
- **3.1.4** Consent shall not be bundled with contractual acceptance unless the processing is strictly necessary for the contract.

### 3.2 Consent for direct marketing

- **3.2.1** Direct marketing consent shall be **opt-in**, captured separately from product onboarding, and capable of selective withdrawal by channel (email, SMS, push, voice).
- **3.2.2** Every direct marketing communication shall carry a one-click opt-out per PDPA Section 43.

### 3.3 Customer rights

- **3.3.1** GIBB shall honour the customer rights set out in PDPA Sections 30–38: access, correction, withdrawal of consent, limitation, and (for direct marketing) cessation. The operating procedure and SLAs are in [REG-DSR](../06-registers/REG-DSR-data-subject-request-register.md).
- **3.3.2** Acknowledgement: within 7 working days. Substantive response: within 21 working days of acknowledgement, extendable by a further 14 working days with a written explanation to the customer.

### 3.4 Permitted disclosures (banking secrecy)

- **3.4.1** Customer information governed by FSA 2013 Section 134 / IFSA 2013 Section 146 shall not be disclosed outside GIBB except where a **permitted disclosure** under the relevant Schedule applies, or written customer consent has been obtained for that disclosure.
- **3.4.2** Disclosure to **TPSPs** for the purpose of service delivery shall be permitted only where the TPSP is governed by an agreement compliant with [POL-19 Supplier Security Policy](POL-19-supplier-security-policy.md) and where MCIPD Appendix 1 conditions are met.
- **3.4.3** Disclosure to **regulators, courts, and law enforcement** shall be discharged by the Chief Compliance Officer, with legal review by General Counsel for non-routine requests. Production-order or warrant disclosures shall be logged in [REG-DIS](../06-registers/REG-DIS-disclosure-register.md).
- **3.4.4** Disclosure to **group entities** shall be permitted only where the customer has been notified of intra-group sharing at onboarding and where the receiving entity is bound by equivalent confidentiality and security obligations.

### 3.5 Cross-border transfer

- **3.5.1** Cross-border transfer of personal data shall comply with PDPA Section 129 — to whitelisted jurisdictions or under contractual safeguards equivalent to PDPA protection.
- **3.5.2** Cross-border disclosures shall be additionally logged in [REG-DIS](../06-registers/REG-DIS-disclosure-register.md) with the receiving-jurisdiction safeguard cited.

### 3.6 Withdrawal and revocation

- **3.6.1** Customers shall be able to withdraw consent at any time through a documented self-service channel, in-branch, or by writing to the DPO.
- **3.6.2** Withdrawal shall be effective within 5 working days; downstream marketing systems shall suppress within that window.
- **3.6.3** Withdrawal does not extinguish processing on other lawful bases (e.g., regulatory record-keeping, fraud prevention) — the customer shall be informed of any continued processing and its basis.

### 3.7 Consent records and audit

- **3.7.1** The bank shall maintain auditable records of consent including: capture timestamp, capture channel, version of the notice presented, the exact text presented, and any subsequent modifications or withdrawals.
- **3.7.2** Consent records shall be retained for the lifetime of the customer relationship plus the applicable statutory retention period.

### 3.8 Shariah-confidential customer information

- **3.8.1** Customer information identified as Shariah-confidential (e.g., zakat declarations, hibah arrangements, Shariah advisory correspondence) shall not be used outside its original Shariah-compliance purpose without separate, explicit consent.
- **3.8.2** Internal access to Shariah-confidential customer data shall be limited to roles with a documented Shariah-related need, audited per the Shariah Committee's directions.

## 4. Roles and responsibilities

| Role | R | A | C | I |
|---|---|---|---|---|
| Risk Management Committee | | A | | I |
| Data Protection Officer | A | | C | |
| Chief Compliance Officer | | A (joint) | C | |
| Head of Customer Experience / Channels | R | | C | I |
| CISO | | | C | I |
| General Counsel | | | C (non-routine disclosures) | I |
| Shariah Committee | | | C (Shariah-confidential) | I |

## 5. Exceptions

Per [POL-04 Section 12](POL-04-information-security-policy.md). Exceptions affecting customer rights require RMC approval. Exceptions affecting banking secrecy require Board approval.

## 6. Enforcement

Per [POL-04 Section 13](POL-04-information-security-policy.md). Customer-rights breach or unlawful disclosure triggers PDPA-incident handling under [POL-13](POL-13-incident-management-policy.md) and may trigger customer notification under [SOP-CI-02](../04-procedures/SOP-CI-02-customer-breach-notification-sop.md).

## 7. Related documents

[POL-CI-01](POL-CI-01-customer-data-protection-policy.md); [POL-13](POL-13-incident-management-policy.md); [POL-19](POL-19-supplier-security-policy.md); [REG-DSR](../06-registers/REG-DSR-data-subject-request-register.md); [REG-DIS](../06-registers/REG-DIS-disclosure-register.md); [REG-ROPA](../06-registers/REG-ROPA-records-of-processing-activity.md); [SOP-CI-02](../04-procedures/SOP-CI-02-customer-breach-notification-sop.md).

## 8. References

PDPA 2010; FSA 2013 Section 134; IFSA 2013 Section 146; BNM MCIPD Appendices 1, 4; BNM Shariah Governance Framework; ISO/IEC 27701:2019; ISO/IEC 29184:2020. [Regulatory Mapping Reference](../_context/framework-stack.md).

## 9. Document control

| Version | Date | Author | Reviewer | Approver | Change summary |
|---|---|---|---|---|---|
| 1.0 | 2026-05-30 | DPO + CCO | Risk Management Committee | Risk Management Committee | Initial version. Created to close CIMF / REG-ROPA cross-reference gap identified in v2 multi-agent review. |
