# Elasticsearch Configuration Notes

## Key Settings Applied

| Setting | Value | Reason |
|---------|-------|--------|
| cluster.name | soc-home-lab | Identifies our SOC cluster |
| node.name | siem-node-1 | Identifies this node |
| network.host | 0.0.0.0 | Accepts connections from all interfaces |
| http.port | 9200 | Standard Elasticsearch API port |
| xpack.security.enabled | false | Disabled for lab environment |
| JVM Heap | 512MB | Optimized for 2.9GB RAM VM |

## Verification Commands
```bash
# Check service status
sudo systemctl status elasticsearch

# Test API response
curl -X GET "localhost:9200"

# Check cluster health
curl -X GET "localhost:9200/_cluster/health?pretty"
```

## Ports Used
- 9200 — HTTP API (Kibana connects here)
- 9300 — Node communication (internal)

## Status
- Installed: ✅
- Configured: ✅
- Running: ✅
- Verified: ✅
