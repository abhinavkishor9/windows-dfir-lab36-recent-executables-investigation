# windows-dfir-lab36-recent-executables-investigation
## Overview

Windows records evidence of recently accessed files and applications through **Recent Items (.lnk shortcuts)** while Security Event ID **4688** records process creation events. Together, these artifacts allow investigators to reconstruct user execution activity, identify recently launched programs, and validate execution timelines.

In this hands-on DFIR lab, a controlled investigation workspace was created before launching several built-in Windows applications. Native Windows tools and PowerShell were then used to examine running processes, executable paths, Windows Recent Items, and Security Event ID 4688 to correlate evidence across multiple forensic artifacts.

---

# Executive Summary

This investigation demonstrates how native Windows forensic artifacts can be used to reconstruct recent executable activity without relying on third-party forensic software. By correlating Recent Items shortcuts, running process information, executable paths, and Windows Security logs, the investigation successfully identified recently executed applications and validated process creation events.

The workflow follows a practical DFIR methodology consisting of evidence generation, artifact collection, correlation, validation, and documentation.

---

# Investigation Objectives

- Create a controlled investigation workspace.
- Generate executable activity using built-in Windows applications.
- Enumerate active processes.
- Identify executable paths.
- Examine Windows Recent Items (.lnk files).
- Validate execution using Security Event ID 4688.
- Correlate evidence from multiple forensic artifacts.
- Document investigation findings.

---

# Skills Demonstrated

- Windows Process Investigation
- Windows Recent Items Analysis
- Windows Security Log Analysis
- Event ID 4688 Investigation
- Host-Based DFIR
- PowerShell Process Enumeration
- Executable Path Analysis
- Evidence Correlation
- Incident Documentation
- Digital Forensic Methodology

---

# Tools Used

- Windows 10
- Windows PowerShell
- Event Viewer
- File Explorer

---

# Lab Environment

| Component | Details |
|-----------|---------|
| Operating System | Windows 10 |
| Investigation Type | Host-Based DFIR |
| Analysis Method | Native Windows Tools |
| Primary Artifact | Windows Recent Items (.lnk) |
| Event Log | Security (4688) |
| Shell | Windows PowerShell |
| Privileges | Administrator |

---

# Investigation Workflow

1. Create investigation workspace.
2. Launch Windows applications.
3. Enumerate running processes.
4. Identify executable paths.
5. Examine Recent Items.
6. Review Event ID 4688.
7. Correlate evidence.
8. Remove lab artifacts.

---

# MITRE ATT&CK Mapping

| Technique | Description |
|-----------|-------------|
| T1059 | Command and Scripting Interpreter |
| T1083 | File and Directory Discovery |
| T1057 | Process Discovery |
| T1106 | Native API |

---

# Evidence Collected

- Investigation workspace
- Running process list
- Executable path enumeration
- Windows Recent (.lnk) artifacts
- Security Event ID 4688 logs
- PowerShell outputs
- Event Viewer screenshots

---

# Evidence Correlation

The investigation correlated multiple Windows artifacts to reconstruct executable activity:

- Running processes identified active applications.
- Executable paths confirmed binary locations.
- Recent Items (.lnk) recorded recently accessed applications and files.
- Security Event ID 4688 validated process creation events.
- Correlating all artifacts produced a reliable timeline of execution activity.

---

# Investigation Findings

The investigation confirmed that Windows maintains multiple independent artifacts related to executable activity. Recent Items preserve shortcut references to recently opened applications and files, while Event ID 4688 records process creation events. PowerShell process enumeration complements these artifacts by providing real-time execution evidence, enabling investigators to reconstruct user activity with higher confidence.

---

# Key Takeaway

Recent executable investigations should never rely on a single artifact. Combining Windows Recent Items, Security Event ID 4688, running processes, and executable path enumeration provides a more complete and reliable picture of application execution during DFIR investigations.
