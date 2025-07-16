failed_logins_sample.csv
queries.txt
Screenshots/
├── dashboard_overview.png
├── failed_logins_table.png
└── failed_logins_timechart.png


Brute Force Login Detection using Splunk

# Brute Force Detection in Splunk
This project shows how to detect brute-force login attempts using Windows logs and Splunk queries.


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

2. Failed Login Attempts Over Time
index=windows EventCode=4625
| timechart span=30m count by user

✅ Outcome
This demonstrates beginner-friendly SOC skills:

Data ingestion

Threat detection

Dashboarding in Splunk

📸 Screenshots
See in the /Screenshots/ folder.

👩‍💻 Author
Rumbidzai Mutsengi | CompTIA Security+ Certified
Frankfurt, Germany
