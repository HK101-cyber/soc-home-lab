# Sysmon Configuration Notes

## Overview
System Monitor (Sysmon) is a Windows system service that logs
detailed security telemetry to Windows Event Log.

## Version
Sysmon 64-bit — Latest version

## Config Used
SwiftOnSecurity sysmon-config (industry standard)
Source: github.com/SwiftOnSecurity/sysmon-config

## Key Event IDs Monitored

| Event ID | Description | SOC Value |
|----------|-------------|-----------|
| 1 | Process Creation | Detects malware execution |
| 2 | File Creation Time | Detects timestomping |
| 3 | Network Connection | Detects C2 communication |
| 5 | Process Terminated | Tracks process lifecycle |
| 6 | Driver Loaded | Detects rootkit installation |
| 7 | Image Loaded | Detects DLL injection |
| 8 | CreateRemoteThread | Detects process injection |
| 10 | ProcessAccess | Detects credential dumping |
| 11 | FileCreate | Detects dropped files |
| 12 | RegistryEvent | Detects persistence |
| 13 | RegistryEvent | Detects config changes |
| 15 | FileCreateStreamHash | Detects ADS attacks |
| 22 | DNSEvent | Detects DNS queries |
| 23 | FileDelete | Detects log tampering |

## Integration
- Winlogbeat reads: Microsoft-Windows-Sysmon/Operational
- Ships to: Elasticsearch 192.168.56.101:9200
- Index: winlogbeat-*
- Kibana query: winlog.channel:Microsoft-Windows-Sysmon/Operational

## Status
- Installed: ✅
- Running: ✅
- Logs flowing via Winlogbeat: ✅
- Kibana verified: ✅
- Screenshots saved: ✅
