# STD-NW-01 — Network Segmentation and On-Premise Network Security Standard

| | |
|---|---|
| **Document ID** | STD-NW-01 | **Version** | 1.0 |
| **Owner / Approver** | Head of Network + CISO / CRO (with CIO concurrence) |
| **Parent policy** | [POL-16 Operations Security Policy](../02-policies/POL-16-operations-security-policy.md); [POL-04](../02-policies/POL-04-information-security-policy.md) | **Parent framework** | [CRMF](../01-frameworks/CRMF.md); [TRMF](../01-frameworks/TRMF.md) |
| **RMiT clause(s)** | Section 10.36–10.43 (Network Resilience); Section 10.44–10.45 (Network Operations and Monitoring) |
| **COBIT objective(s)** | DSS05 Managed Security Services; DSS01 Managed Operations |
| **Practice standard(s)** | ISO/IEC 27002:2022 controls 8.20–8.23 (Networks); CIS Critical Security Controls v8 — Controls 12, 13 (Network Infrastructure); NIST SP 800-41; PCI-DSS 4.0 Requirements 1, 4 (where in scope) |

---

## 1. Purpose

To define minimum network-security and segmentation requirements for **on-premise network infrastructure** — the primary and DR data centres, branch network, head office, and any non-cloud-hosted workload network. Closes the on-premise coverage gap surfaced in the v2 multi-agent review (CIO: "heavy cloud emphasis but no equivalent depth for the on-prem DC that still runs core banking").

Cloud-side equivalents are in [STD-CL-02 Cloud Landing Zone Standard](STD-CL-02-cloud-landing-zone-standard.md).

## 2. Scope

All GIBB-operated on-premise network: data centre core, distribution, access; branch network; head office LAN/WLAN; ATM network; payment-system dedicated networks; OT/IoT-bridge segments; vendor-managed network handoffs that terminate on GIBB premise. Cloud networks are in scope of [STD-CL-02](STD-CL-02-cloud-landing-zone-standard.md).

## 3. Requirements

### 3.1 Segmentation zones

The network **shall** be segmented into the following minimum zones; cross-zone traffic permitted only via documented and authorised flows.

| Zone | Purpose | Default-deny inbound from | Default-deny outbound to |
|---|---|---|---|
| Internet edge / DMZ | Internet-facing services | All except validated internet flows | Internal except validated flows |
| Customer-channel zone | Internet banking, mobile banking application servers | All except DMZ via WAF and internal app traffic | All except DB tier + auth tier |
| Core banking zone | Core banking platform | All except customer-channel-tier app servers and operations | All except authorised downstream systems and operations |
| Payment-systems zone | RENTAS, IBG, e-Channels payment processors | All except payment-app tier and BNM payment-network handoff | Strictly limited per RMiT Section 10.36 |
| Treasury zone | Treasury systems | All except authorised treasury app tier | Strictly limited |
| Database tier | All bank databases | App tier only | None outbound to internet |
| Authentication / identity zone | IDP, AD, IGA, PAM | App tiers via service principals only | Limited management |
| Cardholder data environment (CDE) — if PCI-DSS in scope | PCI-scope assets | PCI-DSS Requirement 1 only | PCI-DSS Requirement 1 only |
| Operations / management zone | Jump hosts, monitoring, backup, patching, configuration | Operator workstations via PAM only | Targeted management traffic only |
| Workforce LAN/WLAN | Employee endpoints | Internet via proxy; identity zone | Internet via proxy; application tiers via identity |
| Branch network | Branch operations | VPN concentrators only; identity zone for application | Internet via proxy; application tiers via identity |
| Visitor / vendor / IoT/OT bridge | Untrusted internal | None — fully isolated from production | Internet only; **never to production** |

### 3.2 Segmentation control bar

| Ref | Requirement |
|---|---|
| 3.2.1 | All inter-zone traffic **shall** traverse a firewall enforcing default-deny with explicit allow-list. *(ISO/IEC 27002 8.22; RMiT 10.40.)* |
| 3.2.2 | All firewall rules **shall** have a documented business justification, named owner, and review cycle (Critical / inter-zone: quarterly; intra-zone: annual). |
| 3.2.3 | The CDE — where PCI-DSS applies — **shall** be physically or logically segmented per PCI-DSS Requirement 1.2.1, with scope reduction by segmentation evidenced and tested annually. |
| 3.2.4 | Workforce LAN **shall not** route directly to database tier, payment-system zone, treasury zone, or core banking zone. |
| 3.2.5 | Visitor / vendor / IoT/OT segments **shall** be physically or logically air-gapped from production zones; any required production-touching flow goes via an explicit data diode or jump server. |
| 3.2.6 | All inter-zone communication **shall** be logged for retention per [STD-CR-02 Logging Standard](STD-CR-02-logging-standard.md). |

### 3.3 Perimeter and edge protection

| Ref | Requirement |
|---|---|
| 3.3.1 | Internet edge **shall** be protected by stateful firewalls + IDS/IPS + WAF for HTTP(S) services. |
| 3.3.2 | DDoS mitigation **shall** be in place for all internet-facing services (per [REG-CL CL-0005](../06-registers/REG-CL-cloud-service-register.md)). |
| 3.3.3 | Encrypted inspection (TLS inspection) **shall** be applied to outbound workforce traffic except for explicitly excluded categories (banking, healthcare, legal — privacy categories). |
| 3.3.4 | Egress filtering **shall** restrict workforce zones and server zones to known-good destinations; exfil-detection rules **shall** be in place. |

### 3.4 Wireless

| Ref | Requirement |
|---|---|
| 3.4.1 | Corporate WLAN **shall** require WPA3-Enterprise (or WPA2-Enterprise pending phase-out); guest WLAN **shall** be isolated from corporate networks. |
| 3.4.2 | Wireless intrusion detection **shall** be in place across all premises. |
| 3.4.3 | Rogue AP detection **shall** be operated continuously; findings triaged per [SOP-IR-01](../04-procedures/SOP-IR-01-incident-triage-sop.md). |

### 3.5 Branch network

| Ref | Requirement |
|---|---|
| 3.5.1 | Branch network **shall** terminate to head office via SD-WAN or MPLS with encrypted backhaul. |
| 3.5.2 | Branch-side endpoints **shall** route all production-zone access via identity-aware proxies. |
| 3.5.3 | Branch ATM networks **shall** be isolated from branch staff network; ATM uplinks to ATM management plane only. |

### 3.6 Network change discipline

| Ref | Requirement |
|---|---|
| 3.6.1 | Firewall rule changes are subject to [STD-CM-01](STD-CM-01-change-management-standard.md), with the Independent Reviewer being a senior network engineer not on the requesting team. |
| 3.6.2 | New zone introduction or material zone-boundary change requires CISO + Head of Network + Head of IT Ops joint approval. |
| 3.6.3 | Quarterly firewall rule recertification per RMiT 10.40; expired or unjustified rules removed within 30 days of review. |

### 3.7 Monitoring and detection

| Ref | Requirement |
|---|---|
| 3.7.1 | Continuous monitoring of east-west and north-south traffic for anomalies; SOC plays the lead per [CRMF](../01-frameworks/CRMF.md) Section 8. |
| 3.7.2 | Network telemetry (NetFlow, packet capture for selected segments, DNS) **shall** feed the SIEM; retention per [STD-CR-02](STD-CR-02-logging-standard.md). |
| 3.7.3 | Detection use-cases **shall** include lateral movement, beaconing, DNS tunnelling, abnormal east-west volume, off-hours administrative access. |

## 4. Exceptions

Per [POL-04](../02-policies/POL-04-information-security-policy.md) and [POL-16](../02-policies/POL-16-operations-security-policy.md). Network exceptions require CISO + Head of Network approval; exceptions affecting customer-facing channels additionally require CIO approval; exceptions affecting CDE require RMC approval per PCI-DSS scope-management discipline.

## 5. Related documents

[POL-04](../02-policies/POL-04-information-security-policy.md); [POL-16](../02-policies/POL-16-operations-security-policy.md); [STD-CL-02 Cloud Landing Zone](STD-CL-02-cloud-landing-zone-standard.md); [STD-CR-02 Logging](STD-CR-02-logging-standard.md); [STD-CM-01 Change Mgmt](STD-CM-01-change-management-standard.md); SOP-DC-01 Data Centre Operations SOP (placeholder).

## 6. References

BNM RMiT 28 Nov 2025 Section 10.36–10.45; ISO/IEC 27002:2022 controls 8.20–8.23; CIS Critical Security Controls v8 Controls 12, 13; NIST SP 800-41; PCI-DSS 4.0 Requirements 1, 4.

## 7. Document control

| Version | Date | Author | Reviewer | Approver | Change summary |
|---|---|---|---|---|---|
| 1.0 | 2026-05-30 | Head of Network + CISO | CRO + CIO | CRO (with CIO concurrence) | Initial version. Closes on-premise network coverage gap identified in v2 multi-agent review (CIO: "heavy cloud emphasis but no equivalent depth for the on-prem DC"). Cloud parallel: STD-CL-02. |
