# Detection Rules Library

## Deployed Rules — All Active in Kibana SIEM

| # | Rule ID | Name | MITRE | Severity | Status |
|---|---------|------|-------|----------|--------|
| 1 | BF-SSH-001 | Brute Force SSH Attack | T1110 | High | ✅ Active |
| 2 | PE-SUDO-001 | Privilege Escalation via Sudo | T1548 | High | ✅ Active |
| 3 | LM-SSH-001 | Lateral Movement via SSH | T1021.004 | Critical | ✅ Active |
| 4 | SP-001 | Suspicious Shell Process | T1059 | Medium | ✅ Active |
| 5 | AL-001 | Multiple Failed Auth Attempts | T1110.001 | Medium | ✅ Active |

## Alert Confirmed
- Brute Force SSH rule triggered successfully
- Attack simulated using Hydra from Kali Linux
- Alert appeared in Kibana Security → Alerts
- Screenshot saved: brute-force-alert-fired.png

## Total Rules: 5 deployed and active
