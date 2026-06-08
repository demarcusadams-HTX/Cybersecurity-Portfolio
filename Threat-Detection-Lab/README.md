# Threat Detection Lab — Splunk SIEM & Brute-Force Detection

## Objective
Simulate a brute-force attack against a Windows target in a controlled lab environment, ingest the resulting logs into Splunk, detect the attack using custom SPL queries, and build a real-time alerting dashboard for threat visibility.

---

## Lab Environment

| Role      | System         | IP Address      |
|-----------|----------------|-----------------|
| Attacker  | Kali Linux     | 192.168.1.100   |
| Target    | Windows 10 VM  | 192.168.1.105   |
| SIEM      | Splunk Free    | 192.168.1.105   |

---

## Tools Used
- **Splunk** — log ingestion, SPL query-based detection, dashboard creation
- **Nmap** — network reconnaissance and open port identification
- **Hydra** — brute-force simulation against RDP
- **Windows Event Viewer** — raw log verification (Event IDs 4625, 4624, 4648)

---

## Key Findings

- **3 high-risk open ports** identified on the target (135, 445, 3389)
- **47 failed login attempts** (Event ID 4625) recorded within a 4-minute window
- Brute-force pattern confirmed via source IP concentration in Splunk
- Custom SPL alert rule created to flag accounts with >10 failed attempts per 5-minute window
- Successful detection and simulated containment documented

---

## Skills Demonstrated
- SIEM log ingestion and querying (Splunk SPL)
- Network reconnaissance (Nmap service/version scanning)
- Brute-force attack simulation and detection
- Windows Security Event Log analysis
- Alert rule creation and dashboard configuration
- Incident documentation and remediation planning

---

## MITRE ATT&CK Mapping

| Technique ID | Technique Name             | Tactic           |
|--------------|----------------------------|------------------|
| T1046        | Network Service Discovery  | Discovery        |
| T1110.001    | Brute Force: Password Guessing | Credential Access |
| T1021.001    | Remote Services: RDP       | Lateral Movement |

---

## Full Report
See [`report.md`](./report.md) for complete methodology, SPL queries, findings, and screenshots.
