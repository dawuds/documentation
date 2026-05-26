# Extension roadmap

What a complete M3 ISMS would add beyond this worked example. The repo intentionally drafts only the documents needed to demonstrate the **cascade pattern** end-to-end on two domains (Access Control, Incident Management). A real bank's M3 ISMS would maintain ~15–25 standards, ~30–80 SOPs, ~3–5 plans, and ~8–12 registers.

← [Back to _learning](README.md) · [Repo home](../README.md)

---

## Standards (Tier 2) to add

| Standard | Parent policy | Why it's needed |
|---|---|---|
| Cryptographic Standard (algorithms, key lengths, deprecation schedule, post-quantum migration) | [POL-05](../01-policies/05-cryptography-policy.md) | Concrete algorithm and key-length choices need a single source of truth |
| Logging Standard (what events to log, format, retention, time-sync) | [POL-11](../01-policies/11-operations-security-policy.md) | Auditors and forensics depend on consistent logging |
| Network Security Standard (segmentation tiers, firewall rules baseline, perimeter) | [POL-11](../01-policies/11-operations-security-policy.md) | RMiT §10.36–10.43 Network Resilience requires explicit network controls |
| Cloud Security Standard (per provider — AWS / Azure / GCP — landing zone, IAM, encryption defaults) | [POL-07](../01-policies/07-supplier-security-policy.md) | Operational specificity for RMiT §10.50–10.52 + App. 10 |
| Endpoint Standard (managed device baseline, EDR config, MDM rules) | [POL-11](../01-policies/11-operations-security-policy.md) / [POL-01](../01-policies/01-acceptable-use-policy.md) | Workforce endpoint security |
| Data Handling Standard (per classification × media combination) | [POL-04](../01-policies/04-data-classification-policy.md) | Operationalises Public / Internal / Confidential / Highly Restricted |
| Secure Coding Standard (per language, per framework) | [POL-12](../01-policies/12-secure-development-policy.md) | Developer-actionable detail |
| Vulnerability Triage Standard (CVSS thresholds, EPSS factors, KEV handling) | [POL-13](../01-policies/13-vulnerability-management-policy.md) | Quantifies POL-13 §3.2 prioritisation |

## Procedures / SOPs (Tier 3) to add

| SOP | Function | Why |
|---|---|---|
| Service Account Lifecycle SOP | IAM | Non-human identity management — distinct from human JML |
| Privileged Access Review SOP | IAM | The quarterly review that populates [REG-PAR](../05-registers/privileged-access-review-register.md) |
| Exception Approval SOP | ISMS Manager | The workflow behind every documented exception |
| Vulnerability Scan Operation SOP | Vulnerability Mgmt | Operational running of the scanning toolchain |
| Patch Deployment SOP | IT Ops | Change-management overlay for patching |
| Backup Operation SOP | IT Ops | Daily / weekly running and restorability testing |
| SOC Detection Tuning SOP | SOC | False-positive management, detection-engineering backlog |
| Cyber Drill Exercise SOP | SOC + CISO | The annual cyber drill required by RMiT §11.16 |
| Forensic Evidence Handling SOP | SOC | Chain-of-custody operations for incident evidence |

## Plans to add

| Plan | Parent policy | Owner | Why |
|---|---|---|---|
| Business Continuity Plan (BCP) | [POL-09](../01-policies/09-business-continuity-policy.md) | COO | Per RMiT §10.24–10.35 service availability; BCM policy alignment |
| Disaster Recovery Plan (DRP) — per critical system | [POL-09](../01-policies/09-business-continuity-policy.md) + [POL-11](../01-policies/11-operations-security-policy.md) | Head of IT Ops | RTO / RPO-aligned technical recovery procedures per service |
| Crisis Communications Plan | [POL-08](../01-policies/08-incident-management-policy.md) + Corp Comms policy | Head of Corp Comms | Coordinates internal, customer, regulator, media during crises |
| Pandemic / Workforce Disruption Plan | [POL-09](../01-policies/09-business-continuity-policy.md) | COO + CHRO | Workforce-availability scenarios |
| Cyber Crisis Playbook (subordinate to IRP) | [POL-08](../01-policies/08-incident-management-policy.md) | CISO | Per-scenario playbooks (ransomware, insider, supplier compromise) — operationalises RMiT §11.12 |

## Registers to add

| Register | Owner | Cadence | Why |
|---|---|---|---|
| Asset Register | Head of IT Ops | Continuous | RMiT §11.3(h) requires a centralised automated tracking system |
| Exception Register | ISMS Manager | Continuous | Every documented deviation from policy / standard |
| Training Register | CHRO + CISO | Continuous | ISO 27001 Clause 7.2 evidence of competence |
| Supplier Register | Procurement + CISO | Continuous | Per POL-07 — supplier criticality, attestation status, contract dates |
| Vulnerability Register | CISO | Continuous | Per POL-13 — beyond the scanner; SLA tracking, exceptions |
| Cloud Inventory Register | Head of Cloud Eng + CISO | Continuous | Per RMiT §10.50–10.52 |
| Records of Processing Activity (ROPA) | DPO | Continuous | Per PDPA 2010 and POL-14 §3.3 |

## 12 supporting policies — drafting completion

The 12 supporting policies (POL-01, POL-03 through POL-07, POL-09 through POL-14) are first-pass skeletons in this repo. A complete M3 ISMS would extend each to the depth shown in POL-00, POL-02, and POL-08.
