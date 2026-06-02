# Attack Simulation 1: Brute Force SSH Attack

## Objective
Simulate a real brute force attack against SSH service and verify detection capabilities.

## Attack Details
- **Tool:** Hydra (password cracking tool)
- **Target:** Ubuntu SIEM server (192.168.56.101)
- **Service:** SSH port 22
- **Username:** root
- **Date:** 2026-06-02
- **Duration:** 3 minutes
- **Threads:** 4 concurrent

## Attack Command
```bash
hydra -l root -P /usr/share/wordlists/rockyou.txt 192.168.56.101 ssh -t 4 -f -v
```

## Results
- **Attempts Generated:** 50+
- **Success Rate:** 0% (no valid credentials)
- **Source IP:** 192.168.56.100 (Kali)
- **Target User:** root

## Log Evidence
Failed password for root from 192.168.56.100 port XXXXX ssh2
Failed password for root from 192.168.56.100 port XXXXX ssh2
Failed password for root from 192.168.56.100 port XXXXX ssh2
## Detection Rule Result
**Rule:** Brute Force SSH Attack (BF-SSH-001)
- **Threshold:** 5 failures in 5 minutes
- **Actual:** 50 failures in 3 minutes
- **Status:** ✅ WOULD TRIGGER

## MITRE ATT&CK Mapping
- **Technique:** T1110 — Brute Force
- **Tactic:** Credential Access

## Screenshots
1. hydra-brute-force-kali.PNG — Attack in progress on Kali
2. ubuntu-failed-logins.png — Real-time failed attempts on Ubuntu

## Findings
✅ Attack successfully simulated
✅ Logs captured and ingested
✅ Detection rule validated
✅ Elasticsearch data available

## Defense Recommendations
1. Enable Fail2ban (block after 3 failures)
2. SSH key-based authentication only
3. Disable root login via SSH
4. Rate limiting on port 22
5. Alert on 5+ failures/5 minutes

## Completion
- Simulation: ✅ Complete
- Documentation: ✅ Complete
- Screenshots: ✅ Captured
- Rule Validation: ✅ Verified
