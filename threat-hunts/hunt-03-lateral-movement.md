# Threat Hunt 3: Lateral Movement via SSH

## Hunt Hypothesis
Attacker is pivoting between machines using SSH.

## Hunt Date
2026-06-08

## Hunter
Hammad Khan SOC Engineer

## KQL Queries Used
event.dataset:system.auth AND process.name:sshd AND event.outcome:success
event.dataset:system.auth AND process.name:sshd AND event.outcome:success AND source.ip:192.168.56.1
## Real Findings

### Finding 1 Successful SSH Sessions Detected
- Total successful logins: 69
- Source IP: 192.168.56.1 (Windows PC)
- Destination: 10.0.2.4 (Ubuntu VM)
- Username: hammad

### Finding 2 Movement Pattern
- All logins from same source IP
- Consistent username used
- Monitoring period: May 9 - Jun 8, 2026 (30 days)
   - Interval: 12 hour auto detection

### Finding 3 Baseline Established
- 69 successful sessions over 30 days
- Average 2-3 sessions per day
- No anomalous spikes detected

## Risk Assessment
- Severity: MEDIUM
- Current Status: MONITORED
- Note: Some logins are legitimate admin sessions

## MITRE ATT&CK
- T1021.004 Remote Services SSH
- T1078 Valid Accounts

## Recommendations
1. Whitelist only known admin IPs
2. Alert on SSH from unexpected IPs
3. Implement MFA for SSH
4. Log all post-login commands

## Conclusion
✅ Hypothesis CONFIRMED 69 successful SSH sessions
✅ Baseline established for future anomaly detection
