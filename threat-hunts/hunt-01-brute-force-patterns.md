# Threat Hunt 1: Brute Force Pattern Analysis

## Hunt Hypothesis
Threat actors are systematically attempting to brute force
SSH credentials against our Ubuntu SIEM server.

## Hunt Date
2026-06-08

## Hunter
Hammad Khan SOC Engineer

## KQL Queries Used
event.dataset:system.auth AND event.outcome:failure
event.dataset:system.auth AND event.outcome:failure AND source.ip:192.168.56.1
event.dataset:system.auth AND event.outcome:failure AND event.action:ssh_login
## Real Findings

### Finding 1 High Volume Brute Force Confirmed
- Source IP: 192.168.56.1
- Total failed attempts: 1,197
- Target username: root (most targeted)
- Attack time: Jun 4, 2026 @ 15:54:10 — 15:54:20
- Duration: 10 seconds
- Tool used: Hydra

### Finding 2 Attack Characteristics
- Speed: 1,197 attempts in 10 seconds
- Method: Password spraying against root
- Wordlist: rockyou.txt

### Finding 3 Timeline Spike
- Clear spike visible in Kibana timeline
- Attack isolated to Jun 4, 2026
- No similar activity before or after

## Risk Assessment
- Severity: HIGH
- Current Status: BLOCKED (no successful logins)
- Impact if successful: Full root access to SIEM

## MITRE ATT&CK
- T1110 Brute Force
- T1110.001 Password Guessing

## Recommendations
1. Enable Fail2ban
2. Disable root SSH login
3. SSH key authentication only
4. Rate limit SSH connections

## Conclusion
✅ Hypothesis CONFIRMED 1,197 brute force attempts detected
