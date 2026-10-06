# NovaPay Inc. — Risk Assessment Scope & Methodology
**Framework Alignment:** NIST SP 800-30 Rev. 1 & ISO/IEC 27005:2022  
**Author:** P.V. Mohlala, Lead GRC Analyst  
**Version:** 1.0 (Final)  

---

## 1. Purpose & Objectives
This methodology defines how NovaPay Inc. identifies, analyzes, evaluates, and treats information security and privacy risks. A standardized methodology ensures that risks are scored objectively across the business, allowing executive leadership to allocate security capital efficiently and satisfy audit requirements for ISO 27001, SOC 2, and GDPR.

## 2. Assessment Scope
This risk assessment evaluates all digital assets, cloud environments (AWS), third-party SaaS vendors, payment processing applications, and remote engineering personnel within NovaPay Inc.’s operational perimeter.

### In-Scope Assets:
* AWS Cloud Infrastructure (`eu-west-1` Ireland & `us-east-1` N. Virginia)
* Payment Processing API microservices and PostgreSQL databases
* Identity and Access Management (Okta SSO, AWS IAM, GitHub)
* Remote developer endpoints (35 macOS/Windows workstations)
* Third-party vendor integrations (Analytics SaaS, SMS notifications)

## 3. Risk Assessment Process
NovaPay follows a 10-step risk lifecycle:
1. **Asset Identification:** Cataloging information assets and data types.
2. **Threat Identification:** Determining plausible threat actors and vectors (e.g., credential stuffing, ransomware, supply chain).
3. **Vulnerability Identification:** Pinpointing systemic or technical weaknesses.
4. **Impact Analysis:** Assessing financial, legal, reputational, and operational consequences.
5. **Likelihood Analysis:** Evaluating the probability of occurrence.
6. **Inherent Risk Scoring:** Multiplying Likelihood × Impact (Scale 1–25).
7. **Control Evaluation:** Reviewing existing technical and administrative safeguards.
8. **Residual Risk Scoring:** Re-evaluating risk level post-control implementation.
9. **Risk Treatment:** Selecting Mitigate, Transfer, Avoid, or Accept strategies.
10. **Review & Monitor:** Quarterly tracking via the Enterprise Risk Register.

---

## 4. Qualitative Scoring Scales

### Likelihood Scale (1 to 5)
| Score | Rating | Definition | Probability |
| :---: | :--- | :--- | :--- |
| **1** | Rare | Unlikely to occur within 5 years | < 10% |
| **2** | Unlikely | Possible within 3 years | 10% – 30% |
| **3** | Possible | Likely to occur within 1 year | 30% – 60% |
| **4** | Likely | Expected to occur quarterly | 60% – 90% |
| **5** | Certain | Expected monthly or active ongoing threat | > 90% |

### Impact Scale (1 to 5 - USD $)
| Score | Rating | Business Consequence (Financial, Regulatory, Operational) |
| :---: | :--- | :--- |
| **1** | Minor | Loss < $10,000; no PII/cardholder data exposed; negligible operational impact. |
| **2** | Moderate | Loss $10,000 – $100,000; internal data exposed; minor customer disruption. |
| **3** | Major | Loss $100,000 – $500,000; limited PII breach; GDPR notification required; client churn risk. |
| **4** | Severe | Loss $500,000 – $2.5 Million; mass PII/API key breach; regulator investigation; loss of major enterprise client. |
| **5** | Critical | Loss > $2.5 Million; core database compromise; max GDPR fine (€20M / 4%); PCI-DSS revoked; business closure risk. |

---

## 5. Risk Scoring Matrix & Action SLAs
$$\text{Risk Score} = \text{Likelihood} \times \text{Impact}$$

| Score Range | Risk Rating | Required Action & Management SLA |
| :---: | :---: | :--- |
| **20 – 25** | **CRITICAL** | Immediate board notification. Mandatory remediation within **15 Days**. |
| **12 – 19** | **HIGH** | Remediation required within **30 Days**. VP of Engineering sign-off. |
| **6 – 11** | **MEDIUM** | Remediation required within **90 Days**. Department head monitoring. |
| **1 – 5** | **LOW** | Formally accept and monitor. Annual review. |
