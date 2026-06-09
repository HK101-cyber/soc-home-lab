# Logstash Configuration Notes

## Pipeline: soc-pipeline.conf

### Input
- Beats input on port 5044
- Receives logs from Filebeat and Winlogbeat agents

### Filter
- Grok pattern parsing for syslog format
- Date field normalization
- Applied to system module events

### Output
- Elasticsearch on localhost:9200
- Index pattern: soc-logs-YYYY.MM.dd (daily rotation)
- Stdout debug output for troubleshooting

## JVM Memory
- Heap set to 256MB (optimized for 2.9GB RAM VM)

## Ports
- 5044 Beats input (Filebeat/Winlogbeat connect here)

## Status
- Installed: ✅
- Pipeline configured: ✅
- JVM optimized: ✅
- Running: ✅
- Port 5044 listening: ✅
