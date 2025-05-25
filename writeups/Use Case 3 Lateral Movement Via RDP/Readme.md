# Lateral Movement Attempt Via RDP

## What is Lateral Movement?

  **Lateral movement** refers to the techniques that a cyberattacker uses, after gaining initial access, to move deeper into a network in search of sensitive data and other high-value assets. After entering the network, the attacker maintains ongoing access by moving through the compromised environment and obtaining increased privileges using various tools.
  Lateral movement is a key tactic that distinguishes today’s **advanced persistent threats (APTs)** from simplistic cyberattacks of the past.It allows a threat actor to avoid detection and retain access, even if discovered on the machine that was first infected. And with a protracted dwell time, data theft might not occur until weeks or even months after the original breach.

## Detecting and Preventing Lateral Movement

 Once an attacker secures administrative privileges and gains deeper access into a network, malicious lateral movement can be very difficult to detect because it can appear to be “normal” network traffic. Also, a human attacker has the ability to change plans and deploy different techniques and tools based on the information collected. And when the adversary utilizes built-in system tools, detection becomes even harder. It’s essential to find and remove these intruders as quickly as possible to avoid costly losses.
## Identifying Malicious Remote Desktop Protocol (RDP) connections with Elastic Security

   how we can detect malicious lateral file transfers using commonly abused admin tools,
   such as SAMBA, SMB/PS Remoting, FTP, SFTP, SSH, and SCP. But we wanted to explore further how to detect fileless malware that attackers use to hijack and compromise systems like the execution of malicious processes and the exploitation of remote services and sessions.
  Adversaries frequently try to compromise active Remote Desktop Protocol (RDP) sessions
   to launch malicious code or gain access to other hosts in the network. In the [8.9 release](https://www.elastic.co/blog/whats-new-elastic-security-8-9-0), we introduce additional anomaly detection jobs and rules in this package capable of detecting lateral movement attacks for the most commonly abused operating system feature: Windows RDP.  
   
   The Lateral Movement Detection package is generally available to Elastic® users in 8.9. With this Advanced Analytics use case, users can detect malicious file transfers and RDP session activities.
   ![Add Lateral Movement Dection](screenshots/Add-Lateral-inta.png)
   **Agent install**
   ![Agent Install](screenshots/lateral-agent-install.png)
**Enabling security detection rules**
To enable and use the installed rules, navigate to **Security > Alerts > Manage rules** and select **Load Elastic prebuild rules and timeline templates**. If you’re running in Elastic Cloud, this step is done automatically.
use the Lateral Movement Detection tag to filter for all of the detection rules under this package. The rules based on anomaly detection jobs are triggered when the anomaly score surpasses a predetermined threshold, which can be customized by duplicating the detection rule.
   