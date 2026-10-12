# 📖 Sigma Rules

Sigma is an **open detection rule format** written in YAML. It allows analysts to describe suspicious behaviors in logs and then translate those rules into queries for different SIEMs (Splunk, Elastic, Sentinel, QRadar, etc.).  
Its main strength is **portability**: write once, use anywhere.

---

## 🔹 Structure of a Sigma Rule
A rule is a YAML file with three main sections:

1. **Detection** → what to look for in logs (keywords, field values, conditions).  
2. **Logsource** → the product/service generating logs (Windows, Linux, Okta, firewall, etc.).  
3. **Metadata** → descriptive info (author, date, severity, references, MITRE ATT&CK tags).

---

## 🔹 Basic Example
```yaml
title: Okta User Account Locked Out
id: 14701da0-4b0f-4ee6-9c95-2ffb4e73bb9a
status: test
description: Detects when a user account is locked out.
logsource:
  product: okta
  service: okta
detection:
  selection:
    displaymessage: Max sign in attempts exceeded
  condition: selection
falsepositives:
  - Unknown
level: medium

# 🔹 Detection Principles

- **Selections** → groups of conditions to match  
- **AND / OR logic** → objects = AND, lists = OR  
- **Detection methods**:
  - Keywords (e.g., `rm *bash_history`)  
  - Field values (e.g., `EventID: 6416`)  
  - Lists of values (e.g., `EventID: [4728, 4729, 4730]`)  

---

# 🔹 Practical Examples

## Linux – Bash history tampering
```yaml
title: Bash History Tampering
logsource:
  product: linux
detection:
  keywords:
    - "rm *bash_history"
    - "history -c"
  condition: keywords

