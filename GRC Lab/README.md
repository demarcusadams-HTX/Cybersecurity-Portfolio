# GRC Lab — Governance, Risk & Compliance Assessment

## Objective
Conduct a comprehensive GRC assessment for a simulated mid-size organization (Apex Property Management) using industry-standard frameworks. This lab demonstrates the ability to identify and score information security risks, map controls to NIST CSF 2.0, perform a compliance gap analysis, and author foundational security governance documentation.

---

## Scenario
**Organization:** Apex Property Management (fictional)  
**Industry:** Real Estate / Property Management  
**Size:** ~200 employees, 3 office locations, Houston TX  
**Data Assets:** Tenant PII, financial records, lease agreements, vendor contracts  
**Assessment Scope:** Full information security risk and compliance posture review

---

## Lab Structure

```
GRC-Lab/
├── README.md                        ← This file
├── risk-assessment-report.md        ← Full NIST SP 800-30 risk assessment
├── risk-register.md                 ← 10-risk register with CVSS scoring
├── nist-csf-mapping.md              ← NIST CSF 2.0 controls mapping & gap analysis
├── policies/
│   └── information-security-policy.md  ← Drafted InfoSec governance policy
└── screenshots/
    ├── 01_risk_heat_map.png
    ├── 02_risk_register.png
    ├── 03_nist_csf_maturity.png
    ├── 04_compliance_gap_analysis.png
    └── 05_executive_dashboard.png
```

---

## Key Findings

| Finding | Detail |
|---------|--------|
| Total Risks Identified | 10 |
| Critical Risks | 1 — Phishing / Credential Theft (Score: 20) |
| High Risks | 3 — Ransomware, Unauthorized PII Access, No MFA |
| Overall NIST CSF Compliance | 35% (31/88 controls implemented) |
| Lowest Maturity Functions | Respond (1.0) and Recover (1.0) |
| Priority Actions | 4 immediate P1 remediation items |

---

## Frameworks & Standards Applied

| Framework | Purpose |
|-----------|---------|
| NIST SP 800-30 r1 | Risk Assessment Methodology |
| NIST CSF 2.0 | Security Controls Mapping & Gap Analysis |
| NIST SP 800-53 r5 | Control Reference for Recommendations |
| CIS Controls v8 | Supplemental Implementation Guidance |
| CVSS v3.1 | Vulnerability / Risk Scoring |

---

## Skills Demonstrated
- Information security risk identification and scoring (NIST SP 800-30)
- Risk register development and maintenance
- NIST CSF 2.0 controls mapping and maturity assessment
- Compliance gap analysis and remediation planning
- Security policy authoring (governance documentation)
- Executive-level risk communication and reporting

---

## MITRE ATT&CK / Risk Coverage

| Risk | Category | Relevant ATT&CK Techniques |
|------|----------|---------------------------|
| Phishing | Initial Access | T1566 — Phishing |
| Ransomware | Impact | T1486 — Data Encrypted for Impact |
| Unauthorized PII Access | Collection | T1530 — Data from Cloud Storage |
| No MFA | Credential Access | T1078 — Valid Accounts |
| Insider Threat | Exfiltration | T1048 — Exfiltration Over Alt Protocol |

---

## Screenshots
See [`screenshots/`](./screenshots/) for visual outputs including the risk heat map, risk register dashboard, NIST CSF maturity comparison, compliance gap analysis, and executive summary dashboard.

---

## Full Documentation
- [Risk Assessment Report →](./risk-assessment-report.md)
- [Risk Register →](./risk-register.md)
- [NIST CSF 2.0 Mapping →](./nist-csf-mapping.md)
- [Information Security Policy →](./policies/information-security-policy.md)
