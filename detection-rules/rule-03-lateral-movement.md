# Detection Rule 3: Lateral Movement — SSH Between Servers

## Rule Details
- **Rule ID:** LM-SSH-001
- **Name:** Lateral Movement via SSH
- **Severity:** Critical
- **Risk Score:** 85
- **MITRE:** T1021.004 — SSH

## KQL Query
event.category:authentication AND process.name:sshd AND source.ip:192.168.* AND event.outcome:success
## Detection Logic
- SSH login from internal IP (192.168.x.x range)
- Successful authentication from another lab VM
- Indicates attacker pivoting to other servers
- Threshold: Any successful SSH from internal network

## Alert Conditions
- SSH success from unexpected internal IP
- SSH login to sensitive servers (database, etc.)
- Multiple servers accessed in sequence

## Baseline
- Expected: Internal SSH for admin management
- Anomalous: SSH from compromised server to others

## Status
✅ Documented and ready for deployment
