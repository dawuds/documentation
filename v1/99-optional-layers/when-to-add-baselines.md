# When to add Baselines

A Baseline is the **minimum technical configuration** for a class of system — typically a hardening configuration expressed in a machine-readable or close-to-machine-readable form. Examples: CIS Benchmark profile, SCAP/STIG content, Ansible-based hardening role, Terraform module, container image base, cloud landing-zone manifest.

General Bank in this worked example uses **Baselines selectively** — for the technology operations stack (server OS, containers, cloud landing zone, network device configuration) — but does not formalise them as a stand-alone folder in this repo (they would live in the engineering tooling repos).

---

## When Baselines earn their keep

Add Baselines when **at least one** of the following is true:

| Trigger | Why Baselines help |
|---|---|
| Configuration drift is causing repeated vulnerability or audit findings | A baseline + automated assessment closes the drift loop. |
| You can express the minimum configuration **as code or data** that a tool can assess | If you can run a scanner against it, it should be a baseline. If it can only be written in prose, it's a standard, not a baseline. |
| You have the engineering capacity to **maintain** the baseline and **assess** against it | Baselines that aren't assessed are decorative. |
| You operate at scale where manual review of every system's configuration is impossible | E.g., hundreds of servers, thousands of cloud resources. |

## When Baselines do **not** earn their keep

- When you have nowhere to apply them (small estate, no scanner, no engineering capacity to maintain).
- When the underlying standard is unclear — baselines crystallise standards into specific settings, so the standard has to be settled first.
- When you have no plan to **enforce** them — a baseline you can't enforce is a guideline.

## What good Baselines look like

| Property | Reason |
|---|---|
| **Versioned** | Configurations change as vulnerabilities and threats evolve. |
| **Sourced from a recognised reference** | CIS Benchmarks, NIST SCAP content, vendor hardening guides, cloud-provider security pillar — don't write a baseline from scratch when an authoritative one exists. |
| **Levelled** | E.g., CIS Level 1 (broad compatibility) vs Level 2 (high security). State which level applies to which environment class. |
| **Tested before enforcement** | A baseline applied without testing breaks production. Stage it. |
| **Assessed continuously, not annually** | Drift is constant; the assessment cadence has to match. |
| **Tied to a remediation workflow** | A non-compliant finding has to lead somewhere. |

## Baseline catalogue General Bank might maintain

| Class | Baseline | Reference |
|---|---|---|
| Linux server (Ubuntu LTS) | CIS Ubuntu 22.04 LTS Benchmark Level 1 (Server) | CIS |
| Windows Server | CIS Microsoft Windows Server Benchmark Level 1 | CIS |
| Kubernetes | CIS Kubernetes Benchmark | CIS |
| Container images | Distroless / minimal images + scan thresholds | Internal |
| AWS landing zone | CIS AWS Foundations Benchmark + bank overlay | CIS + internal |
| Azure landing zone | CIS Azure Foundations Benchmark + bank overlay | CIS + internal |
| Network device | Vendor-provided hardening + internal overlay | Vendor + internal |
| Database (managed) | Cloud-provider security guidance + internal overlay | Provider + internal |

## Relationship to standards

A baseline implements a standard; it does not replace one. Example:

- **Standard (STD)**: "Linux servers shall be hardened per a recognised hardening baseline; baseline shall be assessed weekly; non-compliant configurations shall be remediated per the vulnerability remediation timelines."
- **Baseline**: the actual Ansible role + CIS-CAT content + remediation playbook.

The standard is what auditors read. The baseline is what engineers ship.
