Brute Force Login Detection using Splunk

This mini project simulates brute-force attack detection using Windows Security Logs (EventCode 4625) in Splunk.

 Objective
Detect multiple failed login attempts by the same user or from the same host, indicating potential brute-force attacks.

Tools Used
- Splunk Enterprise (Free Trial)
- Sample CSV Log File (Windows EventCode 4625)
- SPL (Search Processing Language)

Data Source
Custom-made `.csv` log file simulating failed login events:
- `EventCode 4625`
- Timestamps from 08:00 to 09:05
- 2 sample users: `jdoe`, `asmith`
- Multiple login failures

Dashboards Created
1. **Users with Too Many Failed Logins**
```spl
index=windows EventCode=4625
| stats count by user, host
| where count > 2
