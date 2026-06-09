# Kibana Configuration Notes

## Key Settings Applied

| Setting | Value | Reason |
|---------|-------|--------|
| server.port | 5601 | Standard Kibana port |
| server.host | 0.0.0.0 | Accept all interface connections |
| elasticsearch.hosts | http://localhost:9200 | Local Elasticsearch instance |

## Important Fix Applied
Kibana 8.19 does not accept xpack.security.enabled in kibana.yml
This setting belongs only in elasticsearch.yml
Removing it from kibana.yml resolved the FATAL startup error

## Access URL
- http://192.168.56.101:5601

## Modules Available
- Elasticsearch search and indexing
- Observability logs, metrics, traces
- Security SIEM, alerts, threat detection
- Analytics dashboards and visualizations

## Verification Commands
```bash
# Check status
sudo systemctl status kibana

# Check port binding
sudo ss -tlnp | grep 5601

# Check logs
sudo journalctl -u kibana -f
```

## Status
- Installed: ✅
- Configured: ✅
- Running: ✅
- Browser verified: ✅
- Screenshots saved: ✅
