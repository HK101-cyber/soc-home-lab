# Attack Simulations Complete Kill Chain

## All 6 Simulations

| # | Simulation | Machine | MITRE | Alert |
|---|-----------|---------|-------|-------|
| 1 | Brute Force SSH | Kali → Ubuntu | T1110 | ✅ Fired |
| 2 | Privilege Escalation | Ubuntu inside | T1548 | ✅ Fired |
| 3 | Lateral Movement | Kali → Ubuntu | T1021.004 | ✅ Fired |
| 4 | Suspicious Process | Ubuntu inside | T1059 | ✅ Fired |
| 5 | Multiple Failed Auth | Kali → Ubuntu | T1110.001 | ✅ Fired |
| 6 | PowerShell Abuse | Windows host | T1059.001 | ✅ Fired |

## Complete Attack Story
Step 1 → Brute Force SSH (Simulation 1)
Step 2 → Username Enumeration (Simulation 5)
Step 3 → Successful SSH Login Lateral Movement (Simulation 3)
Step 4 → Privilege Escalation via Sudo (Simulation 2)
Step 5 → Suspicious Process Execution (Simulation 4)
Step 6 → PowerShell Abuse on Windows (Simulation 6)
## Tools Used
- Hydra SSH brute force
- SSH client lateral movement
- Bash process execution
- PowerShell Windows abuse
- Sysmon Windows telemetry capture

## Total Alerts Fired: 6/6 ✅
