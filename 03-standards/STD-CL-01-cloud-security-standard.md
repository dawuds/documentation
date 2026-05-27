# STD-CL-01 — Cloud Security Standard

| | |
|---|---|
| **Document ID** | STD-CL-01 | **Version** | 1.0 |
| **Owner / Approver** | Head of Cloud + CISO / CISO |
| **Parent policy** | [POL-20](../02-policies/POL-20-cloud-acceptable-use-policy.md) | **Parent framework** | [CloudRMF](../01-frameworks/CloudRMF.md) |
| **RMiT clause(s)** | Section 10.50–10.52; Appendix 10 |
| **Practice** | CSA Cloud Controls Matrix; CIS Foundations Benchmarks; ISO/IEC 27017/27018 |

## 1. Purpose
Specify cloud-environment security controls for GIBB's primary cloud providers — identity, network, encryption, monitoring, configuration baselines.

## 2. Scope
All IaaS and PaaS workloads in GIBB-managed cloud environments. SaaS-specific controls per separate SaaS standard.

## 3. Requirements

### 3.1 Cloud landing zone baseline

| Ref | Requirement |
|---|---|
| 3.1.1 | All workloads shall deploy into a baselined landing zone aligned to CIS Foundations Benchmark for the provider (AWS, Azure, GCP). |
| 3.1.2 | Landing zone baseline reviewed annually + on CIS benchmark version update. |
| 3.1.3 | Landing zone deviation requires documented exception per [POL-20](../02-policies/POL-20-cloud-acceptable-use-policy.md). |

### 3.2 Cloud identity and access

| Ref | Requirement |
|---|---|
| 3.2.1 | Cloud identity federated with GIBB IDP; no standalone cloud identities except break-glass per [STD-AC-01](STD-AC-01-password-and-authentication-standard.md). |
| 3.2.2 | Cloud root / global admin credentials shall not be used for routine operations; reserved for break-glass with full logging. |
| 3.2.3 | Least-privilege IAM policies — no `*` permissions on production resources. |
| 3.2.4 | Service principals / IAM roles preferred over long-lived API keys. Where API keys necessary, rotated every 90 days. |

### 3.3 Cloud network

| Ref | Requirement |
|---|---|
| 3.3.1 | Production VPCs / VNets segmented by tier and function; explicit egress controls. |
| 3.3.2 | No direct public exposure of compute resources except where the resource is designed as internet-facing (load balancers, CDN endpoints). |
| 3.3.3 | Private connectivity (Direct Connect, ExpressRoute, Interconnect) for material on-premises ↔ cloud traffic. |
| 3.3.4 | Service endpoints / private endpoints for managed services where supported. |

### 3.4 Cloud encryption

| Ref | Requirement |
|---|---|
| 3.4.1 | Confidential or higher data at rest in cloud — encryption with **customer-managed keys (CMK)**, not provider-managed defaults, where service supports CMK. |
| 3.4.2 | All cloud traffic encrypted in transit per [STD-CR-01](STD-CR-01-cryptographic-standard.md). |
| 3.4.3 | KMS access logged; key access reviewed per [REG-PAR](../06-registers/REG-PAR-privileged-access-review-register.md). |

### 3.5 Cloud monitoring

| Ref | Requirement |
|---|---|
| 3.5.1 | Cloud control-plane logs (CloudTrail / Activity Log / Audit Logs) enabled in every account / subscription / project with multi-region delivery to central SIEM per [STD-CR-02](STD-CR-02-logging-standard.md). |
| 3.5.2 | **CSPM** (Cloud Security Posture Management) tooling continuously monitors cloud configuration against baseline; critical findings trigger ticket within 1 hour. |
| 3.5.3 | Cloud workload protection (CWPP) on production VMs and containers per [STD-CR-02](STD-CR-02-logging-standard.md). |

### 3.6 Cloud secrets management

| Ref | Requirement |
|---|---|
| 3.6.1 | Cloud-native secrets stores used for application secrets — Secrets Manager / Key Vault / Secret Manager. |
| 3.6.2 | Hardcoded secrets in code or config prohibited; CI-pipeline secret scanning mandatory. |

### 3.7 Cloud cost as a security signal

| Ref | Requirement |
|---|---|
| 3.7.1 | Anomalous cloud cost spike (potential cryptomining / abuse) triggers SOC investigation per [STD-CR-02](STD-CR-02-logging-standard.md). |

### 3.8 Provider-specific addenda

Per-provider implementation details (AWS / Azure / GCP) maintained in subordinate engineering standards, anchored on this STD-CL-01.

## 4. Exceptions
Per [POL-20](../02-policies/POL-20-cloud-acceptable-use-policy.md). Departures from RMiT Appendix 10 require explicit RMC approval and documented justification.

## 5. Related documents
[POL-20](../02-policies/POL-20-cloud-acceptable-use-policy.md); STD-CL-02 Cloud Landing Zone Standard; STD-CL-03 Cloud Data Residency Standard; [STD-CR-01](STD-CR-01-cryptographic-standard.md); [STD-CR-02](STD-CR-02-logging-standard.md); [REG-CL](../06-registers/REG-CL-cloud-service-register.md); [CloudRMF](../01-frameworks/CloudRMF.md)

## 6. References
BNM RMiT 28 Nov 2025 §10.50–10.52; Appendix 10; BNM Cloud TRAG; CSA CCM; CIS Foundations Benchmarks (AWS / Azure / GCP); ISO/IEC 27017; ISO/IEC 27018.

## 7. Document control
| Version | Date | Author | Approver | Change |
|---|---|---|---|---|
| 1.0 | [Effective] | Head of Cloud + CISO | CISO | Initial |
