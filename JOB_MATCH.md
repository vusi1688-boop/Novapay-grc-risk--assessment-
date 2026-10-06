# 🎯 Job Requirement Evidence Mapping
**Candidate:** P.V. Mohlala  
**Target Role:** Junior GRC Analyst / Compliance Analyst  
**Project Context:** NovaPay Inc. (Fictional 120-person B2B Fintech SaaS)

This document maps standard entry-level GRC job requirements directly to artifacts created within this repository.

| Standard Job Description Requirement | Portfolio Evidence File | Specific Section / Artifact |
| :--- | :--- | :--- |
| **"Conduct information security risk assessments using established frameworks."** | `01-Scope-and-Methodology.md` | NIST SP 800-30 Rev. 1 Risk Assessment Framework, 5x5 Matrix, Likelihood & USD Impact Scales. |
| **"Maintain company risk register and track remediation with control owners."** | `03-Risk-Register.md`<br>`03-Risk-Register.csv` | 10 Risk scenarios with inherent scoring, assigned owners, treatment SLAs, and residual scores. CSV format provided for Excel workflows. |
| **"Map security controls to frameworks such as NIST CSF, ISO 27001, SOC 2, and GDPR."** | `03-Risk-Register.md` | Every risk row contains explicit cross-mapping columns for ISO 27001:2022, NIST CSF 2.0, SOC 2 TSC, and GDPR Articles. |
| **"Assist with third-party and vendor risk assessments."** | `02-Data-Flow-Analysis.md`<br>`03-Risk-Register.md` | Identification of unvetted SaaS telemetry vendor (Risk RSK-004), missing GDPR Art. 28 DPAs, and vendor remediation plan. |
| **"Prepare clear risk and compliance reporting for executive leadership."** | `05-Executive-Summary.md` | 1-Page non-technical executive brief containing business impact ($ USD), top 3 critical risks, and budget requests for CISO/Board. |
| **"Identify security control gaps and track Corrective Action Plans (CAPA)."** | `04-Risk-Treatment-Plan.md` | Prioritized 30/90/180-day SLA roadmap with zero-cost quick wins and required verification evidence before risk closure. |

---
*Note: This repository represents a simulated, end-to-end risk assessment for a fictional B2B SaaS startup created to demonstrate practical GRC execution capabilities.*
