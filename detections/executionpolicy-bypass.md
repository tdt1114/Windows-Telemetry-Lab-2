# Detection – PowerShell ExecutionPolicy Bypass

## Description
Detects PowerShell executions using the ExecutionPolicy Bypass flag, a technique frequently observed in adversary tradecraft to weaken script execution controls.

## Data Sources
- Windows Security Event ID 4688  
- (Optionally) Sysmon Event ID 1

## Detection Logic (SPL)
```spl
sourcetype=win:security:4688
| spath
| search Message="*ExecutionPolicy*"
