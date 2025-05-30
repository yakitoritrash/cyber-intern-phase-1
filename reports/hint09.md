# Hint 09: Lateral Movement Detection

## Objective

Simulate and detect lateral movement between systems using built-in Windows tools.

## Steps Taken

- Used `wmiexec.py` from Impacket and RDP to connect between Windows hosts.
- Monitored logons and SMB traffic.

## Logs & Evidence

- Sysmon Event ID 3 (Network Connection) between internal systems.
- Windows Event ID 4624 (Logon) with new LogonType.
- See: `logs/sysmon_logs_hint9.evtx`
- Screenshot: `screenshots/hint09_lateral_movement.png`

## Detection & Analysis

- SIEM correlated unusual logon types and SMB traffic not associated with normal admin activity.
- Possible lateral movement flagged.

## Lessons Learned

- Internal movement is often missed; monitor east-west traffic and logon patterns.
- Use baselining to differentiate legitimate vs. suspicious connections.
