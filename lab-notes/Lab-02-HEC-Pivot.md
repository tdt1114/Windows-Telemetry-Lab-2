# SOC Alert Investigation – Endpoint Telemetry (Splunk Cloud)

## Objective
Ingest Windows endpoint telemetry into Splunk Cloud and perform SOC-style detection and triage on process execution activity.

---

## Environment & Design Decisions

### Endpoint Source
Initial validation was performed using a local Windows VM to confirm telemetry generation. Due to local resource constraints impacting system stability and event consistency, the environment was transitioned to a dedicated Windows host to ensure reliable telemetry and accurate analysis.

### SIEM Ingestion Method
Universal Forwarder ingestion via the Splunk Cloud TCP receiver was initially validated but proved inconsistent in the cloud trial environment. To ensure reliable telemetry delivery and complete detection workflows, ingestion was intentionally pivoted to Splunk HTTP Event Collector (HEC), a cloud-native ingestion method commonly used in enterprise environments.

**Rationale:** Reliable telemetry ingestion is a prerequisite for effective SOC detection and triage.

---

## Data Sources
- Windows Security Event ID 4688 (Process Creation)
- Sysmon Event ID 1 (Process Execution)
- Transport: Splunk HTTP Event Collector (HEC)

---

## Alert / Detection Evidence
The following activity triggered investigation:
- PowerShell execution using `-ExecutionPolicy Bypass`
- Execution of common reconnaissance commands:
  - `whoami`
  - `ipconfig`

These behaviors are frequently associated with post-compromise reconnaissance but may also occur during legitimate administrative or testing activity.

---

## Triage & Investigation

### Analyst Review Included
- Parent process validation
- User account context
- Command-line argument analysis
- Execution lineage and repetition
- Host role and lab environment context

No evidence of lateral movement, privilege escalation, or follow-on malicious activity was observed.

---

## Assessment & Disposition
- **Activity Type:** Process execution / reconnaissance  
- **Severity:** Context-dependent (Low–Medium)  
- **Determination:** False positive (controlled lab context)

The behavior was assessed as benign based on execution context, environmental controls, and the absence of corroborating indicators.

---

## Analyst Action
- Documented investigation steps and analytical rationale
- No escalation required
- Detection logic reviewed for tuning considerations in controlled environments

---

## Lessons Learned
- Cloud SIEM environments may enforce ingestion constraints that differ from self-hosted deployments
- Multiple ingestion methods (agent-based vs API-based) should be evaluated for reliability in enterprise environments
- Consistent telemetry delivery is foundational to effective SOC detection, triage, and tuning
