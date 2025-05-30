# Hint 06: Unauthorized Access Attempt

## Objective

Detect attempts to log in outside normal hours or using disabled accounts.

## Steps Taken

- Attempted login with disabled account and at unusual hours using RDP.

## Logs & Evidence

- Windows Event ID 4625 (Failed Logon) with account status "disabled".
- Event ID 4624 (Successful Logon) checked for time anomalies.
- See: `logs/event_logs_hint6.json`
- Screenshot: `screenshots/hint06_unauthorized_access.png`

## Detection & Analysis

- SIEM correlation for login attempts outside defined time windows.
- Alert triggered on use of disabled account.

## Lessons Learned

- Time-based and account-status-based monitoring can catch unauthorized access early.
- Regular auditing of logs is recommended.
