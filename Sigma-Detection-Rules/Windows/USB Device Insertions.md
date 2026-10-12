# 🔹 Sigma Rule – USB Device Insertions

This rule detects **USB Device Insertions** in Windows systems of external USB storage devices

---

##  Rule Content
```yaml
title: External USB Device Inserted
id: aaaaaaaa-bbbb-cccc-dddd-eeeeeeeeeeee
status: stable
description: Detects insertion of external USB storage devices.
author: Esteban
date: 2026/10/12
logsource:
  product: windows
  service: security
detection:
  selection:
    EventID: 6416
    ClassName: "DiskDrive"
  condition: selection
falsepositives:
  - Normal user activity with USB drives
level: medium
tags:
  - attack.collection
  - attack.t1091
