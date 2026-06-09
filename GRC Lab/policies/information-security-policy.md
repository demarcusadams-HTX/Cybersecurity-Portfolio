# Information Security Policy

**Organization:** Apex Property Management  
**Policy ID:** ISP-001  
**Version:** 1.0  
**Effective Date:** June 2026  
**Review Date:** June 2027  
**Approved By:** Executive Leadership  
**Prepared By:** Demarcus Adams, IT Systems & Compliance  
**Classification:** Internal Use

---

## 1. Purpose

This Information Security Policy establishes the framework for protecting the confidentiality, integrity, and availability of Apex Property Management's information assets, including tenant personally identifiable information (PII), financial records, lease agreements, and vendor data. This policy reflects our commitment to responsible data stewardship and compliance with applicable regulations.

---

## 2. Scope

This policy applies to:
- All full-time and part-time employees of Apex Property Management
- Contractors, vendors, and third parties with access to company systems or data
- All information systems, networks, and devices owned or operated by the organization
- All data processed, stored, or transmitted on behalf of the organization

---

## 3. Policy Statements

### 3.1 Access Control

- Access to information systems and data shall be granted on a **least-privilege basis**, providing only the minimum access required to perform job functions.
- All user accounts shall be **uniquely assigned** to individuals. Shared accounts are prohibited.
- **Multi-factor authentication (MFA)** is required for all access to critical business applications, remote access, and administrative accounts.
- Access rights shall be reviewed **quarterly** and revoked immediately upon employee separation.
- A formal **Role-Based Access Control (RBAC)** model shall be implemented and maintained.

### 3.2 Password Management

- All passwords must meet the following minimum requirements:
  - Minimum length: 12 characters
  - Must include: uppercase, lowercase, number, and special character
  - Must not reuse the last 12 passwords
  - Must be changed every 90 days for standard accounts; 60 days for privileged accounts
- An **enterprise password manager** shall be provided to all employees.
- Password sharing is strictly prohibited.

### 3.3 Data Classification and Handling

Data shall be classified into the following categories:

| Classification | Description | Examples |
|---------------|-------------|---------|
| Confidential | Highly sensitive; restricted access | Tenant SSNs, payment data, lease financials |
| Internal | Business use only; not for public disclosure | Employee records, vendor contracts, internal policies |
| Public | Approved for public release | Marketing materials, job postings |

- Confidential data shall be **encrypted at rest and in transit**.
- Confidential data shall not be transmitted via personal email, personal cloud storage, or unencrypted messaging applications.

### 3.4 Acceptable Use

- Company-owned devices and systems shall be used **primarily for business purposes**.
- Employees shall not install unauthorized software on company devices.
- Employees shall not access, copy, or transmit company data to personal devices or accounts without written authorization.
- Accessing, storing, or transmitting illegal content using company resources is strictly prohibited.

### 3.5 Incident Response

- All suspected security incidents shall be **reported immediately** to IT Management at security@apexpm.com.
- Employees shall not attempt to investigate or remediate security incidents independently.
- A formal **Incident Response Plan** shall be maintained, tested annually, and made available to relevant staff.
- All incidents shall be logged, categorized, and reviewed for lessons learned.

### 3.6 Third-Party and Vendor Risk

- All vendors with access to company systems or data must complete a **security risk assessment questionnaire** prior to engagement.
- Vendor contracts must include data protection requirements, breach notification obligations, and right-to-audit clauses.
- Vendor access shall be reviewed **annually** and revoked when the business relationship ends.

### 3.7 Business Continuity and Disaster Recovery

- Critical business data shall be backed up **daily**, with backups stored in a secure, geographically separated location.
- Backup restoration shall be **tested quarterly**.
- A **Business Continuity and Disaster Recovery Plan** shall be maintained, reviewed annually, and tested via tabletop exercise.
- Recovery Time Objective (RTO): **4 hours** for critical systems.
- Recovery Point Objective (RPO): **24 hours** for all business data.

### 3.8 Physical Security

- Access to server rooms and network infrastructure shall be restricted to **authorized IT staff only**, enforced via badge-controlled access.
- All access to restricted areas shall be **logged and reviewed monthly**.
- Unattended workstations shall be locked after **5 minutes of inactivity**.
- Visitors to the office must be **escorted** at all times and must sign in/out at reception.

### 3.9 Security Awareness and Training

- All employees shall complete **security awareness training** within 30 days of hire and **annually** thereafter.
- Employees in IT and compliance roles shall complete **role-specific security training** relevant to their responsibilities.
- A **phishing simulation program** shall be conducted at least **twice annually** to assess and reinforce employee awareness.

---

## 4. Roles and Responsibilities

| Role | Responsibility |
|------|---------------|
| Executive Leadership | Approve and sponsor this policy; allocate resources for security initiatives |
| IT Manager | Implement and maintain technical controls; manage incident response |
| Compliance Officer | Maintain policy documentation; conduct audits; manage vendor risk |
| All Employees | Read, understand, and comply with this policy; report suspected incidents |
| HR Department | Integrate security requirements into onboarding and offboarding processes |

---

## 5. Compliance and Enforcement

Violations of this policy may result in disciplinary action up to and including termination of employment, and where applicable, referral to law enforcement. Third parties found in violation may have their access revoked and contracts terminated.

---

## 6. Exceptions

Exceptions to this policy must be:
1. Submitted in writing to the IT Manager and Compliance Officer
2. Documented with business justification and risk acceptance
3. Approved by Executive Leadership
4. Reviewed at least **annually**

---

## 7. Related Documents

- Incident Response Plan (IRP-001) — *In Development*
- Business Continuity and Disaster Recovery Plan (BCP-001) — *In Development*
- Acceptable Use Policy (AUP-001) — *In Development*
- Vendor Risk Assessment Questionnaire (VRA-001) — *In Development*
- Password Policy (embedded in Section 3.2 above)

---

## 8. References

- NIST Cybersecurity Framework (CSF) 2.0
- NIST SP 800-53 Rev. 5 — Security and Privacy Controls
- NIST SP 800-30 Rev. 1 — Risk Assessment Guide
- CIS Controls v8

---

## 9. Policy Review and Revision History

| Version | Date | Author | Summary of Changes |
|---------|------|--------|--------------------|
| 1.0 | June 2026 | Demarcus Adams | Initial policy draft and publication |

*This policy shall be reviewed annually or following any significant security incident or organizational change.*
