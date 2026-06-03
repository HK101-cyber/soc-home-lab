# Detection Rule 4: Suspicious Process Execution

## Rule Details
- **Rule ID:** SP-001
- **Name:** Suspicious Process Execution
- **Severity:** Medium
- **Risk Score:** 65
- **MITRE:** T1059 — Command and Scripting Interpreter

## KQL Query
event.category:process AND (process.name:bash OR process.name:sh) AND process.args:curl OR process.args:wget
## Detection Logic
- Shell spawning curl/wget (download tools)
- Often used for downloading malware
- Threshold: Any occurrence
- Indicates data exfiltration or malware download

## Alert Conditions
- Bash/shell executing curl or wget
- Non-standard user running downloads
- Downloads to /tmp or suspicious paths

## Legitimate Use
- System package managers
- Scheduled update scripts
- Admin deployment automation

## Status
✅ Documented and ready for deployment
