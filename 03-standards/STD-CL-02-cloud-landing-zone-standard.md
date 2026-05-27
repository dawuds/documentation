# STD-CL-02 — Cloud Landing Zone Standard

| | |
|---|---|
| **Document ID** | STD-CL-02 | **Version** | 1.0 |
| **Owner / Approver** | Head of Cloud / CISO |
| **Parent policy** | [POL-20](../02-policies/POL-20-cloud-acceptable-use-policy.md) | **Parent framework** | [CloudRMF](../01-frameworks/CloudRMF.md) |
| **Practice** | CIS Foundations Benchmarks; CSA CCM; provider-specific landing zone reference architectures |

## 1. Purpose
Specify the baseline cloud landing zone every GIBB cloud workload deploys into — account structure, network, identity, encryption, logging defaults.

## 2. Scope
All IaaS and PaaS deployments. SaaS-specific configuration per separate SaaS standard.

## 3. Requirements

### 3.1 Account / subscription / project structure
Per-environment isolation: production, non-production (dev/test), shared services, security tooling, audit/logging in separate accounts (AWS) / subscriptions (Azure) / projects (GCP). Workload accounts cannot directly access security-tooling or audit accounts; controlled via central IAM.

### 3.2 Network baseline
| Ref | Requirement |
|---|---|
| 3.2.1 | Hub-and-spoke network topology; each workload account/subscription is a spoke; hub centralises shared services and egress |
| 3.2.2 | Default-deny egress; explicit egress allow-list per workload |
| 3.2.3 | No direct public exposure of compute; all internet-facing through load balancer/CDN with WAF |
| 3.2.4 | Private endpoints / service endpoints for managed services where supported |
| 3.2.5 | DDoS protection enabled at perimeter |

### 3.3 Identity baseline
| Ref | Requirement |
|---|---|
| 3.3.1 | Federated identity from GIBB IDP; no standalone cloud identities except break-glass per [STD-AC-01 §3.7](STD-AC-01-password-and-authentication-standard.md) |
| 3.3.2 | Workload identity via roles/managed identities/service accounts — not long-lived API keys |
| 3.3.3 | Just-in-time elevation for privileged operations |
| 3.3.4 | IAM policies follow least-privilege; no `*` permissions on production |

### 3.4 Encryption baseline
| Ref | Requirement |
|---|---|
| 3.4.1 | All storage encrypted at rest; customer-managed keys (CMK) for Confidential+ data |
| 3.4.2 | All inter-service traffic encrypted in transit per [STD-CR-01](STD-CR-01-cryptographic-standard.md) |
| 3.4.3 | KMS access logged centrally |

### 3.5 Logging baseline
| Ref | Requirement |
|---|---|
| 3.5.1 | Control-plane logs (CloudTrail/Activity Log/Audit Logs) enabled in every account with central SIEM delivery per [STD-CR-02](STD-CR-02-logging-standard.md) |
| 3.5.2 | VPC flow logs / equivalent for production networks |
| 3.5.3 | KMS audit logs |

### 3.6 Posture baseline
| Ref | Requirement |
|---|---|
| 3.6.1 | CSPM coverage of every cloud account on day 1 of deployment |
| 3.6.2 | Provider-native security services enabled — GuardDuty / Defender for Cloud / Security Command Center |
| 3.6.3 | Configuration drift from baseline triggers ticket per [STD-CR-03](STD-CR-03-vulnerability-triage-standard.md) timelines |

### 3.7 Infrastructure-as-code
| Ref | Requirement |
|---|---|
| 3.7.1 | Landing zone provisioned through IaC; manual provisioning of production resources prohibited except break-glass |
| 3.7.2 | IaC stored in source control with mandatory code review per [POL-17 §4.9](../02-policies/POL-17-secure-development-policy.md) |
| 3.7.3 | Pre-deploy IaC scanning (Checkov / equivalent) blocking pipeline on critical findings |

### 3.8 Provider-specific addenda
Per-provider variations (AWS / Azure / GCP) maintained as subordinate engineering documents.

## 4. Exceptions
Per [POL-20](../02-policies/POL-20-cloud-acceptable-use-policy.md). Departures from landing zone require Head of Cloud + CISO approval.

## 5. Related documents
[STD-CL-01](STD-CL-01-cloud-security-standard.md); [STD-CL-03](STD-CL-03-cloud-data-residency-standard.md); [STD-CR-01](STD-CR-01-cryptographic-standard.md); [STD-CR-02](STD-CR-02-logging-standard.md); [REG-CL](../06-registers/REG-CL-cloud-service-register.md); [SOP-CL-01](../04-procedures/SOP-CL-01-cloud-service-onboarding-sop.md)

## 6. References
BNM RMiT 28 Nov 2025 §10.50–10.52; Appendix 10; BNM Cloud TRAG; CIS Foundations Benchmarks (AWS/Azure/GCP); CSA CCM; AWS Well-Architected Framework — Security Pillar; Azure Cloud Adoption Framework; Google Cloud Architecture Framework.

## 7. Document control
| Version | Date | Author | Approver | Change |
|---|---|---|---|---|
| 1.0 | [Effective] | Head of Cloud | CISO | Initial |
