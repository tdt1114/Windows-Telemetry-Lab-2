# Windows Telemetry SOC Lab

## About
This lab demonstrates the setup, ingestion, and analysis of Windows endpoint telemetry used in Security Operations. Native process creation auditing (Event ID 4688) and Sysmon were enabled on a Windows host and ingested into Splunk Cloud using HTTP Event Collector (HEC). This project focuses on SOC-style workflows: reliably delivering telemetry, detecting suspicious process execution, and performing basic triage using command-line evidence.

## Architecture
Windows Endpoint  
→ Windows Event Logs (4688) & Sysmon  
→ Splunk Cloud (HEC)  
→ Detection & Triage

## What This Lab Demonstrates
- Windows process telemetry (Event ID 4688, Sysmon Event ID 1)
- SIEM ingestion using Splunk HTTP Event Collector (HEC)
- Detection of PowerShell execution with ExecutionPolicy Bypass  
- Analysis of common reconnaissance commands (`whoami`, `ipconfig`)
- SOC-style triage with command-line evidence

## Status
Phase 1: Endpoint Telemetry — Complete  
Phase 2: SIEM Ingestion & Detection — Complete

## Repository Structure
- `lab-notes/`: step-by-step narratives and design decisions  
- `detections/`: written detection logic and triage notes  
- `images/`: key screenshots that support findings
