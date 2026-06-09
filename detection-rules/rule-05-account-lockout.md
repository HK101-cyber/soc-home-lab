# Detection Rule 5: Account Lockout Potential Account Compromise

## Rule Details
- **Rule ID:** AL-001
- **Name:** Account Lockout After Failed Attempts
- **Severity:** Medium
- **Risk Score:** 60
- **MITRE:** T1110 Brute Force

## KQL Query
event.category:authentication AND event.action:user-locked AND process.name:sshd
## Detection Logic
- User account locked after multiple failed attempts
- Indicates brute force attack or wrong password
- Threshold: 1+ account lockout
- Shows attack prevented by system controls

## Alert Conditions
- SSH account locked
- Multiple failed attempts preceding lockout
- Root or admin account locked
- Multiple users locked simultaneously

## Security Value
- Validates anti-brute-force controls working
- Identifies attack attempts being blocked
- Shows system security in action

## Status
✅ Documented and ready for deployment
