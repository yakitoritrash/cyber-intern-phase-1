# /logs Directory

This directory contains the raw and processed log files generated during the Phase 1 Cybersecurity Internship Program.

## Purpose

The `/logs` folder is used to store all logs collected from various simulated cybersecurity scenarios and exercises. These logs are essential for:

- Analyzing security events
- Demonstrating evidence of simulated attacks
- Supporting detection engineering and investigation efforts

## What You’ll Find Here

- **Windows Event Logs**: Event IDs (e.g., 4624, 4625, 4698, etc.) captured from the Windows 10 VM.
- **Sysmon Logs**: Detailed system activity including process creation, network connections, file modifications, and registry changes.
- **Winlogbeat Output**: Forwarded logs from Windows to SIEM (ELK or Wazuh).
- **Network Logs**: Optional packet captures or network monitoring logs (e.g., from Wireshark or tcpdump).
- **Scenario-specific Logs**: Log files related to each simulation hint (e.g., brute force attempts, malware execution, data exfiltration, etc.).

## File Naming Convention

- `event_logs_DATE.json` – Exported logs for a given session
- `sysmon_logs_HINT#.evtx` – Sysmon logs for each scenario/hint
- `winlogbeat_output.log` – Winlogbeat forwarder logs
- `network_capture_HINT#.pcap` – Network captures for specific hints
- `README.md` – This file

## Usage

- Reference these logs in your scenario documentation (`/hints` or `/reports`).
- Use the logs for analysis in SIEM platforms or log viewers.
- Keep logs organized by scenario and date for easy traceability.

## Best Practices

- Do NOT upload sensitive or real production logs.
- Only use logs from your controlled lab environment.
- Document the context of each log file (how it was generated, which scenario it relates to).

---
