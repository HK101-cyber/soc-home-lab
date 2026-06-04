# SOC Home Lab — Setup Log

## Environment
- OS: Ubuntu Server 22.04 LTS
- IP: 192.168.56.101 (Host-Only)
- RAM: 2.9GB
- Disk: 24GB

## Phase 1 — System Preparation ✅
- [x] System updated and upgraded
- [x] Essential tools installed (curl, wget, git, ufw)
- [x] Firewall configured (ports 22, 9200, 5601, 5044, 8220)
- [x] Java 17 installed and verified
- [x] JAVA_HOME environment variable set
- [x] Elastic APT repository added

## Phase 2 — ELK Installation (In Progress)
- [ ] Elasticsearch installed and configured
- [ ] Kibana installed and configured
- [ ] Logstash installed and configured
- [ ] Filebeat installed and configured

## Phase 3 — Log Ingestion
- [ ] Linux logs ingested
- [ ] Windows logs ingested (Winlogbeat)
- [ ] Sysmon telemetry configured

## Phase 4 — Detection Engineering
- [ ] 15 detection rules written
- [ ] Rules tested against simulated attacks
- [ ] Rules exported to GitHub

## Phase 5 — Attack Simulations
- [ ] Brute force SSH (Hydra)
- [ ] PowerShell abuse simulation
- [ ] Privilege escalation
- [ ] Lateral movement
- [ ] Data exfiltration

## Phase 6 — Dashboards
- [ ] 8 Kibana dashboards built
- [ ] Dashboards exported to GitHub

## Commands Reference
```bash
# Start Elasticsearch
sudo systemctl start elasticsearch

# Start Kibana
sudo systemctl start kibana

# Start Logstash
sudo systemctl start logstash

# Check all services
sudo systemctl status elasticsearch kibana logstash
```

## Phase 2 — Elasticsearch ✅
- [x] Elasticsearch 8.x installed
- [x] cluster.name set to soc-home-lab
- [x] network.host set to 0.0.0.0
- [x] xpack security disabled for lab
- [x] JVM heap set to 512MB
- [x] Service enabled and running
- [x] API verified on port 9200
- [x] Screenshots saved

## Phase 3 — Kibana ✅
- [x] Kibana 8.19 installed
- [x] server.host set to 0.0.0.0
- [x] server.port set to 5601
- [x] elasticsearch.hosts configured
- [x] xpack.security conflict resolved
- [x] Service running and verified
- [x] Browser accessible at 192.168.56.101:5601
- [x] Kibana home shows all 4 modules
- [x] Screenshots saved and pushed

## Phase 4 — Logstash ✅
- [x] Logstash installed
- [x] soc-pipeline.conf created
- [x] Input: Beats on port 5044
- [x] Filter: Grok parsing for syslog
- [x] Output: Elasticsearch soc-logs-* index
- [x] JVM heap set to 256MB
- [x] Service running and verified
- [x] Port 5044 listening confirmed

## Phase 5 — Filebeat ✅
- [x] Filebeat 8.19.15 installed
- [x] System module enabled (syslog + auth)
- [x] Output configured to Elasticsearch
- [x] Index template loaded
- [x] Kibana dashboards loaded
- [x] 86,259 documents ingested
- [x] Logs visible in Kibana Discover
- [x] Screenshots saved

## Phase 6 — Dashboard 1 ✅
- [x] SOC Authentication Overview dashboard built
- [x] 6 panels created with real data
- [x] KQL queries verified working
- [x] Dashboard exported as .ndjson
- [x] Screenshot taken and transferred
- [x] Pushed to GitHub

## Phase 7 — Detection Rule 1 ✅
- [x] Brute Force SSH rule documented
- [x] KQL query: event.category:authentication AND event.outcome:failure
- [x] Threshold: 5 failures in 5 minutes
- [x] MITRE ATT&CK mapping: T1110
- [x] Rule tested against real Hydra attack
- [x] Pushed to GitHub detection-rules folder

## Phase 8 — Attack Simulation 1 ✅
- [x] Brute force attack simulated from Kali
- [x] 50+ failed SSH attempts generated
- [x] Logs captured and ingested by Filebeat
- [x] Detection rule validated (threshold: 5 in 5m)
- [x] Screenshots taken (Kali + Ubuntu)
- [x] Attack report documented
- [x] MITRE T1110 mapped

## Phase 9 — Detection Rules Deployed ✅
- [x] All 5 rules created in Kibana SIEM
- [x] Kibana security and encryption keys configured
- [x] Elasticsearch xpack.security enabled
- [x] SSL certificates generated
- [x] elastic and kibana_system passwords set
- [x] Filebeat credentials updated
- [x] Brute force alert confirmed firing
- [x] All rule screenshots taken
- [x] Security setup guide documented
