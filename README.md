# Splunk Security Monitoring Lab

## Overview
This project simulates a Security Operations Center (SOC) workflow using Splunk SIEM. Linux authentication and system logs were ingested and analyzed to investigate suspicious login behavior and privilege escalation activity.

The environment includes simulated failed authentication attempts and repeated `sudo` usage to demonstrate brute-force style activity detection and log analysis techniques.

## Objectives
- Ingest Linux authentication and system logs into Splunk
- Monitor authentication failures and `sudo` activity
- Identify patterns consistent with brute-force attempts
- Use SPL queries to investigate security events
- Develop foundational SOC monitoring and analysis skills

## Environment
- Linux system generating authentication and system logs
- Splunk Enterprise / Splunk Free
- Custom index: `main`
- Simulated user activity including failed logins and sudo attempts

## Key Findings
- Repeated failed login attempts were detected using Splunk query filtering on authentication-related logs
- `sudo` activity logs were used to observe potential privilege escalation attempts
- Centralized logging in the `main` index enabled efficient investigation of system-wide activity
- Aggregation and filtering helped identify repeated user-based suspicious behavior patterns
- Splunk queries allowed rapid isolation of authentication anomalies

## SPL Queries Used

### Total event count
```spl
index=main | stats count
