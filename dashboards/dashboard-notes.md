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
