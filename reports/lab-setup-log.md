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
