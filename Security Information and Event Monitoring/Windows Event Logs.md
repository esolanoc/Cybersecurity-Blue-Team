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

## 🔹 References
For a deeper dive into Windows Security Events, check out:
- [Ultimate Windows Security Log Encyclopedia](https://www.ultimatewindowssecurity.com/securitylog/encyclopedia/default.aspx)  
- [Andrea Fortuna – Windows Security Event Logs Cheatsheet](https://www.andreafortuna.org/2019/06/12/windows-security-event-logs-my-own-cheatsheet/)  

---

✅ **In short:** Monitoring login and logoff events with Custom Views provides visibility into user activity, supports auditing, and strengthens security detection.
