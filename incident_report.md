# SOC Incident Report

**Date:** June 1, 2026
**Analyst:** Varsha T
**Severity:** HIGH
**Status:** ESCALATED TO L2

## Incident Summary
Detected SSH brute force attack from multiple 
IP addresses. Port scanning, privilege 
escalation, DNS anomalies and Windows 
security events also identified.

## Findings
| Attack Type | Details |
|-------------|---------|
| SSH Brute Force | 15 failed attempts |
| Successful Logins | 2 accepted |
| Attacker IPs | 7 identified |
| Top Target | admin (6), root (5) |
| Port Scanning | 5 ports scanned |
| Windows Events | 5 event IDs detected |
| DNS Anomalies | Suspicious queries found |

## Attacker IPs
| IP | Attempts | Risk |
|----|----------|------|
| 192.168.1.1 | 6 | HIGH |
| 192.168.1.10 | 4 | HIGH |
| 192.168.1.3 | 2 | LOW |
| 192.168.1.4 | 2 | LOW |
| Others | 1 each | LOW |

## Recommended Actions
1. Block 192.168.1.1 immediately
2. Block 192.168.1.10 immediately
3. Reset all user passwords
4. Enable MFA on SSH
5. Review Windows event logs
6. Block suspicious DNS queries
7. Monitor for further attempts

## Tools Used
Splunk Cloud SIEM, SPL Query Language
