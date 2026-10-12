# 🔹 Sigma Rule – Windows Logon and Logoff Monitoring

This rule detects **user logon and logoff activity** in Windows systems by monitoring key Security Event IDs.

---

##  Rule Content
```yaml
title: Windows Logon and Logoff Monitoring
id: 9a8b7c6d-1234-5678-9101-abcdef987654
status: stable
description: Detects user logon and logoff activity in Windows systems.
author: Esteban
date: 2026/10/12
logsource:
  product: windows
  service: security
detection:
  selection:
    EventID:
      - 4624   # User Logon Successful
      - 4672   # Special Logon (privileged accounts)
      - 4647   # User Initiated Logoff
      - 4634   # User Logoff
  condition: selection
falsepositives:
  - Normal user activity (expected logons/logoffs)
level: informational
tags:
  - attack.persistence
  - attack.privilege_escalation
  - attack.t1078

