# Detection – PowerShell ExecutionPolicy Bypass

## Description
Detects PowerShell executions using the ExecutionPolicy Bypass flag, a technique frequently observed in attacker tradecraft to weaken script execution controls.

## Data Sources
- Windows Security Event ID 4688
- Sysmon Event ID 1 (optional corroboration)

## Detection Logic (SPL)
```spl
sourcetype=win:security:4688
| spath
| search Message="*ExecutionPolicy*"
