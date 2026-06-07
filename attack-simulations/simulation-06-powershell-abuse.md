# Attack Simulation 6: Windows PowerShell Abuse

## Objective
Simulate attacker using PowerShell for reconnaissance and suspicious
execution — one of the most common real-world attack techniques.

## Attack Machine
Windows Host PC (attacker already inside)

## Attack Commands
```powershell
whoami && hostname && ipconfig
net user && net localgroup administrators
powershell -EncodedCommand "aQBwAGMAbwBuAGYAaQBnAA=="
reg query HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Run
cmd.exe /c systeminfo
```

## MITRE ATT&CK
- Technique: T1059.001 — PowerShell
- Tactic: Execution
- Sub-technique: Command and Scripting Interpreter

## Kill Chain Position
Post-compromise — attacker running recon and downloading tools

## What Sysmon Captured
- Event ID 1 — Process Creation (powershell.exe)
- Event ID 1 — Process Creation (cmd.exe)
- Command line arguments logged
- Parent process recorded
- Hash of executable captured

## Detection Rule Triggered
- Rule: Suspicious PowerShell Execution
- Index: winlogbeat-*
- KQL: winlog.event_id:1 AND process.name:powershell.exe
- Severity: High
- Risk Score: 80
- Status: ✅ ALERT FIRED

## Evidence Chain
1. PowerShell commands executed on Windows
2. Sysmon captured Event ID 1 (process creation)
3. Winlogbeat shipped events to Elasticsearch
4. Kibana detection rule matched events
5. Alert fired in Security dashboard
6. Full command line visible in Kibana Discover

## MITRE ATT&CK Reference
https://attack.mitre.org/techniques/T1059/001/

## Screenshots
1. sim06-powershell-commands.png
2. sim06-sysmon-powershell-detected.png
3. rule-06-powershell-deployed.png
4. sim06-powershell-alert-fired.png

## Completion
- Simulation: ✅ Complete
- Sysmon capture: ✅ Verified
- Alert fired: ✅ Confirmed
- Documentation: ✅ Complete
