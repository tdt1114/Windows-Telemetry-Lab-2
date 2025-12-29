# Windows Telemetry SOC Lab

## About
This lab demonstrates the setup, ingestion, and analysis of Windows endpoint telemetry used in Security Operations. Native process creation auditing (Event ID 4688) and Sysmon were enabled on a Windows host and ingested into Splunk Cloud using HTTP Event Collector (HEC).

The project focuses on SOC-style workflows: validating telemetry, detecting suspicious process execution, and performing basic triage using command-line evidence.

## Architecture
Windows Endpoint  
→ Windows Event Logs (4688) & Sysmon  
→ Splunk Cloud (HEC)  
→ Detection & Triage

## What This Lab Demonstrates
- Windows process telemetry (4688, Sysmon Event ID 1)
- Cloud SIEM ingestion using HTTP Event Collector
- Detection of PowerShell execution with ExecutionPolicy Bypass
- Analysis of common reconnaissance commands (whoami, ipconfig)
- SOC-style triage and decision-making

## Status
Phase 1: Endpoint Telemetry — Complete  
Phase 2: SIEM Ingestion & Detection — Complete
