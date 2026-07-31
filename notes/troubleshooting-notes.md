# Troubleshooting Notes

## Issue 1

Unable to locate the Recent folder.

### Cause

Incorrect AppData path or Recent Items had not yet been generated.

### Resolution

Verify the location:

```powershell
echo $env:APPDATA
```

Then browse to:

```text
%APPDATA%\Microsoft\Windows\Recent
```

---

## Issue 2

Recent folder contained very few shortcut files.

### Cause

Insufficient application activity.

### Resolution

Launch several Windows applications and reopen files before examining Recent Items.

---

## Issue 3

No Event ID 4688 found.

### Cause

Process Creation Auditing was disabled.

### Resolution

Enable Audit Process Creation through Local Security Policy or Group Policy.

---

## Issue 4

ExecutablePath returned blank values.

### Cause

Some protected system processes do not expose executable paths.

### Resolution

Focus on user processes and applications instead of protected Windows processes.

---

## Issue 5

Unable to remove investigation folder.

### Cause

Files or applications were still open.

### Resolution

Close all running applications before executing:

```powershell
Remove-Item C:\RecentExecutablesLab -Recurse -Force
```

---

## Issue 6

Recent shortcut did not correspond to expected application.

### Cause

Recent Items records recently accessed files and shortcuts rather than every executed executable.

### Resolution

Correlate Recent Items with Event ID 4688 and running processes instead of relying on a single artifact.
