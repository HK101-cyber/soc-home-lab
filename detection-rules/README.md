# Detection Rules Library

## All Rules

| Rule ID | Name | MITRE | Severity | KQL |
|---------|------|-------|----------|-----|
| BF-SSH-001 | Brute Force SSH | T1110 | High | event.category:authentication AND event.outcome:failure |
| PE-SUDO-001 | Privilege Escalation Sudo | T1548 | High | process.name:sudo AND event.outcome:success |
| LM-SSH-001 | Lateral Movement SSH | T1021.004 | Critical | source.ip:192.168.* AND event.outcome:success |
| SP-001 | Suspicious Process | T1059 | Medium | process.name:(bash OR sh) AND process.args:(curl OR wget) |
| AL-001 | Account Lockout | T1110 | Medium | event.action:user-locked |

## Total Rules: 5
- Rules documented: ✅ 5/5
- Rules tested: ✅ 1/5 (Brute Force)
- Rules deployed: ⏳ Pending Kibana fix

## Status
All rules ready for production deployment once Kibana permissions fixed.
cat > ~/soc-home-lab/detection-rules/README.md << 'EOF'
# Detection Rules Library

## All Rules

| Rule ID | Name | MITRE | Severity | KQL |
|---------|------|-------|----------|-----|
| BF-SSH-001 | Brute Force SSH | T1110 | High | event.category:authentication AND event.outcome:failure |
| PE-SUDO-001 | Privilege Escalation Sudo | T1548 | High | process.name:sudo AND event.outcome:success |
| LM-SSH-001 | Lateral Movement SSH | T1021.004 | Critical | source.ip:192.168.* AND event.outcome:success |
| SP-001 | Suspicious Process | T1059 | Medium | process.name:(bash OR sh) AND process.args:(curl OR wget) |
| AL-001 | Account Lockout | T1110 | Medium | event.action:user-locked |

## Total Rules: 5
- Rules documented: ✅ 5/5
- Rules tested: ✅ 1/5 (Brute Force)


## Status
All rules ready for production deployment once Kibana permissions fixed.

