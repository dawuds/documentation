# Physical & Environmental Security Policy

| | |
|---|---|
| **Document ID** | POL-10 |
| **Layer** | Policy (Tier 1) |
| **Owner** | Head of Facilities (joint with CISO) |
| **Approver** | Risk Management Committee |
| **Classification** | Internal |
| **Version** | 1.0 |
| **Effective date** | 2026-02-01 |
| **Next review** | 2027-02-01 |
| **ISO/IEC 27002:2022 controls** | 7.1–7.14 (physical and environmental controls) |
| **BNM RMiT (28 Nov 2025)** | §10.26 (Production Data Centre Physical Security); §10.24–10.28 (Data Centre Resilience more broadly) |

> Skeleton policy.

---

## 1. Purpose

To define controls protecting information assets from physical and environmental threats — including unauthorised physical access, theft, environmental damage, and disruption to supporting utilities.

## 2. Scope

All General Bank premises and any third-party premises hosting General Bank information assets, including data centres, branches, head office, disaster recovery sites, and remote-work locations.

## 3. Policy statements

### 3.1 Physical perimeter and entry

- **3.1.1** Physical security perimeters shall be defined for premises hosting information assets, with controls proportionate to the sensitivity of the assets within. *(Implements ISO/IEC 27002:2022 controls 7.1, 7.2.)*
- **3.1.2** Physical access to data centres, secure rooms, and restricted areas shall be authorised, logged, and reviewed quarterly. *(Implements ISO/IEC 27002:2022 control 7.3.)*

### 3.2 Visitor management

- **3.2.1** Visitors to restricted areas shall be authorised in advance, escorted at all times, identified by visible visitor identification, and logged.

### 3.3 Equipment and cabling

- **3.3.1** Equipment shall be sited and protected to reduce risk from environmental threats, hazards, and unauthorised access. Power and communications cabling shall be protected from interception and damage. *(Implements ISO/IEC 27002:2022 controls 7.5, 7.8, 7.12.)*

### 3.4 Working in secure areas

- **3.4.1** Working in secure areas shall be subject to specific controls including restrictions on recording devices, supervision of contractors, and removal of equipment.

### 3.5 Clear desk and clear screen

- **3.5.1** A clear desk and clear screen practice shall apply to information classified Confidential or higher. *(Implements ISO/IEC 27002:2022 control 7.7.)*

### 3.6 Environmental and utilities

- **3.6.1** Critical premises shall have monitored protection against fire, flood, environmental excursion, and power failure, with redundant utilities and tested failover. *(Implements ISO/IEC 27002:2022 controls 7.5, 7.11; BNM RMiT §10.24 (DC Resilience Objectives); §10.25 (DC Redundancy); §10.26 (DC Physical Security).)*

### 3.7 Secure disposal and re-use

- **3.7.1** Equipment containing information shall be securely sanitised before disposal or re-use, in accordance with media sanitisation standards aligned with NIST SP 800-88 Rev. 1. *(Implements ISO/IEC 27002:2022 controls 7.10, 7.14.)*

### 3.8 Remote work

- **3.8.1** Personnel working remotely shall apply equivalent physical and environmental safeguards proportionate to the classification of information being handled, per the Remote Work Standard.

## 4. Roles and responsibilities

| Role | R | A | C | I |
|---|---|---|---|---|
| Risk Management Committee | | A | | I |
| Head of Facilities | A | | C | |
| CISO | | | C | I |
| Head of IT Operations (for data centres) | R | | C | I |

## 5. Exceptions

Per [POL-00](00-information-security-policy.md).

## 6. Enforcement

Per [POL-00](00-information-security-policy.md).

## 7. Related documents

[POL-00](00-information-security-policy.md), [POL-02](02-access-control-policy.md), [POL-03](03-asset-management-policy.md), [POL-09](09-business-continuity-policy.md).

## 8. References

ISO/IEC 27002:2022 — controls 7.1–7.14. NIST SP 800-88 Rev. 1 (Media Sanitization). BNM RMiT (28 Nov 2025) §10.24–10.28 (Data Centre Resilience). [Regulatory Mapping Reference](../00-foundations/regulatory-mapping-reference.md).

## 9. Document control

| Version | Date | Author | Reviewer | Approver | Change summary |
|---|---|---|---|---|---|
| 1.0 | 2026-01-15 | Head of Facilities + CISO | Risk Management Committee | Risk Management Committee | Initial Effective version (skeleton). |
