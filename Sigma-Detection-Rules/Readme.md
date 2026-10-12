# 📖 Sigma Rules Project

## 🔹 Summary
This repository contains a collection of **Sigma detection rules** designed to identify suspicious or malicious activity across different platforms.  
Sigma is a **universal detection language for logs**, allowing analysts to write rules once and apply them across multiple SIEMs (Splunk, Elastic, Wazuh, Sentinel, QRadar, etc.).

The goal of this project is to provide **ready-to-use detection content** for common attack techniques, mapped to MITRE ATT&CK, and organized by operating system or environment.

---

## 🔹 Repository Structure

### `/windows/`
Contains Sigma rules for **Windows Security Events**.  
Examples include:
- Logon and logoff monitoring (Event IDs 4624, 4634, 4647, 4672)  
- Privilege escalation attempts  
- Process creation anomalies (e.g., Word spawning PowerShell)  
- USB device insertions  

---

### `/linux/`
Contains Sigma rules for **Linux system activity**.  
Examples include:
- SSH brute force detection  
- Suspicious command execution (`rm *bash_history`, `history -c`)  
- Privilege escalation attempts (`sudo`, `su`)  
- File tampering and persistence techniques  

---

### `/cloud/`
Contains Sigma rules for **Cloud environments** (AWS, Okta, Azure AD, etc.).  
Examples include:
- AWS CloudTrail events (unauthorized API calls, IAM changes)  
- Okta login failures and account lockouts  
- Azure AD privilege assignments  

---

### `/docs/`
Documentation explaining:
- How Sigma rules are structured (title, logsource, detection, metadata)  
- How to convert rules into queries for different SIEMs using **sigmac**  
- References to MITRE ATT&CK techniques and external resources  
- Best practices for tuning and reducing false positives  

---

## 🔹 What You’ll Find
- **Detection rules** written in YAML format.  
- **Examples** of suspicious activity detection for Windows, Linux, and Cloud.  
- **Documentation** to help you understand, customize, and deploy these rules.  
- **MITRE ATT&CK mapping** for each rule to align with industry standards.  

---

✅ **In short:** This project is a practical Sigma rule library for SOC analysts, security engineers, and students who want to learn how to detect threats across multiple environments and integrate them into their SIEM.

