# Suspicious Logon Times - After Hours Admin Activity
## Objective

Detect and alert on privileged account logins occurring outside defined business hours (9 AM–7 PM) using Elastic. This helps identify suspicious after-hours activity that could indicate unauthorized access or insider threats.
## Detection in Elastic Kibana

The search query identifies successful login events that occur **outside standard business hours (09:00–19:00)**. For example, if an attacker logs in at **20:45**, Elastic captures the event and flags it as an **after-hours administrative login**, indicating potentially suspicious activity.

### query
```sql
event.code: ("4624" or "4625") and user.name : "Administrator" AND (
  @timestamp < now/d + 9h OR 
  @timestamp >= now/d + 19h
)
```
![Suspicious logon time](screenshots/Suspicious-logon-time.png)
Elastic successfully identified and displayed the unauthorized login attempt, capturing key details such as the username, timestamp, and logon type. This confirms the effectiveness of the detection logic and highlights the critical role of time-based access controls in strengthening network security.