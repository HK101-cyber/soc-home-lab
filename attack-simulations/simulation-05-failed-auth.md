# Attack Simulation 5: Multiple Failed Authentication Attempts

## Objective
Simulate attacker trying multiple usernames with wrong passwords.

## Attack Machine
Kali Linux (192.168.56.100) → Ubuntu (192.168.56.101)

## Attack Commands
```bash
# From Kali
ssh root@192.168.56.101
ssh admin@192.168.56.101
ssh administrator@192.168.56.101
ssh test@192.168.56.101
ssh oracle@192.168.56.101
ssh postgres@192.168.56.101
ssh guest@192.168.56.101
```

## MITRE ATT&CK
- Technique: T1110.001 — Password Guessing
- Tactic: Credential Access

## Kill Chain Position
Step 3 of attack — username enumeration before brute force

## Detection Rule Triggered
- Rule: Multiple Failed Authentication Attempts (AL-001)
- KQL: event.dataset:system.auth AND event.outcome:failure
- Status: ✅ ALERT FIRED

## Result
✅ Alert fired in Kibana Security dashboard
✅ Screenshot captured
