# Hint 05: Phishing Email Detection

## Objective

Simulate phishing attempt detection through email analysis and SIEM correlation.

## Steps Taken

- Used GoPhish to send a simulated phishing email with a suspicious attachment.
- Inspected email headers and content.

## Logs & Evidence

- Email event logs showed delivery from unusual sender domain.
- Attachment with `.exe` extension flagged as suspicious.
- See: `logs/email_logs_hint5.eml`
- Screenshot: `screenshots/hint05_phishing_email.png`

## Detection & Analysis

- SIEM/email gateway flagged email based on attachment type and header anomalies.
- No user clicked the link or opened the file in this simulation.

## Lessons Learned

- Email filtering and attachment policy are key to phishing defense.
- Header analysis helps detect spoofing and malicious links.
