# 🔹 Sigma Rule – SSH Brute Force Detection

This rule detects **SSH Brute Force Detection** in linux systems for multiple failed SSH login attempts in a short timeframe.

---

##  Rule Content
```yaml
title: SSH Brute Force Attempt
id: ffffffff-1111-2222-3333-444444444444
status: test
description: Detects multiple failed SSH login attempts in a short timeframe.
author: Esteban
date: 2026/10/12
logsource:
  product: linux
  service: sshd
detection:
  selection:
    message: "Failed password"
  timeframe: 10m
  condition: selection | count() > 5
falsepositives:
  - Users mistyping passwords
level: high
tags:
  - attack.credential_access
  - attack.t1110
