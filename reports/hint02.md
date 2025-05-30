# Hint 02: Malware Execution Simulation

## Objective

Simulate execution of suspicious files and scripts to observe how malware activity is logged and detected.

## Steps Taken

- Created and executed a benign `.bat` file mimicking malware behavior:
  ```bat
  @echo off
  echo Simulating malware...
  ping 8.8.8.8 -n 10
  ```
- Uploaded file to Windows VM and executed from the Downloads directory.

## Logs & Evidence

- Sysmon Event ID 1 (Process Create) for `cmd.exe` and the batch file.
- Sysmon Event ID 11 (File Create) for the new file.
- See: `logs/sysmon_logs_hint2.evtx`
- Screenshot: `screenshots/hint02_malware_exec.png`

## Detection & Analysis

- SIEM flagged unusual process execution from user Downloads folder.
- Correlation: File creation followed by process execution.
- No antivirus triggered as file was benign.

## Lessons Learned

- File creation and process logs are critical for detecting malware execution.
- Monitoring non-standard directories for executable files is recommended.
