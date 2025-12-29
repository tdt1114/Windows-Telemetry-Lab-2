# Lab 02 – SIEM Ingestion via HEC

## Objective
Ingest Windows endpoint telemetry into Splunk Cloud and demonstrate SOC-style detection and triage.

## Environment Pivot (VM to Host)
Initial validation was completed using a local Windows VM to generate telemetry. Due to local resource constraints impacting VM performance and stability, the environment was transitioned to a dedicated Windows host to ensure reliable event generation and focus on telemetry quality and analysis.

## SIEM Ingestion Pivot (Design Decision)
Universal Forwarder–based ingestion was initially attempted using Splunk Cloud’s TCP receiver. While endpoint telemetry and authentication were validated, sustained ingestion was inconsistent due to receiver-side constraints in the cloud trial environment. To ensure reliable delivery of endpoint telemetry and complete detection workflows, ingestion was intentionally pivoted to Splunk HTTP Event Collector (HEC). This cloud-native ingestion method allowed telemetry delivery and detection without infrastructure blockers.

## Data Sources
- Windows Security Event ID 4688 (process creation)  
- Sysmon Event ID 1 (process execution)  
- Transport: Splunk HTTP Event Collector (HEC)

## Detection Evidence
The following activity was observed and detected:
- PowerShell execution using `-ExecutionPolicy Bypass`  
- Common reconnaissance commands: `whoami`, `ipconfig`

## Triage Summary
- **Activity Type:** Process execution / reconnaissance  
- **Severity:** Context-dependent (Low–Medium)  
- **Assessment:** Benign in lab context  
- **Analyst Actions:** Confirm parent process, user context, command lineage, repeated behavior
