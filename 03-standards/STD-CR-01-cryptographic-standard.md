# STD-CR-01 — Cryptographic Standard

| | |
|---|---|
| **Document ID** | STD-CR-01 |
| **Layer** | Standard | **Version** | 1.0 |
| **Owner / Approver** | CISO / CISO |
| **Parent policy** | [POL-12](../02-policies/POL-12-cryptography-policy.md) | **Parent framework** | [CRMF](../01-frameworks/CRMF.md) |
| **RMiT clause(s)** | Section 10.20–10.23 |
| **COBIT** | APO13 | **Practice** | NIST FIPS 140-3; NIST SP 800-57 |

## 1. Purpose
Specify approved cryptographic algorithms, key lengths, protocol versions, key-management requirements, and crypto-agility provisions for GIBB.

## 2. Scope
All cryptographic use within GIBB — data at rest, data in transit, authentication, digital signatures, PKI, secrets management.

## 3. Requirements

### 3.1 Approved algorithms (symmetric)

| Use | Algorithm | Minimum key length |
|---|---|---|
| Bulk encryption at rest | AES-GCM-256 | 256-bit |
| Bulk encryption in transit (TLS) | AES-GCM-256 or ChaCha20-Poly1305 | 256-bit |
| Key wrapping | AES-KW-256 | 256-bit |

Prohibited: DES, 3DES, RC4, MD5 for any new use; deprecated and being phased out by 2026-12-31.

### 3.2 Approved algorithms (asymmetric)

| Use | Algorithm | Minimum key length |
|---|---|---|
| Key exchange | ECDHE (P-256 or P-384) or X25519 | Per curve |
| Digital signature | ECDSA (P-256, P-384) or Ed25519 or RSA-PSS | RSA ≥ 3072-bit |
| PKI CA root | ECDSA P-384 or RSA-4096 | Per curve / 4096-bit |

### 3.3 Hashing

| Use | Algorithm |
|---|---|
| General | SHA-256, SHA-384, SHA-512, SHA-3 family |
| Password hashing | Argon2id (preferred); bcrypt cost ≥ 12; PBKDF2-HMAC-SHA-256 iterations ≥ 600,000 |

Prohibited: MD5, SHA-1 for any security use (signatures, certificates, MAC).

### 3.4 TLS / protocols

| Ref | Requirement |
|---|---|
| 3.4.1 | TLS 1.2 minimum; TLS 1.3 preferred. SSL all versions prohibited. |
| 3.4.2 | Cipher suites limited to forward-secret (ECDHE), AEAD (GCM, ChaCha20-Poly1305). |
| 3.4.3 | Internet-facing services shall achieve SSL Labs grade ≥ A. |

### 3.5 Key management

| Ref | Requirement |
|---|---|
| 3.5.1 | All keys for production systems shall be generated, stored, used, and destroyed within an HSM or cloud KMS with FIPS 140-2 Level 2 / FIPS 140-3 validated modules. |
| 3.5.2 | Customer-data encryption keys in cloud shall use customer-managed keys (CMK), not provider-managed defaults. |
| 3.5.3 | Key rotation cadence: data-at-rest keys annually; authentication signing keys per use-case (typically 1–3 years); session keys per session. |
| 3.5.4 | Key compromise handling — documented incident response, key revocation, data re-encryption plan. |

### 3.6 Certificate management

| Ref | Requirement |
|---|---|
| 3.6.1 | Public certificates issued by trusted public CAs (DigiCert, Sectigo, Let's Encrypt for non-EV use cases). |
| 3.6.2 | Internal PKI certificates issued by GIBB's internal CA per Certificate Policy. |
| 3.6.3 | Certificate validity ≤ 397 days for public certificates (CA/B Forum); shorter where supported. |
| 3.6.4 | Certificate expiry monitoring with ≥ 30-day warning. |

### 3.7 Post-quantum readiness

| Ref | Requirement |
|---|---|
| 3.7.1 | Crypto-agility — systems shall support algorithm replacement without re-architecture. |
| 3.7.2 | Post-quantum migration plan maintained by CISO; updated annually as NIST PQC guidance evolves. |
| 3.7.3 | Hybrid post-quantum / classical cryptography evaluated for long-lived secrets. |

### 3.8 Prohibited uses

| Ref | Requirement |
|---|---|
| 3.8.1 | Cryptography shall not be used to evade legitimate inspection by security or compliance functions. |
| 3.8.2 | Personal cryptography of bank information to conceal from authorised audit is prohibited. |

## 4. Exceptions
Per [POL-12](../02-policies/POL-12-cryptography-policy.md). Any non-approved algorithm use requires written CISO approval.

## 5. Related documents
[POL-12](../02-policies/POL-12-cryptography-policy.md); [CRMF](../01-frameworks/CRMF.md); [STD-AC-01](STD-AC-01-password-and-authentication-standard.md)

## 6. References
BNM RMiT 28 Nov 2025 §10.20–10.23; ISO/IEC 27002:2022 control 8.24; NIST FIPS 140-3; NIST SP 800-57; NIST SP 800-208 (PQC); CA/Browser Forum.

## 7. Document control
| Version | Date | Author | Approver | Change |
|---|---|---|---|---|
| 1.0 | [Effective] | CISO | CISO | Initial |
