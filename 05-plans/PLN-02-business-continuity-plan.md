# PLN-02 — Business Continuity Plan

| | |
|---|---|
| **Document ID** | PLN-02 |
| **Layer** | Plan |
| **Version** | 1.0 |
| **Owner** | Chief Operating Officer |
| **Approver** | Risk Management Committee |
| **Classification** | Internal — restricted |
| **Effective** | [Effective] |
| **Next review** | Annual + post-disruption |
| **Parent framework(s)** | [BCMF](../01-frameworks/BCMF.md) |
| **Parent policy** | [POL-14](../02-policies/POL-14-business-continuity-policy.md) |
| **RMiT clause(s)** | Section 10.24–10.45 |
| **Aligned with** | ISO/IEC 22301:2019; BNM BCM Policy Document |

> **Distribution.** Internal — restricted. On-call card extracted from Section 4 distributed to BC team via secure on-call platform. Full plan distribution: COO, CEO, CFO, CIO, CISO, CRO, Head of IT Ops, Head of Corp Comms, RMC members.

---

## 1. Purpose

To define how GIBB sustains critical business services through disruption. Implements [POL-14 Business Continuity Policy](../02-policies/POL-14-business-continuity-policy.md) and operationalises the BCMF lifecycle (Section 8 of BCMF: BIA → Strategy → Plans → Test → Maintain).

## 2. Scope

All critical business services as identified in [REG-BIA Business Impact Analysis Register](../06-registers/REG-BIA-business-impact-analysis-register.md). Disruption causes: technology failure (including cyber-originated), third-party failure, environmental, pandemic, workforce.

**Out of scope.** Pure security-incident response (covered by [PLN-01 IRP](PLN-01-incident-response-plan.md)). BC activation arising from a cyber incident is coordinated jointly via the IRP and this BCP.

## 3. Activation

| Trigger | Activation authority | Channel |
|---|---|---|
| Critical-service outage exceeding 50% of MTPD or trending to MTPD | COO | Crisis call + secure messaging |
| Data centre incident affecting primary site | COO + Head of IT Operations | Secure messaging |
| Cyber-induced disruption per [PLN-01 Section 5.5](PLN-01-incident-response-plan.md) | CISO + COO (joint) | IRP bridge + BC channels |
| Pandemic or material workforce disruption | COO + CHRO | Per Pandemic Plan PLN-06 |
| External event (environmental, civil) with material operational impact | COO | Crisis management committee |

Activation creates: (a) BC log entry in [REG-BCT BC Test Outcomes Register](../06-registers/REG-BCT-bc-test-outcomes-register.md) (separate event register on real activation), (b) assigned BC Lead, (c) crisis communications channel opened.

## 4. Roles and contacts

| Role | Default holder | Alternate | Out-of-band contact |
|---|---|---|---|
| **BC Lead** | COO | Deputy COO | Mobile + on-call card |
| **IT Recovery Lead** | Head of IT Operations | Deputy | Mobile + on-call card |
| **Cyber Liaison** (if cyber-induced) | CISO | Deputy CISO | Per IRP |
| **Communications Lead** | Head of Corporate Communications | Deputy | Mobile + email |
| **Customer Operations Lead** | Head of Customer Operations | Deputy | Mobile + email |
| **Treasury / Settlement Lead** (if affecting Treasury) | Head of Treasury Ops | Deputy | Mobile + secure channel |
| **Shariah Liaison** (if affecting Shariah-compliant product services) | Head of Shariah Compliance | Shariah Committee Chair | Per Shariah Committee channels |
| **CEO** | CEO | CRO | Mobile + secure channel |
| **Board contact** | Board Chair | Board Risk Committee Chair | Via Company Secretary |

Out-of-band channels documented on physical on-call cards held by named individuals (not stored solely in systems that may be impacted).

## 5. Response phases

### 5.1 Activation and stand-up

- BC Lead confirms activation criteria met.
- Convene BC bridge (separate from IR bridge if both active).
- Assign roles per Section 4.
- Open Communications channel.
- Notify CEO and (for material disruptions) Board Chair via Company Secretary.

### 5.2 Damage assessment

- IT Recovery Lead assesses ICT impact.
- Service owners assess business impact per service.
- Confirm which critical services are affected and projected duration.
- Compare against MTPD per service from BIA.

### 5.3 Continuity strategy execution

- Activate alternate-site failover for affected IT services per DRP (PLN-03 per service).
- Invoke alternate-supplier arrangements for affected third-party services per TPRMF.
- Deploy manual workarounds where automated continuity is insufficient.
- For Shariah-compliant services: confirm continuity strategy preserves Shariah compliance (no riba / gharar introduced through workaround).

### 5.4 Customer and stakeholder communication

- Communications Lead executes customer communication per the Crisis Communications Plan (PLN-04, future).
- Regulator notification per [POL-13 Section 4.4](../02-policies/POL-13-incident-management-policy.md) (BNM via RMiT 11.18) and BNM BCM PD where applicable.

### 5.5 Recovery to normal

- Phased return to primary infrastructure / supplier / process.
- Validate recovered services meet operational quality before declaring full recovery.
- Enhanced monitoring period before declaring incident closed.

### 5.6 Post-event review

- Within 15 working days of stand-down: full review.
- Lessons captured in [REG-BCT BC Test Outcomes Register](../06-registers/REG-BCT-bc-test-outcomes-register.md) (real-event entries flagged distinctly from test entries).
- Updates to BIA, DRPs, this BCP as warranted.

## 6. Communication

| Audience | Trigger | Channel | Owner |
|---|---|---|---|
| Internal response team | Activation | BC bridge + secure messaging | BC Lead |
| Executive team | Material activation | Direct call | BC Lead |
| Board Chair | Material activation | Via Company Secretary | CEO |
| Risk Management Committee | Activation | Email brief + bridge invite | COO |
| All staff (if action required) | If staff action required | Internal channels | Communications Lead |
| Customers | Per impact and per regulatory expectations | Customer channels | Communications Lead with Legal sign-off |
| BNM | Per BNM BCM PD and per RMiT 11.18 for cyber-induced | Per BNM channels | CCO |
| Shariah Committee | If Shariah-compliant services affected materially | Per Shariah Committee channels | Head of Shariah Compliance |

## 7. Testing and exercise

| Frequency | Type | Owner |
|---|---|---|
| Quarterly | Tabletop exercise — rotating scenarios | COO |
| Annually | Functional / component test per critical service | Head of IT Ops + service owner |
| Annually | End-to-end exercise (one critical service per year on rotating multi-year cycle) | COO + CEO |
| Annually overlapping | Joint BCP/DRP/IRP exercise | COO + CISO |

Outcomes documented in [REG-BCT BC Test Outcomes Register](../06-registers/REG-BCT-bc-test-outcomes-register.md). Material findings reported to RMC.

## 8. Reference appendices

(Maintained separately for distribution control; not in this repo.)

- Appendix A — BIA outcomes summary per critical service (with current MTPD/RTO/RPO)
- Appendix B — DRP index (PLN-03-x per critical service)
- Appendix C — Alternate-site activation procedures
- Appendix D — Alternate-supplier activation procedures
- Appendix E — Customer communication templates per scenario class
- Appendix F — Shariah-compliance continuity considerations per product

## 9. Document control

| Version | Date | Author | Reviewer | Approver | Change summary |
|---|---|---|---|---|---|
| 1.0 | [Effective] | COO | RMC review pack | RMC | Initial Effective version |
