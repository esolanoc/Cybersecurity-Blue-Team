# 🔹 Sigma Rule – Process Creation Anomalies (Word spawning PowerShell)

This rule detects **Process Creation Anomalies (Word spawning PowerShell)** in Windows systems by searching for images often link to malicious macros.

---

##  Rule Content
```yaml
title: Suspicious Process Creation - Word Spawning PowerShell
id: 66666666-7777-8888-9999-000000000000
status: test
description: Detects Microsoft Word spawning PowerShell, often linked to malicious macros.
author: Esteban
date: 2026/10/12
logsource:
  product: windows
  category: process_creation
detection:
  parent_process:
    Image|endswith: 'WINWORD.EXE'
  child_process:
    Image|endswith: 'powershell.exe'
  condition: parent_process AND child_process
falsepositives:
  - Rare legitimate automation scripts
level: high
tags:
  - attack.execution
  - attack.t1059.001
