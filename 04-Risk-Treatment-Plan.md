# 🛠️ NovaPay Inc. — Risk Treatment & Corrective Action Plan (CAPA)

**Framework Alignment:** ISO/IEC 27001:2022 Clauses 8.9, 10.1 & 10.2 | SOC 2 CC7.3  
**Author:** P.V. Mohlala, Lead GRC Analyst  
**Version:** 1.0 (Final)  

---

## 1. Executive Purpose
This document establishes NovaPay Inc.’s Risk Treatment and Corrective Action Plan (CAPA) following the Q4 Information Security Risk Assessment. It outlines the phased remediation roadmap, defines operational Service Level Agreements (SLAs) based on risk severity, assigns single-point accountability, and details the evidence required to formally close identified risk items.

---

## 2. Remediation SLAs & Governance Escalation

Risks identified in the Enterprise Risk Register (`03-Risk-Register.md`) are subject to mandatory operational SLAs based on their inherent risk score:

| Risk Level | Score Range | Mandatory SLA | Governance Escalation Pathway |
| :---: | :---: | :---: | :--- |
| **CRITICAL** | **20 – 25** | **15 Calendar Days** | Immediate notification to CEO, CISO, and Board Audit Committee. Daily standups until contained. |
| **HIGH** | **12 – 19** | **30 Calendar Days** | Escalation to VP of Engineering and Legal Counsel. Weekly progress tracking. |
| **MEDIUM** | **6 – 11** | **90 Calendar Days** | Escalation to Department Head. Bi-weekly review. |
| **LOW** | **1 – 5** | **180 Days / Accept** | Annual review by Lead GRC Analyst. |

---

## 3. Phased Remediation Roadmap

PHASE 1: Immediate Critical Quick Wins (Days 1 – 15)
-RSK-001: GitHub Secret Scanning & AWS Secrets Manager Deployment 

-RSK-002: Enforce BitLocker / FileVault Full-Disk Encryption via MDM 

-RSK-004: Formal Appointment of Data Protection Officer (DPO) & UK ICO Registration 

PHASE 2: High-Priority Controls & Vendor Remediation (Days 16 – 30)

├── RSK-003: Mandatory FIDO2/TOTP Hardware MFA Rollout across Okta & AWS

├── RSK-005: Publication of Master IR Plan & Tabletop Scenario Testing

├── RSK-006: Execution of GDPR Article 28 DPAs with Tier 1 SaaS Vendors

└── RSK-007: Enable Global AWS S3 "Block Public Access" & AWS Config Rules

PHASE 3: Operational Hardening & Audit Preparation (Days 31 – 90)
├── RSK-008: Documented Database Backup Restoration Verification Testing
└── RSK-009: Automated HRIS-to-Okta Offboarding Connector & Access Reviews

PHASE 4: Formal Risk Acceptance & Annual Review
── RSK-010: Remote Working Workspace Security Guidance & Formal Risk Acceptance.


---

## 4. Action Item Breakdown & Required Closure Evidence

### Phase 1: Critical Priorities (15-Day SLA)

#### 🔹 Action 1.1: Cloud API Key Protection (RSK-001)
* **Risk Score:** 20 (Critical) ➔ **Target Residual:** 6 (Medium)
* **Action Steps:**
  1. Enable GitHub Advanced Security automated secret scanning across all private repositories.
  2. Migrate hardcoded Stripe and database API credentials to AWS Secrets Manager.
  3. Rotate all existing staging and production API access keys.
* **Owner:** DevOps Lead
* **Required Closure Evidence:** Screenshot of GitHub Secret Scanning configuration showing zero active alerts + AWS Secrets Manager deployment logs.

#### 🔹 Action 1.2: Endpoint Full-Disk Encryption (RSK-002)
* **Risk Score:** 20 (Critical) ➔ **Target Residual:** 4 (Low)
* **Action Steps:**
  1. Enforce BitLocker (Windows) and FileVault (macOS) compliance policies via Intune MDM.
  2. Audit 35 developer workstations and remotely encrypt non-compliant devices.
* **Owner:** IT Operations Lead
* **Required Closure Evidence:** Exported MDM compliance report verifying 100% endpoint encryption status across active devices.

#### 🔹 Action 1.3: Data Protection Governance (RSK-004)
* **Risk Score:** 20 (Critical) ➔ **Target Residual:** 3 (Low)
* **Action Steps:**
  1. Formally designate internal virtual Data Protection Officer (vDPO).
  2. Register DPO contact details on the UK Information Commissioner's Office (ICO) portal.
* **Owner:** Legal Counsel / CISO
* **Required Closure Evidence:** Official UK ICO registration confirmation certificate + updated privacy policy naming the DPO.

---

### Phase 2: High Priorities (30-Day SLA)

#### 🔹 Action 2.1: Hardware MFA Enforcement (RSK-003)
* **Risk Score:** 20 (Critical) ➔ **Target Residual:** 6 (Medium)
* **Action Steps:** Enforce WebAuthn/FIDO2 hardware keys or TOTP authentication across Okta SSO, AWS IAM, and GitHub. Disable SMS/Email OTP.
* **Owner:** IT Manager | **Evidence:** Okta Sign-On Policy log confirming MFA enforcement for 100% of active users.

#### 🔹 Action 2.2: Incident Response Plan & Tabletop Testing (RSK-005)
* **Risk Score:** 20 (Critical) ➔ **Target Residual:** 6 (Medium)
* **Action Steps:** Publish Master Incident Response Plan, establish 72-hour GDPR reporting workflows, and conduct a simulated phishing tabletop exercise.
* **Owner:** Lead GRC Analyst | **Evidence:** Approved IR Plan PDF + Signed Tabletop Simulation Report ("Operation Credential Exfiltrate").

#### 🔹 Action 2.3: Vendor DPA Execution (RSK-006)
* **Risk Score:** 12 (High) ➔ **Target Residual:** 3 (Low)
* **Action Steps:** Execute GDPR Article 28 Data Processing Agreement (DPA) including Standard Contractual Clauses (SCCs) with SaaS Analytics provider.
* **Owner:** Procurement / Legal | **Evidence:** Fully executed DPA PDF signed by both NovaPay Inc. and Vendor Analytics Corp.

---

## 5. CAPA Verification & Verification Sign-Off

A risk item is marked as **"CLOSED"** in the Enterprise Risk Register only after independent verification by the Lead GRC Analyst.

```text
[Risk Identified] ➔ [Remediation Executed] ➔ [Evidence Submitted] ➔ [GRC Audit Verification] ➔ [CLOSED]

Sign-Off Block
Lead GRC Analyst: P.V. Mohlala — Status: Approved
CISO / VP of Engineering: Approved for Execution
Date: October 2026
