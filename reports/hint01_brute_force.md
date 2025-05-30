# Hint 01 – Brute Force Login Simulation

## Objective
To simulate a brute-force login attempt and capture the corresponding failed login events.

## Steps Performed
```powershell
for ($i=1; $i -le 10; $i++) {
    net use \\127.0.0.1\IPC$ /user:FakeUser WrongPassword
} ```

## Expected Logs
Windows Event ID 4625: Failed login attempts.

Shows target username, source IP, and error code.

## SIEM Detection
Wazuh/ELK log pattern: Repeated 4625 events within a short time



