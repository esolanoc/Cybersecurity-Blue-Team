# 🌐 Network Security Controls

---

## 🛡️ Network Intrusion Detection Systems (NIDS)
Can come in the form of software or physical devices that monitor network traffic to generate alerts for analysts to investigate.  

**Positions of NIDS:**  
- 📡 **Inline** → Installed directly in the path of network traffic, all traffic passes through the NIDS.  
- 🔌 **Network Tap** → Connected to a physical network cable.  
- 📥 **Passive** → Connected to a SPAN Port, mirrors traffic to create a copy for analysis.  

---

## 🚫 Network Intrusion Prevention Systems (NIPS)
Similar to NIDS, but can also take **preventive actions** against attacks.  

---

## 🔥 Firewalls
Restrict incoming and outgoing network traffic.  

**Types of Firewalls:**  
- 🖥️ **Standard Firewalls** → Run on dedicated hardware.  
- 💻 **Local Firewalls** → Software installed on devices (e.g., Windows Firewall).  
- 🌐 **Web Application Firewalls (WAF)** → Protect web servers and applications.  

---

## 📜 Log Monitoring
Network devices generate logs that are sent to platforms such as SIEM.  
Logs are normalized and provide analysts with information to investigate and respond to alerts.  

---

## 🔑 Network Access Controls (NAC)
Prevent non-compliant devices from connecting to a network.  
Security teams may require:  
- 📦 Latest patches installed  
- 🧩 Antivirus running  
