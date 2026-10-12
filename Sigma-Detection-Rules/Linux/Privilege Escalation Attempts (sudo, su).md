# 🔹 Sigma Rule – Privilege Escalation Attempts (sudo, su)

This rule detects **Privilege Escalation Attempts (sudo, su)** in Linux systems by using udo or su commands for privilege escalation.

---

##  Rule Content
```yaml
title: Linux Privilege Escalation Attempt
id: 12345678-9999-8888-7777-666666666666
status: test
description: Detects use of sudo or su commands for privilege escalation.
author: Esteban
date: 2026/10/12
logsource:
  product: linux
detection:
  keywords:
    - "sudo"
    - "su"
  condition: keywords
falsepositives:
  - Normal administrative tasks
level: medium
tags:
  - attack.privilege_escalation
  - attack.t1069
