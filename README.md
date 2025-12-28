## Overview
This project documents a progressive Windows telemetry lab focused on endpoint process creation logging (4688 + Sysmon),
SIEM ingestion, and SOC-style detection/triage workflows.

## Skills Demonstrated
- Windows auditing (4688) + command-line capture
- Sysmon deployment and validation
- Log ingestion into SIEM (Splunk)
- Baseline analysis, detection logic, and triage documentation

## Lab Phases
- Phase 1: Sysmon + 4688 enablement + Splunk ingestion (local)
- Phase 2 (current): Pivot to host-based telemetry + cloud SIEM ingestion

## Repository Structure
- lab-notes/   – Lab documentation and analysis notes
- configs/     – Sanitized configuration snippets
- detections/  – Detection logic and SPL queries
- images/      – Evidence screenshots (SOC-focused)
