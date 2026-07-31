# Investigation Notes

## Lab Summary

This investigation focused on reconstructing recent executable activity using native Windows forensic artifacts.

The investigation correlated Windows Recent Items (.lnk shortcuts), running processes, executable paths, and Windows Security Event ID 4688 to validate application execution and reconstruct user activity.

---

## Analyst Methodology

1. Create investigation workspace.
2. Launch built-in Windows applications.
3. Enumerate running processes.
4. Identify executable paths.
5. Examine Windows Recent Items.
6. Review Security Event ID 4688.
7. Correlate evidence.
8. Document findings.
9. Remove lab artifacts.

---

## Investigation Scenario

Several Windows applications were executed during the investigation.

The investigation aimed to determine:

- Which applications were executed.
- Which executables were currently running.
- Whether Windows generated process creation logs.
- Whether Recent Items recorded execution artifacts.
- How multiple evidence sources could reconstruct user activity.

---

## Evidence Collected

### Evidence 1 – Investigation Workspace

Collected:

- Lab directory structure

Finding:

Established investigation baseline.

---

### Evidence 2 – Running Processes

Command Used

```powershell
Get-Process | Sort-Object ProcessName
```

Finding:

Confirmed active Windows processes.

---

### Evidence 3 – Executable Paths

Command Used

```powershell
Get-CimInstance Win32_Process |
Select-Object Name, ExecutablePath
```

Finding:

Validated executable locations.

---

### Evidence 4 – Windows Recent Items

Collected:

- .lnk shortcut files

Finding:

Confirmed recently accessed applications and files.

---

### Evidence 5 – Event Viewer

Collected:

- Security Event ID 4688

Finding:

Confirmed successful process creation events.

---

## DFIR Analysis

The investigation demonstrated how multiple Windows artifacts complement one another during executable investigations.

Running processes provide live execution evidence, executable paths identify binary locations, Recent Items preserve recently accessed applications, and Event ID 4688 independently validates process creation. Correlating these artifacts enables investigators to accurately reconstruct recent user execution activity.

---

## MITRE ATT&CK Mapping

| Tactic | Technique | ID |
|---------|-----------|----|
| Execution | Command and Scripting Interpreter | T1059 |
| Discovery | Process Discovery | T1057 |
| Discovery | File and Directory Discovery | T1083 |

---

## Analyst Observations

- Running processes provide live execution evidence.
- Executable paths identify binary locations.
- Recent Items preserve shortcut artifacts for recently accessed applications.
- Event ID 4688 independently validates process creation.
- Multiple forensic artifacts significantly improve investigation confidence.

---

## Conclusion

The investigation successfully reconstructed recent executable activity using native Windows forensic artifacts by correlating running processes, executable paths, Recent Items shortcuts, and Windows Security Event ID 4688, demonstrating a structured host-based DFIR workflow.
