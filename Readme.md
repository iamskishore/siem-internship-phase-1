# SIEM Internship – Phase 1: Sysmon Setup & Log Collection

## **Welcome to the SOC Internship Program**

 I’m excited to begin this journey into the world of cybersecurity. This program offers a unique opportunity to gain hands-on experience in monitoring, detecting, and responding to security incidents just like a real SOC analyst.

#### Objective of Phase 1
The main goals of this phase are to:
-  Setup Your SOC Lab
	- Install and configure a virtual lab environment.
	- Use tools like SIEM (Security Information and Event Management), firewalls, and endpoint detection systems.
-  Simulate Basic Attacks
	- Generate common attack scenarios (e.g., brute force, malware, phishing).
	- Understand how attackers operate and how systems respond.
- Configure Log Sources
	 - Enable and collect logs from key sources: endpoints, network devices, and cloud services
	 - Understand log types and relevance for threat detection.
- Detect Real Threats
	- Use your SOC setup to identify Indicators of Compromise (IOCs).
	- Practice correlating log data to discover security incidents

## What is SIEM?

SIEM (Security Information and Event Management) is a security solution that provides real-time visibility into an organization’s IT environment. It collects, aggregates, and analyzes log data from various systems to detect suspicious behavior, trigger alerts, and support incident response. A SIEM acts as the central nervous system of a Security Operations Center (SOC), enabling security teams to identify, prioritize, and respond to potential threats more efficiently

## Real-World Use Cases of SIEM
- Log Collection
	- Gathers logs from endpoints, servers, firewalls, applications, cloud services, and more.
	- Standardizes and centralizes data for easier analysis.
- Alerting
	 - Detects anomalies or known attack patterns using predefined rules or machine learning.
	 - Sends real-time alerts to analysts for immediate attention.
- Correlation
	-  Connects related events across multiple systems to reveal the full scope of an attack.
	- Example: A failed login attempt + privilege escalation + data exfiltration = Possible insider threat.
## Tools Used

- Windows Virtual Machine (VM) in AWS(EC2)
- **Sysmon** – System Monitor for Sysinternals
- Elastic Stack (Elasticsearch + Kibana + Logstash)
- Elastic Agent 

## Steps Performed

In this lab environment, a VMware hypervisor hosts virtual machines, including a **Kali Linux attacker machine** and **Windows victim machines**. Using Kali, various attacks are simulated to generate logs on the Windows machines, where **Sysmon** is pre-configured for detailed system activity monitoring. These logs are collected and forwarded using **Elastic Agent** (or Winlogbeat) to an **Elastic Stack (ELK)** instance, where **Elasticsearch** stores the data and **Kibana** provides visualization and analysis. The purpose is to simulate real-world attack scenarios and observe system behavior through log correlation and threat detection dashboards. This setup is inspired by the lab guide available at [Intro to ELK in the Cloud – IntroClass by Josh Stroschein](https://github.com/strandjs/IntroLabs/blob/master/IntroClassFiles/Tools/IntroClass/md/elk_in_the_cloud.md).

## Use Cases

1. [ RDP Brute Force Detection](<writeups/Use Case 1 Brute Force Detection/Readme.md>)
	Techniques: Credential stuffing, repeated failed login attempts Event ID: `4625` (Failed login – Windows Security Log) Tools: Hydra, CrackMapExec
	Goal: Detect brute force attacks by identifying multiple failed login attempts against valid or invalid user accounts.
	