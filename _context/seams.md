# Framework seams

Where two Layer 2 frameworks have overlapping scope, the seam between them must be explicitly defined. Otherwise: two owners write conflicting rules, or neither owns and an audit gap appears.

← [_context home](README.md) · [decisions.md](decisions.md) · [framework-stack.md](framework-stack.md)

---

## Seam 1 — DGF / CIMF

**Risk:** Both touch customer data. Without a stated seam, conflicting ownership or duplication.

**Resolution:**

| Framework | Owns |
|---|---|
| **DGF** | Enterprise-wide data principles for ALL data assets — customer, employee, vendor, product, transactional, analytical, AI training, regulatory reporting. Topics: data ownership, classification, quality, lineage, master/reference data, metadata, AI training data, data lake/warehouse, lifecycle, destruction. |
| **CIMF** | Customer data specifically + regulatory overlay per BNM MCIPD and PDPA 2010. Topics: customer consent, customer data subject rights, customer data permitted disclosures, customer data breach notification under PDPA + BNM. |

**Required cross-statement** (in both documents):
> *"Customer data is governed by DGF principles AND additionally subject to CIMF customer-specific requirements."*

---

## Seam 2 — TPRMF / CloudRMF

**Risk:** Cloud providers are third parties. Cloud risk could be owned twice or not at all.

**Resolution:**

| Framework | Owns |
|---|---|
| **TPRMF** | The third-party relationship lifecycle — selection, due diligence, contracting, ongoing monitoring, exit. Applies to all third parties regardless of service type. |
| **CloudRMF** | Cloud-specific risk content — shared-responsibility model, data residency, cloud-native controls, cloud exit complexity, cloud regulatory expectations (BNM RMiT 10.50–10.52 + Appendix 10 + BNM Cloud TRAG). |

**Required cross-statement:** Cloud provider engagement triggers BOTH frameworks. TPRMF governs the relationship; CloudRMF governs the cloud-specific risk content within the engagement.

---

## Seam 3 — TRMF / CRMF

**Risk:** Cyber is one of multiple tech-risk domains. Could nest or be peer.

**Resolution:** Peer-level, cross-referenced.

| Framework | Owns |
|---|---|
| **TRMF** | Technology risk management broadly — satisfies RMiT Section 9.2 (11 mandatory TRMF elements) + broader IT governance content (COBIT EDM + APO domains). The bank's overarching technology risk framework. |
| **CRMF** | Cyber resilience capabilities — satisfies RMiT Section 11.2 + Section 11.3 (nine mandatory CRF elements). The bank's cyber-specific resilience framework. The Information Security sub-framework (ISO 27001-based, drawing on v1) sits within CRMF. |

**Required cross-statement:** TRMF establishes the technology risk governance umbrella. CRMF establishes the cyber resilience capability within the bank's overall technology risk posture. Both are RMiT-mandated as standalone documents.

---

## Adjacent overlaps (not strictly seams)

| Overlap | Resolution |
|---|---|
| **AIGF / DGF** — AI training data is governed by DGF; AI model risk is governed by AIGF | AIGF references DGF for training-data governance; AIGF owns model risk, AI use-case risk classification, AI lifecycle management. |
| **NCIIF / CRMF** — NCII obligations overlap heavily with cyber resilience | NCIIF owns NACSA-specific obligations (Code of Practice, NACSA notifications, NCII designation maintenance). CRMF owns the broader cyber resilience capability. NCIIF cites CRMF for the underlying cyber controls. |
| **BCMF / TRMF** — IT service continuity is both BC and tech-risk | BCMF owns the overall business continuity governance (BIA, RTO/RPO, plans). TRMF owns IT-specific resilience controls (service availability per RMiT 10.29–10.35, backup per 10.44–10.45). BCMF cites TRMF for IT-specific recovery. |

---

## Maintenance

When a new framework is added (or scope of an existing one expands), assess for new seams. Add to this document with explicit cross-statements. Failure to define a seam early creates audit pain later.
