# Risk Register — Apex Property Management

**Assessor:** Demarcus Adams  
**Date:** June 2026  
**Methodology:** NIST SP 800-30 Rev. 1  
**Scoring:** Likelihood (1–5) × Impact (1–5) = Risk Score  
**Rating Scale:** Low (1–6) | Medium (7–12) | High (13–19) | Critical (20–25)

---

## Risk Register

### R-01 — Phishing Attack Leading to Credential Theft

| Field | Detail |
|-------|--------|
| **Risk ID** | R-01 |
| **Category** | Access Control / Social Engineering |
| **Likelihood** | 4 — Likely |
| **Impact** | 5 — Catastrophic |
| **Risk Score** | **20 — CRITICAL** |
| **Description** | Employees receive phishing emails that capture login credentials, granting attackers access to tenant PII, financial systems, and internal communications. |
| **Current Controls** | Annual security awareness reminder email (informal) |
| **Control Gap** | No formal phishing simulation program, no MFA enforced, no email filtering solution |
| **Recommended Treatment** | Deploy phishing simulation platform; enforce MFA; implement email gateway with SPF/DKIM/DMARC |
| **Owner** | IT Manager |
| **Status** | Open |
| **MITRE ATT&CK** | T1566 — Phishing |

---

### R-02 — Ransomware Attack on Core Property Management Systems

| Field | Detail |
|-------|--------|
| **Risk ID** | R-02 |
| **Category** | Malware / Business Disruption |
| **Likelihood** | 3 — Possible |
| **Impact** | 5 — Catastrophic |
| **Risk Score** | **15 — HIGH** |
| **Description** | Ransomware delivered via phishing or unpatched vulnerability encrypts critical systems including lease management, payment processing, and tenant records, halting operations. |
| **Current Controls** | Antivirus (legacy, signature-based); irregular manual backups |
| **Control Gap** | No EDR solution; backups not tested; no offline/immutable backup copy |
| **Recommended Treatment** | Deploy EDR; implement 3-2-1 backup strategy with immutable offsite copy; test recovery quarterly |
| **Owner** | IT Manager |
| **Status** | In Progress |
| **MITRE ATT&CK** | T1486 — Data Encrypted for Impact |

---

### R-03 — Unauthorized Access to Tenant PII

| Field | Detail |
|-------|--------|
| **Risk ID** | R-03 |
| **Category** | Data Privacy / Access Control |
| **Likelihood** | 4 — Likely |
| **Impact** | 4 — Major |
| **Risk Score** | **16 — HIGH** |
| **Description** | Overpermissioned user accounts allow employees to access tenant records beyond their job function. Combined with weak password practices, this creates significant data exposure and potential regulatory liability. |
| **Current Controls** | Basic user accounts created per hire; no formal access review process |
| **Control Gap** | No RBAC policy; no access review schedule; no audit logging on tenant data access |
| **Recommended Treatment** | Implement RBAC; conduct quarterly access reviews; enable audit logging; classify data by sensitivity |
| **Owner** | Compliance Officer |
| **Status** | Open |
| **MITRE ATT&CK** | T1078 — Valid Accounts |

---

### R-04 — No Multi-Factor Authentication on Critical Applications

| Field | Detail |
|-------|--------|
| **Risk ID** | R-04 |
| **Category** | Access Control |
| **Likelihood** | 4 — Likely |
| **Impact** | 4 — Major |
| **Risk Score** | **16 — HIGH** |
| **Description** | Critical business applications (property management system, email, financial portal) are protected by passwords only. Stolen credentials grant immediate unrestricted access. |
| **Current Controls** | Password requirement (min 8 characters, no complexity enforced) |
| **Control Gap** | No MFA on any system; no SSO; no privileged access management |
| **Recommended Treatment** | Enforce MFA on all critical applications immediately; implement SSO with MFA; deploy PAM for admin accounts |
| **Owner** | IT Manager |
| **Status** | In Progress |
| **MITRE ATT&CK** | T1078 — Valid Accounts; T1110 — Brute Force |

---

### R-05 — Unpatched Software Vulnerabilities

| Field | Detail |
|-------|--------|
| **Risk ID** | R-05 |
| **Category** | Vulnerability Management |
| **Likelihood** | 3 — Possible |
| **Impact** | 4 — Major |
| **Risk Score** | **12 — MEDIUM** |
| **Description** | Workstations and servers are not patched on a consistent schedule. Known vulnerabilities in OS and third-party applications create exploitable attack vectors. |
| **Current Controls** | Windows Update enabled on some workstations; no centralized patch management |
| **Control Gap** | No patch management policy; no SLA for critical patches; no vulnerability scanning program |
| **Recommended Treatment** | Implement centralized patch management (e.g., WSUS, Automox); establish 30/60/90-day patch SLAs by severity; conduct quarterly vulnerability scans |
| **Owner** | IT Manager |
| **Status** | Open |
| **MITRE ATT&CK** | T1190 — Exploit Public-Facing Application |

---

### R-06 — Third-Party Vendor Data Breach

| Field | Detail |
|-------|--------|
| **Risk ID** | R-06 |
| **Category** | Third-Party Risk Management |
| **Likelihood** | 3 — Possible |
| **Impact** | 4 — Major |
| **Risk Score** | **12 — MEDIUM** |
| **Description** | Vendors with access to tenant data or internal systems (property software providers, maintenance contractors, payment processors) may experience a breach, exposing Apex data by extension. |
| **Current Controls** | Standard vendor contracts; no formal security review process |
| **Control Gap** | No vendor risk assessment questionnaire; no data processing agreements; no vendor security monitoring |
| **Recommended Treatment** | Implement vendor risk assessment program; require security questionnaires and SOC 2 reports; include right-to-audit clauses in contracts |
| **Owner** | Compliance Officer |
| **Status** | Open |
| **MITRE ATT&CK** | T1195 — Supply Chain Compromise |

---

### R-07 — Weak and Shared Password Practices

| Field | Detail |
|-------|--------|
| **Risk ID** | R-07 |
| **Category** | Access Control |
| **Likelihood** | 4 — Likely |
| **Impact** | 3 — Moderate |
| **Risk Score** | **12 — MEDIUM** |
| **Description** | Employees use weak, reused, or shared passwords for business systems. Staff turnover has resulted in former employee credentials remaining active in some systems. |
| **Current Controls** | Informal guidance to "use strong passwords" |
| **Control Gap** | No formal password policy; no password manager deployed; no offboarding checklist enforced |
| **Recommended Treatment** | Publish formal Password Policy; deploy enterprise password manager; automate account deprovisioning on offboarding |
| **Owner** | HR + IT Manager |
| **Status** | Closed — Password Policy published June 2026 |
| **MITRE ATT&CK** | T1110.001 — Brute Force: Password Guessing |

---

### R-08 — Insider Threat / Unauthorized Data Exfiltration

| Field | Detail |
|-------|--------|
| **Risk ID** | R-08 |
| **Category** | Insider Threat |
| **Likelihood** | 2 — Unlikely |
| **Impact** | 5 — Catastrophic |
| **Risk Score** | **10 — MEDIUM** |
| **Description** | A disgruntled or departing employee with broad data access could intentionally exfiltrate tenant PII, financial records, or proprietary business data before or after termination. |
| **Current Controls** | No monitoring in place |
| **Control Gap** | No DLP solution; no user behavior analytics; no data classification to identify sensitive assets |
| **Recommended Treatment** | Implement DLP policy and tooling; conduct data classification; establish employee offboarding data access revocation checklist; log and monitor privileged user activity |
| **Owner** | HR + IT Manager |
| **Status** | Open |
| **MITRE ATT&CK** | T1048 — Exfiltration Over Alternative Protocol |

---

### R-09 — No Tested Disaster Recovery Plan

| Field | Detail |
|-------|--------|
| **Risk ID** | R-09 |
| **Category** | Business Continuity / DR |
| **Likelihood** | 2 — Unlikely |
| **Impact** | 5 — Catastrophic |
| **Risk Score** | **10 — MEDIUM** |
| **Description** | In the event of a ransomware attack, natural disaster, or critical system failure, the organization has no documented or tested plan for recovering operations. This could result in extended downtime and significant financial loss. |
| **Current Controls** | Informal manual backups on some systems |
| **Control Gap** | No DR plan document; no RTO/RPO defined; no DR testing; backups not validated |
| **Recommended Treatment** | Develop Business Continuity and DR Plan; define RTO (4 hrs) and RPO (24 hrs); conduct annual tabletop exercise; test backup restoration quarterly |
| **Owner** | Executive Leadership |
| **Status** | Open |
| **MITRE ATT&CK** | T1486 — Data Encrypted for Impact (business impact) |

---

### R-10 — Physical Access to Server Room

| Field | Detail |
|-------|--------|
| **Risk ID** | R-10 |
| **Category** | Physical Security |
| **Likelihood** | 2 — Unlikely |
| **Impact** | 3 — Moderate |
| **Risk Score** | **6 — LOW** |
| **Description** | The server room / network closet at the main office does not have a dedicated access control mechanism. Physical access by unauthorized personnel could enable hardware tampering, device theft, or direct network access. |
| **Current Controls** | Office building access badge; server room door with standard lock |
| **Control Gap** | No dedicated badge reader on server room; no access log; no camera coverage |
| **Recommended Treatment** | Install badge reader with access log on server room; add CCTV camera coverage; restrict access to authorized IT staff only |
| **Owner** | Facilities Manager |
| **Status** | Closed — Badge reader installed May 2026 |
| **MITRE ATT&CK** | T1200 — Hardware Additions |

---

## Risk Summary

![Risk Register Dashboard](screenshots/02_risk_register.png)

![Risk Heat Map](screenshots/01_risk_heat_map.png)

| Rating | Count | Risk IDs |
|--------|-------|----------|
| Critical | 1 | R-01 |
| High | 3 | R-02, R-03, R-04 |
| Medium | 5 | R-05, R-06, R-07, R-08, R-09 |
| Low | 1 | R-10 |
