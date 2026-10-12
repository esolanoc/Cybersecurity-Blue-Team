# 🔹 Sigma Rule - Privilege Escalation Attempts

This rule detects **privilege escalation** in Windows systems by monitoring key Security Event ID 4772.

---

##  Rule Content
```yaml
title: Windows Privilege Escalation Attempt
id: 11111111-2222-3333-4444-555555555555
status: test
description: Detects privilege escalation attempts via special logon.
author: Esteban
date: 2026/10/12
logsource:
  product: windows
  service: security
detection:
  selection:
    EventID: 4672   # Special Logon (privileged accounts)
  condition: selection
falsepositives:
  - Administrators performing normal tasks
level: high
tags:
  - attack.privilege_escalation
  - attack.t1078
