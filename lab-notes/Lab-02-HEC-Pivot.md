# Lab 02 – SIEM Ingestion via HEC

## Objective
Ingest Windows endpoint telemetry into Splunk Cloud and demonstrate SOC-style detection and triage.

## Data Sources
- Windows Security Event ID 4688 (process creation)
- Sysmon Event ID 1 (process execution)
- Transport: Splunk HTTP Event Collector (HEC)

## Architectural Notes
Universal Forwarder–based ingestion was initially attempted. Due to receiver-side constraints in the cloud environment, ingestion was completed using HEC to reliably deliver endpoint telemetry for analysis.

## Detection Evidence
Observed PowerShell executions using:
- ExecutionPolicy Bypass
- whoami
- ipconfig

These commands are commonly associated with reconnaissance and post-execution discovery activity.

## Triage Summary
- Activity Type: Process execution / discovery
- Severity: Low–Medium (context dependent)
- Assessment: Benign in lab context
- Analyst Actions: Validate parent process, user context, frequency, and follow-on activity
