
Detected in Splunk access logs:

![DVWA SQLi Event](screenshots/dvwa_sqli_event.png)

---

## Detection Engineering

### SQL Injection Detection (Primary)
```spl
index=web sourcetype="xampp:apache:access"
| search "/dvwa/vulnerabilities/sqli/"
| eval attack_type="SQL Injection Attempt"
| stats count min(_time) as first_seen max(_time) as last_seen by clientip host useragent attack_type
| sort - count
