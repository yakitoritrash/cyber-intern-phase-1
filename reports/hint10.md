# Hint 10: Command & Control (C2) Traffic Detection

## Objective

Detect periodic beaconing and other signs of C2 communication.

## Steps Taken

- Set up a mock C2 listener using Netcat.
- Used PowerShell Empire to simulate beaconing from Windows VM.

## Logs & Evidence

- Sysmon Event ID 3 (Network Connection) with regular outbound intervals.
- Network logs show repeated small packets to C2 server.
- See: `logs/network_capture_hint10.pcap`
- Screenshot: `screenshots/hint10_c2_traffic.png`

## Detection & Analysis

- SIEM detected regular beaconing intervals (e.g., every 60 seconds).
- No legitimate process mapped to this activity.

## Lessons Learned

- Beaconing patterns are strong C2 indicators; monitor for periodic external connections.
- Detecting C2 early is critical to prevent deeper compromise.
