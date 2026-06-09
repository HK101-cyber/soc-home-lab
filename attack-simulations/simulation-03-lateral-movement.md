# Attack Simulation 3: Lateral Movement via SSH

## Objective
Simulate attacker pivoting from Kali to Ubuntu via SSH.

## Attack Machine
Kali Linux (192.168.56.100) → Ubuntu (192.168.56.101)

## Attack Commands
```bash
# From Kali
ssh hammad@192.168.56.101
# Successfully logged in
ifconfig
cat /etc/hosts
arp -a
```

## MITRE ATT&CK
- Technique: T1021.004 Remote Services SSH
- Tactic: Lateral Movement

## Kill Chain Position
Step 4 of attack attacker moving between machines

## Detection Rule Triggered
- Rule: Lateral Movement via SSH (LM-SSH-001)
- KQL: event.dataset:system.auth AND process.name:sshd AND event.outcome:success AND source.ip:192.168.56.100
- Status: ✅ ALERT FIRED

## Result
✅ Alert fired in Kibana Security dashboard
✅ Screenshot captured
