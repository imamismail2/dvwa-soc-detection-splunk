
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


## Field Extraction (When URI Fields Were Missing)

| rex field=_raw "^(?<clientip>\d{1,3}(?:\.\d{1,3}){3})\s"
| rex field=_raw "\"(?<method>\w+)\s+(?<uri>\S+)\s+HTTP\/"
