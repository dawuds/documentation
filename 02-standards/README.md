# 02 — Standards (Tier 2)

Mandatory, measurable requirements implementing the policies. CISO-approved. Annual review or technology-driven.

← [Repo home](../README.md) · [Foundations](../00-foundations/) ↑ · [Policies](../01-policies/) ↑

---

## Purpose

Standards quantify what the policy layer leaves as principle. A policy says "all privileged access shall require MFA"; a standard specifies which factors are approved, which are prohibited, the password length, the rotation cadence, and the evidence by which compliance is verified.

Without a standards layer, every SOP author has to make their own security decisions — producing inconsistency, drift, and audit findings.

## Contents

| ID | Document | Parent policy | ISO 27002:2022 | BNM RMiT (28 Nov 2025) |
|---|---|---|---|---|
| STD-02-01 | [Password & Authentication Standard](password-and-authentication-standard.md) | [POL-02](../01-policies/02-access-control-policy.md) | 5.17, 8.2, 8.5 | Section 10.53–10.57 (esp. Section 10.55 MFA) |
| STD-08-01 | [Incident Classification & Severity Standard](incident-classification-and-severity-standard.md) | [POL-08](../01-policies/08-incident-management-policy.md) | 5.25, 5.26 | Section 11.12; Section 11.13; Section 11.18 (with 4-hour BNM notification) |

Additional standards a complete M3 ISMS would maintain: see [`../_learning/extension-roadmap.md`](../_learning/extension-roadmap.md).

## Anatomy

Every standard uses the seven-section skeleton in [`../_templates/standard-template.md`](../_templates/standard-template.md): Purpose · Scope · Requirements (quantified **shall** statements with evidence column) · Exceptions · Related documents · References · Document control.

---

[`../01-policies/`](../01-policies/) ↑ · [`../03-procedures/`](../03-procedures/) ↓ · [`../06-document-control/`](../06-document-control/)
