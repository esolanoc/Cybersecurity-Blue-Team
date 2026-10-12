# 🔹 Sigma Rule – Okta Login Failures and Account Lockouts

This rule detects **Okta Login Failures and Account Lockouts** in Cloud systems when an Okta user account is locked due to failed login attempts.

---

##  Rule Content
```yaml
title: Okta Account Lockout
id: 44444444-3333-2222-1111-000000000000
status: test
description: Detects when an Okta user account is locked due to failed login attempts.
author: Esteban
date: 2026/10/12
logsource:
  product: okta
  service: okta
detection:
  selection:
    displaymessage: "Max sign in attempts exceeded"
  condition: selection
falsepositives:
  - Users forgetting passwords
level: medium
tags:
  - attack.credential_access
  - attack.t1110
