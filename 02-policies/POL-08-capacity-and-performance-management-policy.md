# POL-08 — Capacity and Performance Management Policy

| | |
|---|---|
| **Document ID** | POL-08 |
| **Layer** | Policy (Tier 1) |
| **Version** | 1.0 |
| **Owner** | Chief Information Officer |
| **Approver** | Risk Management Committee |
| **Classification** | Internal |
| **Effective** | [Effective] |
| **Next review** | Annual |
| **Parent framework(s)** | [TRMF](../01-frameworks/TRMF.md); secondary [BCMF](../01-frameworks/BCMF.md) |
| **RMiT clause(s)** | Section 10.29 (System Capacity Planning); 10.30 (Real-Time Performance Monitoring); 10.31 (Digital Services Resilience Enhancement); 10.32 (Critical System High Availability Requirements) |
| **COBIT objective(s)** | BAI04 Managed Availability and Capacity; DSS01 Managed Operations |
| **Practice standard(s)** | ITIL 4 Capacity and Performance Management practice; ISO/IEC 27002:2022 control 8.6 |

---

## 1. Purpose

To ensure GIBB technology services have sufficient capacity, perform within agreed service levels, and remain available for customers and operations — supporting the broader continuity expectations of [BCMF](../01-frameworks/BCMF.md) and the resilience expectations of RMiT 10.29–10.32.

## 2. Scope

All production technology services. Applications, infrastructure, cloud services, networks, customer-facing digital channels.

## 3. Definitions

| Term | Definition |
|---|---|
| **Capacity** | The total resource (compute, storage, network, transaction) available to a service. |
| **Demand forecast** | Projection of future capacity demand based on business growth, seasonality, and known initiatives. |
| **Performance baseline** | The measured normal performance against which deviation triggers investigation. |

## 4. Policy statements

### 4.1 Capacity planning

- **4.1.1** Critical services **shall** have a documented capacity plan covering current usage, forecast demand, and planned capacity additions. *(Implements RMiT 10.29; COBIT BAI04.)*
- **4.1.2** Capacity additions **shall** be planned to maintain agreed service levels during peak conditions and forecast growth.

### 4.2 Performance monitoring

- **4.2.1** Critical services **shall** be monitored in real time for performance against baseline. *(Implements RMiT 10.30.)*
- **4.2.2** Performance deviations **shall** trigger investigation per the operations support procedure.

### 4.3 Digital services resilience

- **4.3.1** Digital service capacity and resilience **shall** meet customer experience expectations during peak and degraded conditions. *(Implements RMiT 10.31.)*

### 4.4 Critical system high availability

- **4.4.1** Critical systems **shall** be designed for high availability per the requirements in RMiT 10.32 and the targets in [BCMF](../01-frameworks/BCMF.md).
- **4.4.2** High availability design includes redundancy, failover, and tested recovery.

### 4.5 Continuous improvement

- **4.5.1** Performance and capacity metrics **shall** be reviewed monthly with trend analysis and improvement actions tracked.

## 5. Roles and responsibilities

| Role | R | A | C | I |
|---|---|---|---|---|
| Risk Management Committee | | A | | |
| CIO | A | | | |
| Head of IT Operations | R | | C | |
| Service owners | R | | | I |

## 6. Exceptions

Per TRMF Section 12.

## 7. Enforcement

Per TRMF Section 12.

## 8. Related documents

- **Parent framework:** [TRMF](../01-frameworks/TRMF.md); [BCMF](../01-frameworks/BCMF.md)
- **Related policies:** [POL-14 Business Continuity Policy](POL-14-business-continuity-policy.md) (cross-reference); [POL-16](POL-16-operations-security-policy.md)

## 9. References

- BNM RMiT, 28 November 2025: Section 10.29–10.32
- COBIT 2019 — BAI04; DSS01
- ITIL 4 — Capacity and Performance Management
- ISO/IEC 27002:2022 — control 8.6

## 10. Document control

| Version | Date | Author | Reviewer | Approver | Change summary |
|---|---|---|---|---|---|
| 1.0 | [Effective] | CIO | RMC | RMC | Initial Effective version |
