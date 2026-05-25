# Filebeat Configuration Notes

## Setup
- Version: 8.19.15
- Output: Elasticsearch direct (localhost:9200)
- Module: system (syslog + auth logs enabled)

## Log Sources
- /var/log/syslog    — system events
- /var/log/auth.log  — authentication events (SSH logins, sudo)

## Index
- Pattern: filebeat-8.19.15-*
- Documents ingested: 86,259+
- Size: 13.5MB

## Key Fields for Detection Rules
- event.category    — authentication, network, process
- event.outcome     — success, failure
- source.ip         — origin IP address
- user.name         — username involved
- message           — raw log message

## Status
- Installed: ✅
- System module enabled: ✅
- Logs flowing: ✅
- Elasticsearch index confirmed: ✅
- Kibana Discover verified: ✅
