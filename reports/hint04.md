# Hint 04: Suspicious Network Activity

## Objective

Simulate abnormal network behavior (e.g., port scans) to understand how such activity is logged.

## Steps Taken

- Ran an Nmap SYN scan from Kali to Windows VM:
  ```
  nmap -sS <windows-vm-ip>
  ```
- Monitored traffic with Wireshark and Sysmon.

## Logs & Evidence

- Sysmon Event ID 3 (Network Connection) showing multiple connection attempts.
- Windows firewall logs: numerous rejected connections.
- See: `logs/network_capture_hint4.pcap`
- Screenshot: `screenshots/hint04_suspicious_network.png`

## Detection & Analysis

- SIEM detected scan pattern: many short-lived connections from one IP.
- No legitimate application matched this behavior.

## Lessons Learned

- Frequent and repeated connection attempts are strong indicators of scanning.
- Automated detection can block or alert on such patterns.
