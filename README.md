# Cyber Intern Phase 1 – Hands-on Cybersecurity Lab

## Overview

This repository documents my journey through the **Phase 1 Cybersecurity Internship Program**, where I set up a full detection engineering lab, simulated real-world attack scenarios, collected logs, and analyzed events using modern SIEM tools.

**Objective:**  
To gain practical experience in cybersecurity threat detection by performing simulations of common attack patterns and investigating their traces using SIEM platforms.

---

## Lab Setup

### 1. Virtual Environment

- **Virtualization:**  
  Installed [VirtualBox](https://www.virtualbox.org) (or VMware) to run virtual machines.
- **VMs Used:**  
  - **Kali Linux** (for attack simulation)  
  - **Windows 10** (for endpoint logging/target)

### 2. Logging & SIEM Tools

- **Sysmon**: Installed on Windows 10 VM to record detailed system events (processes, connections, file modifications).
- **Winlogbeat**: Configured to ship Windows event and Sysmon logs to SIEM.
- **SIEM Options:**
  - [Wazuh](https://documentation.wazuh.com) (recommended for beginners)
  - ELK Stack (Elasticsearch, Logstash, Kibana)
- **Sample SIEM features:**  
  - Log storage and search (Elasticsearch)
  - Visualization and dashboards (Kibana)
  - Alerting and correlation (Wazuh/ELK)

### 3. Repository Structure

```
cyber-intern-phase-1/
├── logs/
├── reports/
├── screenshots/
├── hints/
└── README.md
```

---

## Step-by-Step Program Guide

### Step 1: Environment Setup

- Installed virtualization software and imported Kali Linux and Windows 10 VMs.
- Deployed SIEM (Wazuh or ELK).
- Configured Sysmon and Winlogbeat on Windows VM.
- Enabled Windows security event logging via Group Policy.
- Created this GitHub repo with folders for logs, screenshots, reports, and hints.

### Step 2: Simulating Security Scenarios

Simulated 10 common attack scenarios to generate event logs and practice detection:

| #  | Scenario                       | Tools / Techniques                                      | Key Events Logged                         |
|----|--------------------------------|---------------------------------------------------------|-------------------------------------------|
| 1  | Brute Force Login              | PowerShell/net use, Hydra, Burp Suite                   | Windows 4625 (Failed Logon)               |
| 2  | Malware Execution              | .bat scripts, test malware, VirusTotal analysis         | Sysmon 1 (Process Create), 11 (File)      |
| 3  | Data Exfiltration              | netcat, Wireshark, file transfer over non-standard port | Sysmon 3 (Network), outbound traffic      |
| 4  | Suspicious Network Activity    | nmap, Wireshark, tcpdump                                | Sysmon 3, odd DNS queries                 |
| 5  | Phishing Email Detection       | GoPhish, email headers, attachments                     | Email logs, attachment events             |
| 6  | Unauthorized Access Attempt    | Failed logins, disabled accounts                        | Windows 4625/4624, geolocation            |
| 7  | Suspicious File Download       | Invoke-WebRequest, curl, PowerShell logging             | Sysmon 1/3, file download events          |
| 8  | Privilege Escalation Attempt   | whoami, accesschk, winPEAS                              | Admin group changes, registry changes     |
| 9  | Lateral Movement Detection     | SMB, RDP, CrackMapExec, Impacket tools                  | Sysmon 3, Windows 4624                    |
| 10 | Command & Control (C2) Traffic | Netcat, Empire, Cobalt Strike, beaconing traffic        | Regular outbound, Sysmon 3                |

- **For each hint:**  
  - Performed the attack/simulation.
  - Captured screenshot(s) of configuration and SIEM output.
  - Saved related logs and config files.

### Step 3: Log Analysis

- Used **Kibana/Wazuh dashboards** and Event Viewer to analyze generated logs.
- Identified patterns for malicious activities (e.g., bursts of 4625, lateral movement, persistence).
- Documented findings in `/reports` and `/hints`.

### Step 4: Documentation

- Created detailed markdown files for each scenario (e.g., `hint01_brute_force.md`) in `/hints` folder.
- Included:
  - Steps performed
  - Screenshots
  - Observed log entries and indicators
  - SIEM alerts (if any)
  - Analysis and lessons learned

### Step 5: Submission

- Committed and pushed lab artifacts (logs, screenshots, reports) to GitHub weekly.
- Ensured at least 8 out of 10 hints were completed and documented for eligibility to Phase 2.

---

## Troubleshooting & Tips

- Use [TryHackMe](https://tryhackme.com) or [HackTheBox](https://www.hackthebox.com) if local lab setup is not possible.
- Refer to [MITRE ATT&CK](https://attack.mitre.org/) for tactics and detection ideas.
- Search YouTube for walkthroughs (e.g., "hydra brute force demo").
- If stuck:  
  “Think like a hacker. Then, think how you’d detect it.”

---

## Acknowledgements

- [Wazuh Documentation](https://documentation.wazuh.com)
- [SwiftOnSecurity/sysmon-config](https://github.com/SwiftOnSecurity/sysmon-config)
- [Elastic Stack](https://www.elastic.co/what-is/elk-stack)
- MITRE ATT&CK Framework

---
