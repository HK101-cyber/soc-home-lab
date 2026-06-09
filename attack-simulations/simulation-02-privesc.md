# Attack Simulation 2: Privilege Escalation via Sudo

## Objective
Simulate attacker who gained access and escalates privileges using sudo.

## Attack Machine
Ubuntu (inside post-compromise simulation)

## Attack Commands
```bash
sudo cat /etc/shadow
sudo cat /etc/passwd
sudo ls /root
sudo find / -perm -4000 2>/dev/null
sudo netstat -tlnp
```

## MITRE ATT&CK
- Technique: T1548 Abuse Elevation Control Mechanism
- Tactic: Privilege Escalation

## Kill Chain Position
Step 6 of attack attacker already inside, now escalating

## Detection Rule Triggered
- Rule: Privilege Escalation via Sudo (PE-SUDO-001)
- KQL: event.dataset:system.auth AND process.name:sudo AND user.name:hammad
- Status: ✅ ALERT FIRED

## Result
✅ Alert fired in Kibana Security dashboard
✅ Screenshot captured
