

| Technique ID | Technique Name                    |
| ------------ | --------------------------------- |
| T1190        | Exploit Public-Facing Application |
| T1595        | Active Scanning                   |
| T1110        | Brute Force (Web Login Abuse)     |


Disclaimer

This lab was conducted in an isolated environment for educational purposes only.



---

# 🛡️ MITRE ATT&CK Mapping 

```markdown
# MITRE ATT&CK Mapping – DVWA SOC Lab

## T1190 – Exploit Public-Facing Application
**Evidence:**
- Access to `/dvwa/vulnerabilities/sqli/`
- SQL injection payloads
- curl-based requests

## T1595 – Active Scanning
**Evidence:**
- Repeated crafted HTTP requests
- Enumeration of vulnerable endpoints

## T1110 – Brute Force (Web Context)
**Evidence:**
- Repeated login attempts
- Abuse of authentication mechanisms
