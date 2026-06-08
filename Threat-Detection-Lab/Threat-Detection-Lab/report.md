# Threat Detection Lab — Full Report

**Author:** Demarcus Adams  
**Date:** June 2026  
**Credential Context:** ISC2 Certified in Cybersecurity (CC) | WGU M.S. Cybersecurity & Information Assurance (In Progress)

---

## 1. Objective

Simulate a real-world brute-force attack in an isolated lab environment, detect the attack using Splunk SIEM, and document the full incident detection lifecycle — from reconnaissance through alerting and remediation recommendations.

---

## 2. Environment Setup

| Role     | System        | IP Address    | Notes                        |
|----------|---------------|---------------|------------------------------|
| Attacker | Kali Linux    | 192.168.1.100 | Nmap, Hydra pre-installed    |
| Target   | Windows 10 VM | 192.168.1.105 | RDP enabled, Splunk Universal Forwarder installed |
| SIEM     | Splunk Free   | 192.168.1.105 | Receiving Windows Security Event Logs |

All systems ran within an isolated VirtualBox network segment with no external internet routing during the simulation.

---

## 3. Methodology

### Phase 1 — Network Reconnaissance

**Tool:** Nmap  
**Command:**
```bash
nmap -sV -p 1-1000 192.168.1.105
```

**Output Summary:**

```
PORT    STATE  SERVICE        VERSION
135/tcp open   msrpc          Microsoft Windows RPC
139/tcp open   netbios-ssn    Microsoft Windows netbios-ssn
445/tcp open   microsoft-ds   Windows 10 microsoft-ds
3389/tcp open  ms-wbt-server  Microsoft Terminal Services (RDP)
```

**Assessment:** Port 3389 (RDP) open on the target significantly increases the attack surface. RDP is a common vector for brute-force and credential-stuffing attacks.

---

### Phase 2 — Brute-Force Simulation

**Tool:** Hydra  
**Command:**
```bash
hydra -l administrator -P /usr/share/wordlists/rockyou.txt rdp://192.168.1.105 -t 4
```

**Result:** 47 failed authentication attempts were generated against the Administrator account over a 4-minute window before the simulation was manually stopped.

---

### Phase 3 — Log Ingestion & Detection (Splunk)

Windows Security Event Logs were forwarded to Splunk via the Universal Forwarder. The following Event IDs were monitored:

| Event ID | Description                         |
|----------|-------------------------------------|
| 4625     | An account failed to log on         |
| 4624     | An account successfully logged on   |
| 4648     | Logon attempt using explicit credentials |

**SPL Query — Detect Brute-Force Pattern:**
```spl
index=windows EventCode=4625
| stats count by Account_Name, src_ip, host
| where count > 10
| sort - count
```

**SPL Query — Timeline of Failed Attempts:**
```spl
index=windows EventCode=4625 Account_Name="Administrator"
| timechart span=1m count as "Failed Logins"
```

**SPL Query — Flag Accounts Exceeding Threshold in 5-Minute Window:**
```spl
index=windows EventCode=4625
| bucket _time span=5m
| stats count by _time, Account_Name, src_ip
| where count >= 10
```

---

### Phase 4 — Alert Rule & Dashboard

An alert was configured in Splunk to trigger when any account registered 10 or more failed logins within a 5-minute window. A dashboard was built with the following panels:

- **Failed Login Count by Source IP** (bar chart)
- **Failed Login Timeline** (line chart, 1-minute buckets)
- **Top Targeted Accounts** (table)
- **Logon Success vs. Failure Ratio** (pie chart)

> 📸 See `/screenshots/` folder for Splunk dashboard and alert configuration captures.

---

## 4. Findings

| Finding | Detail |
|--------|--------|
| Open high-risk port | Port 3389 (RDP) exposed on target system |
| Attack volume | 47 failed login attempts (Event ID 4625) in ~4 minutes |
| Source concentration | All failed attempts originated from single IP: 192.168.1.100 |
| Target account | Administrator account exclusively targeted |
| Detection time | Alert triggered after 2 minutes, 14 seconds from attack onset |
| MITRE mapping | T1110.001 — Brute Force: Password Guessing |

---

## 5. Analysis

The pattern of rapid, repeated failed authentication attempts from a single external IP against a privileged account (Administrator) is consistent with an automated credential brute-force attack. The concentration of Event ID 4625 records within a narrow timeframe is a reliable indicator of compromise (IoC) for this attack type.

The open RDP port (3389) served as the primary attack vector. Without network segmentation or an account lockout policy in place, the target was highly susceptible to this attack pattern. The Splunk alert successfully flagged the anomaly within the first 2 minutes of activity, demonstrating the effectiveness of threshold-based alerting for brute-force detection.

---

## 6. Recommendations

| Priority | Recommendation | Rationale |
|----------|---------------|-----------|
| High | Disable public-facing RDP or restrict to VPN only | Eliminates primary attack vector |
| High | Implement account lockout policy (e.g., 5 attempts / 15-min lockout) | Breaks automated credential attacks |
| Medium | Enable Network Level Authentication (NLA) for RDP | Adds pre-authentication layer |
| Medium | Deploy Splunk alert with automated response (e.g., block IP via firewall rule) | Reduces mean time to respond (MTTR) |
| Low | Rename default Administrator account | Reduces target visibility for automated scanners |
| Low | Enable MFA on all remote access points | Mitigates credential-only attacks |

---

## 7. MITRE ATT&CK Framework Mapping

| Technique ID | Name | Tactic | Observed In Lab |
|---|---|---|---|
| T1046 | Network Service Discovery | Discovery | Nmap scan of target |
| T1110.001 | Brute Force: Password Guessing | Credential Access | Hydra RDP attack |
| T1021.001 | Remote Services: RDP | Lateral Movement | RDP as attack vector |

---

## 8. Conclusion

This lab demonstrated end-to-end threat detection using a SIEM environment. The simulation confirmed that threshold-based alerting in Splunk can reliably detect brute-force activity in near real-time. The combination of network reconnaissance, attack simulation, log analysis, and dashboard visualization reflects core competencies in security monitoring and incident detection aligned with the ISC2 CC domains of Security Operations and Network Security.
