# 🔄 NovaPay Inc. — Data Flow & Trust Boundary Analysis
**Compliance Alignment:** GDPR Article 30 & SOC 2 Trust Services Criteria (CC6.6)  
**Author:** P.V. Mohlala, Lead GRC Analyst  

---

## 1. Data Classification Standard
NovaPay classifies all data into four distinct sensitivity tiers to determine appropriate cryptographic and access controls:
* **Public:** Marketing collateral, public API documentation.
* **Internal:** Non-sensitive operational communications, internal engineering wikis.
* **Confidential:** Proprietary source code, unencrypted staging logs, internal financial forecasts.
* **Restricted (PII / Cardholder Data):** EU/US customer personal identifiable information (PII), merchant bank routing numbers, and encrypted card tokens.

## 2. Payment Gateway Data Lifecycle

### A. Ingress (Data Collection)
Merchants integrate with NovaPay via REST APIs over **TLS 1.3**. Cardholder data and payment payloads are ingested directly into AWS Application Load Balancers (ALB) and processed within ephemeral container instances.

### B. Storage & Processing
* **Database:** Transaction records and merchant credentials are stored in Amazon Aurora PostgreSQL with **AES-256 storage-level encryption**.
* **Tokenization:** Raw primary account numbers (PANs) are tokenized immediately upon ingress; raw card numbers are never persisted in NovaPay logs or databases (satisfying PCI-DSS scope reduction).

### C. Egress (Data Flow & Third-Party Sharing)
Data leaves NovaPay's boundary through three primary channels:
1. **Merchant Webhooks:** Real-time transaction status notifications sent to merchant endpoints over signed HTTPS payloads.
2. **Analytics Telemetry:** Usage data sent to a third-party SaaS analytics provider. *(Identified as Risk RSK-004 due to missing Data Processing Agreements).*
3. **SMS Notification Gateway:** Customer phone numbers transmitted to an external SMS vendor for payment confirmation codes.

## 3. Trust Boundaries & Identified Exposure Points
* **Boundary 1 (External to Cloud):** Encrypted via TLS 1.3. Secure.
* **Boundary 2 (Developer Workstations to Staging):** Identified security gap. Remote engineers connecting to staging environments without mandatory hardware MFA or device compliance checks.
* **Boundary 3 (Internal to Third-Party SaaS):** Unvetted transfer of telemetry data without executed GDPR Article 28 Data Processing Agreements (DPAs).
