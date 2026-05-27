# POL-15 — Physical and Environmental Security Policy

| | |
|---|---|
| **Document ID** | POL-15 |
| **Layer** | Policy (Tier 1) |
| **Version** | 1.0 |
| **Owner** | Head of Facilities + CISO (joint) |
| **Approver** | Risk Management Committee |
| **Classification** | Internal |
| **Effective** | [Effective] |
| **Next review** | Annual |
| **Parent framework(s)** | [TRMF](../01-frameworks/TRMF.md); secondary [BCMF](../01-frameworks/BCMF.md) |
| **RMiT clause(s)** | Section 10.26 (Production Data Centre Physical Security); 10.24–10.28 (Data Centre Resilience broadly); 10.27 (DC Operations Control Procedures) |
| **COBIT objective(s)** | DSS05 Managed Security Services (physical aspect); BAI09 Managed Assets |
| **Practice standard(s)** | ISO/IEC 27002:2022 controls 7.1–7.14 (physical and environmental); ISO/IEC 27037 (where physical evidence is involved) |

---

## 1. Purpose

To protect GIBB information assets from physical and environmental threats — unauthorised physical access, theft, tampering, natural events, environmental excursion, and disruption to supporting utilities.

## 2. Scope

All GIBB premises and any third-party premises hosting GIBB information assets, including data centres, branches, head office, disaster recovery sites, and remote-work locations.

## 3. Definitions

| Term | Definition |
|---|---|
| **Production data centre** | Primary or secondary data centre hosting production-supporting systems. |
| **Secure area** | A defined physical area with controlled access (data centre, network closet, secure work area, branch vault). |
| **Visitor** | Any non-employee accessing GIBB premises. |

## 4. Policy statements

### 4.1 Physical perimeters

- **4.1.1** Physical security perimeters **shall** be defined for premises hosting information assets, with controls proportionate to the sensitivity of assets within. *(Implements ISO/IEC 27002:2022 controls 7.1, 7.2.)*

### 4.2 Physical access

- **4.2.1** Physical access to data centres, network closets, and secure areas **shall** be authorised, logged, and reviewed quarterly. *(Implements ISO/IEC 27002:2022 control 7.3; RMiT 10.26.)*

### 4.3 Visitors

- **4.3.1** Visitors to restricted areas **shall** be authorised in advance, escorted at all times, identified by visible visitor identification, and logged.

### 4.4 Equipment

- **4.4.1** Equipment **shall** be sited and protected to reduce risk from environmental threats, hazards, and unauthorised access. Cabling **shall** be protected from interception and damage. *(Implements ISO/IEC 27002:2022 controls 7.5, 7.8, 7.12.)*

### 4.5 Clear desk and clear screen

- **4.5.1** A clear desk and clear screen practice **shall** apply to information classified Confidential or higher. *(Implements ISO/IEC 27002:2022 control 7.7.)*

### 4.6 Environmental controls

- **4.6.1** Critical premises **shall** have monitored protection against fire, flood, environmental excursion, and power failure, with redundant utilities and tested failover. *(Implements RMiT 10.24, 10.25, 10.26; ISO/IEC 27002:2022 controls 7.5, 7.11.)*

### 4.7 Secure disposal

- **4.7.1** Equipment containing information **shall** be securely sanitised before disposal or re-use per [POL-09 IT Asset Management Policy](POL-09-it-asset-management-policy.md) and NIST SP 800-88 Rev. 1. *(Implements ISO/IEC 27002:2022 controls 7.10, 7.14.)*

### 4.8 Remote work

- **4.8.1** Personnel working remotely **shall** apply equivalent physical and environmental safeguards proportionate to the classification of information being handled.

## 5. Roles and responsibilities

| Role | R | A | C | I |
|---|---|---|---|---|
| Risk Management Committee | | A | | |
| Head of Facilities | A (premises) | | C | |
| CISO | | A (information asset protection) | C | |
| Head of IT Operations | R (data centres) | | C | |

## 6. Exceptions

Per TRMF Section 12.

## 7. Enforcement

Per TRMF Section 12.

## 8. Related documents

- **Parent framework:** [TRMF](../01-frameworks/TRMF.md); [BCMF](../01-frameworks/BCMF.md)
- **Related policies:** [POL-09 IT Asset Management](POL-09-it-asset-management-policy.md); [POL-14 Business Continuity Policy](POL-14-business-continuity-policy.md)

## 9. References

- BNM RMiT, 28 November 2025: Section 10.24–10.28
- COBIT 2019 — DSS05; BAI09
- ISO/IEC 27002:2022 — controls 7.1–7.14
- NIST SP 800-88 Rev. 1 — Media Sanitization

## 10. Document control

| Version | Date | Author | Reviewer | Approver | Change summary |
|---|---|---|---|---|---|
| 1.0 | [Effective] | Head of Facilities + CISO | RMC | RMC | Initial Effective version |
