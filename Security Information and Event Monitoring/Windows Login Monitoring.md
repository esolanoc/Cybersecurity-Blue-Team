# 🔹 Windows Event Logs – Login Monitoring

**Date:** Wednesday, May 6, 2026 – 3:51 PM  

This example demonstrates how **Custom Views** in Windows Event Viewer can be used to monitor employee login and logoff activity. By filtering specific event IDs, administrators can track authentication behavior across systems.

---

## 🔹 Key Event IDs for Login Monitoring
- **4624** → User Logon Successful  
- **4672** → Special Logon (privileged accounts)  
- **4647** → User Initiated Logoff  
- **4634** → User Logoff  

---

## 🔹 Custom View Example
By creating a Custom View in Event Viewer that includes these event IDs, you can quickly monitor:
- When users successfully log in  
- When privileged accounts are used  
- When users log off (both initiated and automatic)  

This helps in **auditing user activity** and detecting anomalies such as unexpected logons or privileged account usage.

---

## 🔹 Splunk Query Example
To integrate these events into Splunk, you can use the following search:

```spl
index=wineventlog sourcetype="WinEventLog:Security"
(EventCode=4624 OR EventCode=4672 OR EventCode=4647 OR EventCode=4634)
| stats count by EventCode, Account_Name, host
| rename EventCode AS "Event ID", Account_Name AS "User", host AS "Machine"
| sort - count
