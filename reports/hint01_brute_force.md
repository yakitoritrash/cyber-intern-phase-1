# Hint 01: Brute Force Attack Simulation

## Objective

Simulate repeated failed login attempts to observe brute force attack patterns and validate detection mechanisms.

## Steps Taken

- Used PowerShell to generate multiple invalid login attempts:
  ```powershell
  for ($i=1; $i -le 10; $i++) {
      net use \\127.0.0.1\IPC$ /user:FakeUser WrongPassword
  }
  ```
- Ensured Sysmon and Winlogbeat were running; logs forwarded to SIEM.

## Logs & Evidence

- Windows Event ID 4625 (Failed Logon) appeared with repeated attempts.
- Key fields: TargetUserName, IpAddress, FailureReason, and Timestamps.
- See: `logs/event_logs_bruteforce.json`
- Screenshot: `screenshots/hint01_brute_force.png`

## Detection & Analysis

- SIEM alert for >5 failed logins from same source within 1 minute.
- Pattern matched MITRE ATT&CK T1110 (Brute Force).
- No successful logins observed during this simulation.

## Lessons Learned

- Brute force attempts can be quickly detected using simple event correlation.
- Account lockout or alerting policies should be configured for rapid response.
