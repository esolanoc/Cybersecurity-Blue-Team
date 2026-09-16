# 📊 SIEM Rules

---

## 📌 Definition
SIEM rules are **search queries** designed to detect specific activity within imported or real-time data.  
They can trigger actions such as:  
- Generating alerts  
- Sending notifications (e.g., email to a team)  
- Recording activity to a separate location  

Rules can run **continuously (real-time detection)** or on a **scheduled basis** (daily, weekly).  

---

## 🛠️ Types of SIEM Rules
1. **Out-of-the-box rules** → Provided by the SIEM vendor to detect generic attacks and suspicious patterns.  
2. **Custom rules** → Written by defenders who understand what is normal activity in their environment.  

---

## 🔎 Examples of SIEM Rule Functionality

### 🔹 Authentication / Account Activity
- Failed logon attempts  
- Login attempts to disabled accounts  
- Use of privileged accounts (local/domain administrator)  
- SID changes (possible privilege escalation)  

### 🔹 Process Execution
- Execution from unusual locations (e.g., temp directories, browser caches)  
- Suspicious process relationships (e.g., Word spawning PowerShell → malicious macro)  
- Detection of known bad hashes (MD5, SHA1, SHA256)  

### 🔹 Network Activity
- Port scans  
- Service enumeration  
- Host discovery  

---

## 🚨 False Positive Reduction and Tuning
- **False positives** = alerts that do not represent malicious events.  
- Example: Monitoring Windows Event ID 4625 (failed logon).  
  - Single failed attempts are common → noisy alerts.  
  - Better approach: set thresholds (e.g., 10 failed logins within 10 minutes).  
- Rules can be tuned to **exclude trusted sources** (e.g., vulnerability scanners) to prevent unnecessary alerts.  

---

## 📝 Writing Search Queries and Alerts
- SIEM rules are essentially **queries**.  
- Once you learn to write queries (e.g., in Splunk SPL), you can set up **alerts**.  
- Example resource: [ELK Stack - Creating Detection Rules](https://www.elastic.co/guide/en/security/current/rules-ui-create.html)  

---

## ✅ Summary
- SIEM rules = queries that detect suspicious activity.  
- Two types: **vendor-provided** and **custom defender-written**.  
- Cover areas like **authentication, process execution, and network activity**.  
- **Tuning** is essential to reduce false positives and improve detection accuracy.  
