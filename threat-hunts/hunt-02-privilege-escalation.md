# Threat Hunt 2: Privilege Escalation via Sudo

## Hunt Hypothesis
Attacker gained access and is escalating privileges using sudo.

## Hunt Date
2026-06-08

## Hunter
Hammad Khan SOC Engineer

## KQL Queries Used
event.dataset:system.auth AND process.name:sudo
event.dataset:system.auth AND process.name:sudo AND user.name:root
## Real Findings

### Finding 1 High Sudo Activity
- Total sudo events: 891
- Users running sudo: hammad, root
- Time period: Starting May 23, 2026 @ 07:03:55

### Finding 2 Security Gap Identified
- Sudo commands NOT fully visible in message field
- Exact commands run cannot be audited
- This is a critical logging gap

### Finding 3 Recommendation
- Enable auditd for sudo command logging
- Configure sudoers to log all commands
- Forward audit logs to SIEM

## Risk Assessment
- Severity: HIGH
- Gap Found: Incomplete sudo logging
- Impact: Cannot fully audit privileged activity

## MITRE ATT&CK
- T1548 Abuse Elevation Control Mechanism
- T1003 OS Credential Dumping (attempted)

## Recommendations
1. Enable auditd logging
2. Configure sudo log to separate file
3. Alert on sudo access to /etc/shadow
4. Restrict sudo to specific commands only

## Conclusion
✅ Hypothesis CONFIRMED 891 sudo events detected
⚠️ Critical Gap Found sudo commands not fully logged
