# 🖥️ Syslog

---

## 📌 Definition
**Syslog (System Logging Protocol)** is used to convey **events or system notification messages** to a designated server called a **Syslog server**.  
It centralizes statistical information from different devices so it can be **analyzed and reviewed**.  

---

## ⚙️ Ports
- **UDP 514 / TCP 514** → Default ports, but not reliable.  
- **TCP 6514** → Secured port (recommended).  

---

## 🧾 Syslog Message Structure
A Syslog message is composed of three components:  
1. **Priority Value (PRI)**  
2. **Header**  
3. **Message**  

---

### 🔹 Priority Value (PRI)
The **PRI** is derived from both the **Facility Code** and the **Severity Level**.  

Formula:  


\[
PRI = (Facility \, Code \times 8) + Severity \, Value
\]



This calculation allows categorization of messages based on their source (facility) and importance (severity).  

---

## ✅ Conclusion
- Syslog = protocol for centralized logging.  
- Default ports: **UDP/TCP 514**, secure port: **TCP 6514**.  
- Message structure: **PRI + Header + Message**.  
- PRI is calculated using **facility code** and **severity level**.  
