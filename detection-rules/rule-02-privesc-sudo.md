# Detection Rule 2: Privilege Escalation — Sudo Abuse

## Rule Details
- **Rule ID:** PE-SUDO-001
- **Name:** Privilege Escalation via Sudo Abuse
- **Severity:** High
- **Risk Score:** 70
- **MITRE:** T1548 — Abuse Elevation Control Mechanism

## KQL Query
event.category:authentication AND process.name:sudo AND event.outcome:success
## Detection Logic
- Detects successful sudo command execution
- Threshold: 10+ sudo commands in 5 minutes
- Indicates potential privilege escalation attempt
- Grouped by: user.name

## Alert Conditions
- Multiple successful sudo executions in short timeframe
- Unusual user running sudo
- Sudo commands during off-hours

## False Positives
- System administrators running routine sudo tasks
- Automated backup scripts with sudo
- Scheduled maintenance jobs

## Status
✅ Documented and ready for deployment
