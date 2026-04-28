# Threat Detection Lab Report

## Objective
To simulate threat detection using a SIEM environment and identify suspicious activity.

## Environment
- Kali Linux (Attacker)
- Windows VM (Target)
- Splunk SIEM

## Methodology
A network scan was performed using Nmap to identify open ports and services. Logs were monitored using Splunk to detect unusual activity.

## Findings
- Open ports detected on target system
- Multiple login attempts observed
- Indicators of potential unauthorized access identified

## Analysis
The presence of open ports increases the attack surface. Repeated login attempts suggest possible brute-force activity.

## Recommendations
- Close unnecessary ports
- Implement account lockout policies
- Monitor logs continuously using SIEM tools

## Conclusion
This lab demonstrated the ability to detect and analyze potential security threats using SIEM tools and network scanning techniques.
