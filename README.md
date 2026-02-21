# DVWA SOC Detection Lab – Splunk SIEM

## Overview
This project demonstrates end-to-end SOC analyst and detection engineering skills using **Splunk Enterprise** to detect real-world web application attacks against **DVWA (Damn Vulnerable Web Application)**.

The lab simulates a realistic attack scenario where a Kali Linux host performs SQL injection attempts against a vulnerable web application hosted on Windows. Apache logs are ingested into Splunk using a Universal Forwarder and analyzed using SPL-based detections mapped to **MITRE ATT&CK**.

---

## Lab Architecture

![Architecture](architecture/lab-architecture.png)

### Components
- **Attacker:** Kali Linux (curl-based SQL injection)
- **Target:** Windows 10 + XAMPP + DVWA
- **SIEM:** Splunk Enterprise (Ubuntu)
- **Log Forwarding:** Splunk Universal Forwarder (Windows)

---

## Objectives
- Ingest Apache access/error logs into Splunk
- Troubleshoot Windows-based log ingestion issues
- Detect SQL Injection attempts using SPL
- Handle missing field extractions using `_raw` and `rex`
- Map detections to MITRE ATT&CK
- Produce SOC-ready incident documentation

---

## Log Ingestion Validation

Apache logs were successfully monitored and forwarded:

![Apache Logs Monitored](screenshots/apache_logs_ingested.png)

Confirmed in Splunk:

![Splunk Ingestion](screenshots/splunk_ingestion_confirmed.png)

---

## Attack Simulation

SQL injection attempts were generated from Kali using `curl` against DVWA:
