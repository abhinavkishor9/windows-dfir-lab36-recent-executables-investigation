# Investigation Timeline

| Time | Activity | Evidence |
|------|----------|----------|
| 08:03 | Created investigation workspace | PowerShell |
| 08:04 | Created Executables folder | PowerShell |
| 08:08 | Launched Windows applications | Notepad, Calculator, Paint |
| 08:10 | Enumerated running processes | Get-Process |
| 08:12 | Enumerated executable paths | Get-CimInstance |
| 08:15 | Examined Windows Recent Items | .lnk files |
| 08:18 | Reviewed Security Event ID 4688 | Event Viewer |
| 08:22 | Correlated forensic evidence | Documentation |
| 08:25 | Removed investigation workspace | PowerShell |

---

# Investigation Flow

Investigation Started

↓

Created Investigation Workspace

↓

Executed Windows Applications

↓

Enumerated Running Processes

↓

Collected Executable Paths

↓

Examined Recent Items

↓

Reviewed Event ID 4688

↓

Correlated Evidence

↓

Removed Lab Artifacts

↓

Investigation Completed

---

# Summary

The investigation reconstructed recent executable activity by correlating Windows Recent Items (.lnk artifacts), running process enumeration, executable path analysis, and Security Event ID 4688. Using multiple native Windows artifacts provided a reliable method to validate application execution and build a structured host-based DFIR investigation.
