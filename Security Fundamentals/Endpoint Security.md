# 🖥️ Endpoint Security Tools

---

## 🛡️ Host Intrusion Detection Systems (HIDS)
Is software installed on an endpoint that allows for detections of suspicious or malicious activity.  
It works based on rules that are checked against activity to see if it matches a specific malicious pattern.  

---

## 🚫 Host Intrusion Prevention Systems (HIPS)
Is also a software installed but it also takes actions to prevent the malicious activity to continue.  
It works with rules that are written to search for any specific malicious pattern but with a rule that contains an action to take, such as:  
- ❌ Delete the file  
- 🌐 Block the website or IP  
- 🔔 Generate an alert  

---

## 🧩 Anti-Virus
Software installed on any device (desktops, laptops, servers, endpoints).  
It is used to detect and remove malware from systems.  
There are two types:  
- 📝 Signature Based  
- 🤖 Behavior Based  

---

## 📜 Log Monitoring
Endpoints can be configured to send logs to a centralized platform such as a SIEM.  
That data can be aggregated and normalized to allow security analysts to investigate suspicious or unusual activity.  

---

## 🔎 Endpoint Detection & Response (EDR)
Software silently sitting on endpoints to provide logging, monitoring, and reactive capabilities.  
Similar to HIDS or HIPS, these send activity to a centralized platform such as a SIEM to correlate and analyze logs, allowing analysts to investigate suspicious activity.  

---

## 🧪 Vulnerability Scanning
A routine performed on endpoints to detect misconfigurations, security flaws, or vulnerabilities exploitable by attackers.  
Scans can be:  
- 🌐 External or Internal  
- 🔑 Credentialed or Non-credentialed  
