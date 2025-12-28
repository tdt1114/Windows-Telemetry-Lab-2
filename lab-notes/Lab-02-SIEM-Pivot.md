# Lab 02 — SIEM Pivot (Host-Based Telemetry + Cloud SIEM)

## Objective
Continue Windows telemetry lab by moving SIEM off the VM while keeping endpoint telemetry intact.

## Architecture Adjustment (Resource-Aware Pivot)
(Insert your pivot section here.)

## Endpoint Telemetry Sources
- Windows Security Log: Event ID 4688 (Process Creation)
- Sysmon Operational: Event ID 1 (Process Create), Event ID 3 (Network Connect)

## Pre-Ingestion Validation (Host System)
### Sysmon Validation
- Command(s):
- Result:

### 4688 Validation
- Command(s):
- Result:

## Evidence
(Reference screenshots in /images)

## Next Steps
- Splunk Cloud onboarding
- Universal Forwarder install
- Ingestion validation
- First detection + triage
