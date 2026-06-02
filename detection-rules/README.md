# Detection Rules Library

This folder contains all custom KQL detection rules for the SOC lab environment.

## Rules

### Rule 1: Brute Force SSH Attack (BF-SSH-001)
- **File:** rule-01-bruteforce.md
- **KQL:** event.category:authentication AND event.outcome:failure
- **Threshold:** 5 failures in 5 minutes
- **Status:** Active
- **MITRE:** T1110

## How to Import Rules

Rules are documented in markdown for reference and can be manually created in Kibana:

1. Go to Security → Rules → Create new rule
2. Select: Custom query rule
3. Copy KQL query from rule file
4. Set threshold and time window as documented
5. Add tags and MITRE technique ID
6. Enable rule

## Rule Naming Convention

- Format: `rule-[number]-[technique].md`
- Example: `rule-01-bruteforce.md`, `rule-02-lateral-movement.md`

## Planned Rules

- [ ] Rule 2: Privilege Escalation (sudo abuse)
- [ ] Rule 3: Lateral Movement (SSH between servers)
- [ ] Rule 4: Data Exfiltration (large outbound transfers)
- [ ] Rule 5: Suspicious Process Execution
- [ ] Rule 6: Failed Account Lockout
- [ ] Rule 7: RDP Brute Force
- [ ] Rule 8: Web Shell Detection
- [ ] Rule 9: Reverse Shell Connections
- [ ] Rule 10: Credential Dumping
