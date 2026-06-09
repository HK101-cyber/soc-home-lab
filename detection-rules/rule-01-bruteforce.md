# Detection Rule 1: Brute Force SSH Attack

## Overview
Detects multiple failed SSH/authentication login attempts within a short time window, indicating potential brute force attack.

## Rule Details
- **Rule ID:** BF-SSH-001
- **Name:** Brute Force SSH Attack
- **Severity:** High
- **Risk Score:** 75
- **Status:** Active

## KQL Query
event.category:authentication AND event.outcome:failure

## Detection Logic
- Count failed authentication events
- Time window: 5 minutes
- Alert threshold: 5 or more failures
- Grouped by: source.ip and user.name

## MITRE ATT&CK Mapping
- **Technique:** T1110 Brute Force
- **Tactic:** Credential Access
- **Description:** Adversary attempts to gain credentials by repeated login attempts

## Fields Monitored
- `event.category` must be "authentication"
- `event.outcome`  must be "failure"
- `source.ip` attacker source IP
- `user.name` target username
- `@timestamp` event time

## Alert Actions
When triggered:
1. Create high-severity alert in Security dashboard
2. Display source IP and targeted username
3. Show number of failed attempts
4. Link to Discover for full event details

## False Positives
- Legitimate user typing wrong password multiple times
- Automated backup jobs with wrong credentials
- Failed scheduled tasks

## Tuning Options
- Increase threshold to 10 for less sensitive detection
- Decrease time window to 1 minute for more aggressive detection
- Add exclusion list for known service accounts

## Testing
Rule tested against real brute force simulation:
- Hydra attack from 192.168.56.100 against root user
- Generated 50+ failed attempts in 2 minutes
- Rule successfully triggered

## Created
Date: 2026-06-02
Author: Hammad Khan
Version: 1.0
