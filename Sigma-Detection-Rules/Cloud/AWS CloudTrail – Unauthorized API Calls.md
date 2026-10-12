# 🔹 Sigma Rule – AWS CloudTrail – Unauthorized API Calls

This rule detects **AWS CloudTrail – Unauthorized API Calls** in Cloud systems by unauthorized API calls in AWS CloudTrail logs.

---

##  Rule Content
```yaml
title: AWS Unauthorized API Call
id: 55555555-6666-7777-8888-999999999999
status: test
description: Detects unauthorized API calls in AWS CloudTrail logs.
author: Esteban
date: 2026/10/12
logsource:
  product: aws
  service: cloudtrail
detection:
  selection:
    errorCode: "UnauthorizedOperation"
  condition: selection
falsepositives:
  - Misconfigured IAM policies
level: high
tags:
  - attack.credential_access
  - attack.t1078
