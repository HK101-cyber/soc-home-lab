# Elasticsearch & Kibana Security Setup Guide

## Overview
Complete guide for enabling xpack.security, generating SSL certificates,
setting passwords, and configuring Kibana encryption keys for SIEM rules.

## Phase 1 — Enable Security & Generate SSL Certificates

### Create certificates directory:
```bash
sudo mkdir -p /etc/elasticsearch/certs
```

### Generate Certificate Authority:
```bash
sudo /usr/share/elasticsearch/bin/elasticsearch-certutil ca \
  --out /etc/elasticsearch/certs/elastic-stack-ca.p12 --pass ""
```

### Generate Transport Certificate:
```bash
sudo /usr/share/elasticsearch/bin/elasticsearch-certutil cert \
  --ca /etc/elasticsearch/certs/elastic-stack-ca.p12 --ca-pass "" \
  --out /etc/elasticsearch/certs/transport.p12 --pass ""
```

### Add passwords to keystore:
```bash
echo "" | sudo /usr/share/elasticsearch/bin/elasticsearch-keystore add -x -f xpack.security.transport.ssl.keystore.secure_password
echo "" | sudo /usr/share/elasticsearch/bin/elasticsearch-keystore add -x -f xpack.security.transport.ssl.truststore.secure_password
```

### Fix permissions:
```bash
sudo chown -R elasticsearch:elasticsearch /etc/elasticsearch/certs
sudo chown elasticsearch:elasticsearch /etc/elasticsearch/elasticsearch.keystore
```

## Phase 2 — Configure elasticsearch.yml

Add at bottom of /etc/elasticsearch/elasticsearch.yml:
```yaml
xpack.security.enabled: true
xpack.security.enrollment.enabled: true
xpack.security.http.ssl:
  enabled: false
xpack.security.transport.ssl:
  enabled: true
  verification_mode: certificate
  keystore.path: certs/transport.p12
  truststore.path: certs/transport.p12
```

## Phase 3 — Generate User Passwords

```bash
# Generate elastic superuser password
sudo /usr/share/elasticsearch/bin/elasticsearch-reset-password -u elastic -a -f

# Generate kibana_system password
sudo /usr/share/elasticsearch/bin/elasticsearch-reset-password -u kibana_system -a -f
```

## Phase 4 — Configure kibana.yml

Add at bottom of /etc/kibana/kibana.yml:
```yaml
elasticsearch.username: "kibana_system"
elasticsearch.password: "YOUR_KIBANA_SYSTEM_PASSWORD"
```

### Generate encryption keys:
```bash
sudo /usr/share/kibana/bin/kibana-encryption-keys generate
```

### Add to kibana.yml:
```yaml
xpack.encryptedSavedObjects.encryptionKey: "your_generated_key_1"
xpack.reporting.encryptionKey: "your_generated_key_2"
xpack.security.encryptionKey: "your_generated_key_3"
```

## Phase 5 — Verify Setup

```bash
# Check Elasticsearch
curl -X GET "http://localhost:9200/_cluster/health?pretty" -u elastic:PASSWORD

# Check Kibana
curl -X GET "http://localhost:5601/api/status" -u elastic:PASSWORD
```

## Result
- SIEM rules creation: ✅ Working
- Detection alerts firing: ✅ Working
- Kibana encryption: ✅ Configured
- User authentication: ✅ Configured

## Status: ✅ Complete
