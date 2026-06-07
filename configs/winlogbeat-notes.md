# Winlogbeat Configuration Notes

## Overview
Winlogbeat ships Windows Event Logs to Elasticsearch.
Installed on Windows host PC to monitor all Windows activity.

## Version
Winlogbeat 9.4.2

## Log Sources Configured
- Application — Windows application events
- System — Windows system events
- Security — Login, logoff, privilege use, account changes
- Microsoft-Windows-Sysmon/Operational — Deep process telemetry

## Output
- Elasticsearch: 192.168.56.101:9200
- Credentials: elastic user
- Index: winlogbeat-*

## Key Windows Event IDs Monitored
| Event ID | Description |
|----------|-------------|
| 4624 | Successful logon |
| 4625 | Failed logon |
| 4648 | Logon with explicit credentials |
| 4672 | Special privileges assigned |
| 4688 | New process created |
| 4698 | Scheduled task created |
| 4720 | User account created |
| 4732 | User added to security group |
| 7045 | New service installed |

## Status
- Installed: ✅
- Service running: ✅
- Logs flowing to Elasticsearch: ✅
- Kibana Discover verified: ✅
- Screenshots saved: ✅
