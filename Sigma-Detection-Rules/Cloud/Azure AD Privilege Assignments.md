# 🔹 Sigma Rule – Azure AD Privilege Assignments

This rule detects **Azure AD Privilege Assignments** in Cloud systems of privileged roles in Azure AD .

---

##  Rule Content
```yaml
title: Azure AD Privilege Assignment
id: 77777777-8888-9999-aaaa-bbbbbbbbbbbb
status: test
description: Detects assignment of privileged roles in Azure AD.
author: Esteban
date: 2026/10/12
logsource:
  product: azure
  service: active_directory
detection:
  selection:
    Operation: "Add member to role"
    RoleName: "Global Administrator"
  condition: selection
falsepositives:
  - Legitimate admin role assignments
level: high
tags:
  - attack.privilege_escalation
  - attack.t1078
