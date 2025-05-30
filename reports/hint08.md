# Hint 08: Privilege Escalation Attempt

## Objective

Detect attempts to escalate privileges, such as adding a user to the administrators group.

## Steps Taken

- Ran commands to create new user and add to administrators:
  ```
  net user attacker P@ssword123 /add
  net localgroup administrators attacker /add
  ```
- Verified changes via `whoami /groups`.

## Logs & Evidence

- Windows Event ID 4720 (User Creation).
- Event ID 4732 (Added to Admins group).
- See: `logs/event_logs_hint8.json`
- Screenshot: `screenshots/hint08_privilege_escalation.png`

## Detection & Analysis

- SIEM alert on new admin group membership.
- Pattern consistent with privilege escalation techniques (MITRE T1078).

## Lessons Learned

- Monitor for account creation and privilege changes in real time.
- Restrict administrative actions and regularly review membership.
