# 🔹 Sigma Rule – Suspicious Command Execution

This rule detects **Suspicious Command Execution** in Linux systems by clearing or removing bash history.

---

##  Rule Content
```yaml
title: Bash History Tampering
id: 99999999-aaaa-bbbb-cccc-dddddddddddd
status: stable
description: Detects attempts to clear or remove bash history.
author: Esteban
date: 2026/10/12
logsource:
  product: linux
detection:
  keywords:
    - "rm *bash_history"
    - "history -c"
  condition: keywords
falsepositives:
  - Rare legitimate admin cleanup
level: medium
tags:
  - attack.defense_evasion
  - attack.t1070.003
