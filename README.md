## Cyber Intern Phase 1 – Threat Detection Lab

## 🎯 Objective
This repository documents the hands-on simulation of real-world cybersecurity threats and corresponding detection methods using Sysmon, Winlogbeat, Wazuh/ELK, and a Windows lab environment.

## 🧰 Lab Setup
- ✅ VirtualBox Installed
- ✅ Kali Linux VM (attacker)
- ✅ Windows 10 VM (target)
- ✅ Sysmon Installed with SwiftOnSecurity config
- ✅ Winlogbeat configured and logs forwarded to SIEM
- ✅ Wazuh or ELK SIEM stack setup and working
- ✅ GitHub repository structured for documentation


---

## 🔍 Simulated Attack Scenarios & Logs

### ✅ Hint 1: Brute Force Login
- **Simulated**: Repeated `net use` attempts with fake credentials
- **Event ID**: 4625 (Failed Logon)
- **Tool**: PowerShell
- **Logs Captured**: Windows Security, Sysmon

### ✅ Hint 2: Suspicious PowerShell Usage
- **Simulated**: Encoded PowerShell payload (`Start-Process smoch.exe`)
- **Event ID**: Sysmon 1, PowerShell logs
- **Detection**: PowerShell command logging enabled

### ✅ Hint 3: USB Insertion (❌ Skipped)
- **Status**: Not completed
- **Plan**: Use virtual USB VHD simulation in the future

### ✅ Hint 4: Malware Execution Simulation
- **Simulated**: `.bat` file executing ping
- **Event ID**: Sysmon 1, Sysmon 3
- **Logs**: File creation and process execution tracked

### ✅ Hint 5: Registry Modification
- **Simulated**: Registry key added for persistence
- **Event ID**: Sysmon 13 (Registry object modification)
- **Key**: `HKCU:\Software\Microsoft\Windows\CurrentVersion\Run`

### ✅ Hint 6: Suspicious Network Activity
- **Simulated**: `Invoke-WebRequest` to external URL
- **Event ID**: Sysmon 3 (Network Connection)
- **Tool**: PowerShell

### ✅ Hint 7: Fileless Attack Simulation
- **Simulated**: In-memory PowerShell execution
- **Logged**: ScriptBlock logging, Sysmon 1

### ✅ Hint 8: Suspicious Scheduled Task
- **Simulated**: Task created to run malicious PowerShell
- **Event ID**: Windows 4698
- **Logs**: Process chain + task scheduling

### ✅ Hint 9: Persistence via Startup Folder
- **Simulated**: Dropped `evil.exe` to Startup path
- **Event ID**: Sysmon 11
- **Outcome**: Persistence achieved on reboot

### ✅ Hint 10: Privilege Escalation Attempt
- **Simulated**: Added local admin user `attacker`
- **Event IDs**: 4720 (User created), 4732 (Added to Admins)

---

## 📊 SIEM Integration
- All logs forwarded to **Wazuh** or **ELK** via **Winlogbeat**
- Validation:
  - Confirmed event codes via Kibana/Wazuh dashboard
  - Screenshots captured and stored in `/screenshots/`

---

## 📝 Documentation Checklist
| Scenario                      | Done | Logs | Screenshot | Summary |
|------------------------------|------|------|------------|---------|
| Brute Force Login            | ✅   | ✅   | ✅         | ✅      |
| PowerShell Abuse             | ✅   | ✅   | ✅         | ✅      |
| USB Malware Simulation       | ❌   | ❌   | ❌         | ❌      |
| Malware Execution            | ✅   | ✅   | ✅         | ✅      |
| Registry Persistence         | ✅   | ✅   | ✅         | ✅      |
| Suspicious Network Activity  | ✅   | ✅   | ✅         | ✅      |
| Fileless Attack              | ✅   | ✅   | ✅         | ✅      |
| Scheduled Task Abuse         | ✅   | ✅   | ✅         | ✅      |
| Startup Folder Persistence   | ✅   | ✅   | ✅         | ✅      |
| Privilege Escalation         | ✅   | ✅   | ✅         | ✅      |

---

## 📦 How to Reproduce
1. Clone this repo
2. Review setup guide in `/reports/`
3. Use included commands to simulate each attack
4. Verify logs in Wazuh/Kibana
5. Compare output with provided screenshots/logs

---

## ✅ Status
> ✔️ 9/10 Hints completed  
> 🕐 USB simulation pending (planned via virtual USB disk)

---

## 📎 Resources
- [Sysmon Config - SwiftOnSecurity](https://github.com/SwiftOnSecurity/sysmon-config)
- [Wazuh Documentation](https://documentation.wazuh.com/)
- [Microsoft Sysinternals Tools](https://docs.microsoft.com/en-us/sysinternals/)
- [ELK Stack Setup](https://www.elastic.co/what-is/elk-stack)

---

## 🧠 Notes
> "If you're stuck, think like a hacker. Then, think how you'd detect it." — Internship Guide

---


