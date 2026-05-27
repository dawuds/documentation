# STD-AI-04 — AI Training Data Standard

| | |
|---|---|
| **Document ID** | STD-AI-04 | **Version** | 1.0 |
| **Owner / Approver** | CDO + DPO / CDO |
| **Parent policy** | [POL-21](../02-policies/POL-21-ai-acceptable-use-policy.md); [POL-11](../02-policies/POL-11-data-classification-policy.md) | **Parent framework** | [AIGF](../01-frameworks/AIGF.md); [DGF](../01-frameworks/DGF.md) |

## 1. Purpose
Specify governance for AI training data — sourcing, lawful basis, quality, bias assessment, provenance, retention.

## 2. Scope
All datasets used to train, fine-tune, or fine-prompt AI models at GIBB.

## 3. Requirements

### 3.1 Lawful basis for personal data in training
| Ref | Requirement |
|---|---|
| 3.1.1 | Personal data in training requires PDPA-compliant lawful basis recorded in [REG-ROPA](../06-registers/REG-ROPA-records-of-processing-activity.md) |
| 3.1.2 | Customer data for training requires consent or contractual basis with explicit AI-use disclosure |
| 3.1.3 | Preference for de-identified / synthetic data where the use case permits |

### 3.2 Provenance
| Ref | Requirement |
|---|---|
| 3.2.1 | Every training dataset registered in [REG-DA](../06-registers/REG-DA-data-asset-register.md) with `ai_training_use=true` |
| 3.2.2 | Source documented — internal system, public dataset, vendor-provided, third-party-purchased |
| 3.2.3 | Vendor / third-party datasets carry licence and rights-of-use confirmation |
| 3.2.4 | Training data lineage documented per [STD-DG-03](STD-DG-03-metadata-standard.md) |

### 3.3 Quality
| Ref | Requirement |
|---|---|
| 3.3.1 | Training data quality measured per [STD-DG-01](STD-DG-01-data-quality-standard.md) dimensions adapted for AI: accuracy, completeness, representativeness |
| 3.3.2 | Test set held out per industry practice; never used in training |

### 3.4 Bias assessment
| Ref | Requirement |
|---|---|
| 3.4.1 | Training data assessed for bias across customer-affecting groups (demographic, geographic, Islamic-conventional product mix) |
| 3.4.2 | Bias findings remediated through resampling, augmentation, or data exclusion documented in [REG-AIB AI Bias and Fairness Register](../06-registers/REG-AIB-ai-bias-and-fairness-register.md) |

### 3.5 Sensitive data
| Ref | Requirement |
|---|---|
| 3.5.1 | Sensitive personal data per PDPA in training requires explicit DPO + DCO sign-off |
| 3.5.2 | Shariah-Confidential data not used in training without Shariah Committee approval |
| 3.5.3 | Authentication data never used in training |

### 3.6 Data minimisation
| Ref | Requirement |
|---|---|
| 3.6.1 | Training datasets minimised to fields necessary for the use case |
| 3.6.2 | Identifiers stripped where not required for the modelling problem |

### 3.7 Vendor / foundation-model considerations
| Ref | Requirement |
|---|---|
| 3.7.1 | GIBB does not contribute customer data to vendor foundation-model training unless contractually permitted and customer-disclosed |
| 3.7.2 | Vendor RAG with GIBB knowledge base — knowledge base prepared per this standard |

### 3.8 Retention
| Ref | Requirement |
|---|---|
| 3.8.1 | Training data retained per [STD-DG-02 §3](STD-DG-02-data-retention-standard.md) AI training data row |
| 3.8.2 | Training data destruction at end of retention per SOP-DG-03 Data Destruction SOP |

### 3.9 Re-training data refresh
| Ref | Requirement |
|---|---|
| 3.9.1 | Re-training requires fresh data quality + bias assessment |
| 3.9.2 | Re-training datasets versioned and linked to model versions |

## 4. Exceptions
Per [POL-21](../02-policies/POL-21-ai-acceptable-use-policy.md). Personal data in training without consent requires DPO + CCO + AIGC joint approval.

## 5. Related documents
[POL-21](../02-policies/POL-21-ai-acceptable-use-policy.md); [POL-11](../02-policies/POL-11-data-classification-policy.md); [STD-AI-01](STD-AI-01-ai-use-case-risk-classification-standard.md); [STD-AI-02](STD-AI-02-ai-model-validation-standard.md); [STD-DG-01](STD-DG-01-data-quality-standard.md); [STD-DG-02](STD-DG-02-data-retention-standard.md); [STD-DG-03](STD-DG-03-metadata-standard.md); [REG-DA](../06-registers/REG-DA-data-asset-register.md); REG-AIB (future)

## 6. References
NIST AI RMF 1.0; ISO/IEC 42001:2023; ISO/IEC 23894:2023 (AI risk management); EU AI Act Art. 10 (data and data governance); PDPA 2010; BNM Discussion Paper on Responsible AI.

## 7. Document control
| Version | Date | Author | Approver | Change |
|---|---|---|---|---|
| 1.0 | [Effective] | CDO + DPO | CDO | Initial |
