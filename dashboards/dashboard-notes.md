# SOC — Authentication Overview Dashboard

## Panels Built
1. Total Authentication Events — Metric
2. Authentication Timeline — Area chart
3. Top Targeted Usernames — Bar horizontal
4. Sudo Usage by User — Bar horizontal
5. Auth Events by Process — Bar horizontal
6. Failed Login Attempts — Metric

## KQL Queries Used
- event.category:authentication
- event.category:authentication AND event.outcome:failure
- event.category:authentication AND process.name:sudo

## Fields Used
- user.name — targeted username
- process.name — process generating auth event
- event.outcome — success/failure
- @timestamp — time of event

## Status: ✅ Complete
EOFcat > ~/soc-home-lab/dashboards/dashboard-notes.md << 'EOF'
# SOC — Authentication Overview Dashboard

## Panels Built
1. Total Authentication Events — Metric
2. Authentication Timeline — Area chart
3. Top Targeted Usernames — Bar horizontal
4. Sudo Usage by User — Bar horizontal
5. Auth Events by Process — Bar horizontal
6. Failed Login Attempts — Metric

## KQL Queries Used
- event.category:authentication
- event.category:authentication AND event.outcome:failure
- event.category:authentication AND process.name:sudo

## Fields Used
- user.name — targeted username
- process.name — process generating auth event
- event.outcome — success/failure
- @timestamp — time of event

## Status: ✅ Complete

## Dashboard 2 — SOC Network Overview

### Panels
1. Total Network Events — Metric
2. Network Activity Timeline — Area chart
3. Top Source IPs — Bar horizontal
4. Failed Login Source IPs — Bar horizontal
5. Auth Processes — Bar horizontal

### KQL Queries Used
- event.category:network
- event.dataset:system.auth
- event.dataset:system.auth AND event.outcome:failure

### Status: ✅ Complete

## Dashboard 3 — SOC System Overview

### Panels
1. Total System Events — Metric
2. System Events Timeline — Area chart
3. Top System Processes — Bar horizontal
4. Log Sources Distribution — Pie chart
5. Active Hosts — Metric
6. Authentication Actions — Bar horizontal

### KQL Queries Used
- event.dataset:system.syslog
- event.dataset:system.auth OR event.dataset:system.syslog
- event.dataset:system.auth

### Status: ✅ Complete

## Dashboard 4 — SOC Windows Security Overview

### Panels
1. Total Windows Events — Metric
2. Windows Events Timeline — Area chart
3. New Processes Created (Event 4688) — Metric
4. Total System Channel Events — Metric
5. Top Windows Event IDs — Bar horizontal
6. Top Windows Processes — Bar horizontal
7. Windows Log Sources — Pie chart
8. Active Windows Hosts — Metric

### Data View
- winlogbeat-*

### KQL Queries Used
- agent.type:winlogbeat
- winlog.event_id:4688
- winlog.channel:Security
- winlog.channel:System

### Status: ✅ Complete

## Dashboard 2 — SOC Network Overview (Updated)

### Final 6 Panels
1. Total Network Events — Metric (event.category:network)
2. Network Activity Timeline — Area chart (@timestamp)
3. Top Source IPs — Bar horizontal (source.ip)
4. Top Destination IPs — Bar horizontal (host.ip)
5. Auth Success vs Failure — Pie chart (event.outcome)
6. Auth Events by Process — Bar horizontal (process.name)

### KQL Queries Used
- event.category:network
- event.dataset:system.auth
- event.dataset:system.auth AND event.outcome:failure
- event.dataset:system.auth AND process.name:sshd

### Update Notes
- Panel 4 fixed: Changed to host.ip for destination IPs
- Panel 5 fixed: Changed to Auth Success vs Failure pie chart
- Panel 6 fixed: Changed to Auth Events by Process bar chart
- All 6 panels verified with real data

### Status: ✅ Updated and Complete
