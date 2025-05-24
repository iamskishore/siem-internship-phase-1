# Brute-Force RDP Attack Scenario with Detection and Alerting
## Objective

Simulate a real-world brute-force RDP attack where an attacker attempts multiple failed logins and later succeeds using valid admin credentials. The goal is to detect the attack and generate an alert when a **successful login occurs within 5 minutes of 10+ failed login attempts** from the same source.

## Event ID–based Detection Rules in Elastic Security

### What is event ID 

In Windows, an Event ID is a unique numerical identifier assigned to specific events logged in the Windows Event Log.  It helps administrators identify and understand the nature of a logged event, providing a specific description of what occurred
[Microsoft Docs - Event ID 4624 & 4625](https://learn.microsoft.com/en-us/answers/questions/1529208/event-id-ad-account-login)
[Ultimate Windows Security - Event ID 4624](https://www.ultimatewindowssecurity.com/securitylog/encyclopedia/event.aspx?eventid=4624)

## Rule Setup in  Kibana

![RDP Rule Screenshot](screenshots/set-rule-rdp-dec.png)


# Attack Simulation

The following command was run on **Attacker System** to Brute Force RDP protocal
```sh
➜  ~ nxc rdp 54.145.192.180 -u 'Administrator' -p passwords.txt
```
This try to enumerate password of the administrator, If the credentials are incorrect or access is denied, **Windows logs Event ID 4625**, indicating a failed login.

## Detections in Elastic Kibana

This detection highlights potential brute-force behavior by tracking accounts or IPs with over 5 failed logins in a short time frame. It enables SOC teams to swiftly detect and respond to unauthorized access attempts.

![](screenshots/Detection-rdp.png)


