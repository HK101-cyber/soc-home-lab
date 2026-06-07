# Attack Simulations

## Complete Attack Kill Chain

| # | Simulation | Machine | MITRE | Alert Status |
|---|-----------|---------|-------|-------------|
| 1 | Brute Force SSH | Kali → Ubuntu | T1110 | ✅ Fired |
| 2 | Privilege Escalation | Ubuntu (inside) | T1548 | ✅ Fired |
| 3 | Lateral Movement | Kali → Ubuntu | T1021.004 | ✅ Fired |
| 4 | Suspicious Process | Ubuntu (inside) | T1059 | ✅ Fired |
| 5 | Multiple Failed Auth | Kali → Ubuntu | T1110.001 | ✅ Fired |

## Attack Story — Full Kill Chain
Step 1 → Reconnaissance (Nmap scan)
Step 2 → Brute Force SSH attempt (Simulation 1)
Step 3 → Username enumeration (Simulation 5)
Step 4 → Successful SSH login — Lateral Movement (Simulation 3)
Step 5 → Download tools — Suspicious Process (Simulation 4)
Step 6 → Privilege Escalation via sudo (Simulation 2)

## Tools Used
- Hydra — SSH brute force
- SSH client — lateral movement
- Bash — process execution
- Native Linux commands — privilege escalation

## Screenshots
All screenshots saved in /screenshots folder
