# 🔐 Windows Artifact - Logon Events

In digital forensics, logon events are crucial to **verify which accounts logged into a system and at what time**.  
This information helps determine **user activity before or during an incident**.

---

## 📌 Key Event IDs

- ⭐ **Special Logon** → Event ID **4672**  
  Grants special privileges to a user (e.g., admin rights).  

- ✅ **Successful Logon** → Event ID **4624**  
  Indicates a user has successfully logged in.  

- ❌ **Failed Logon** → Event ID **4625**  
  Shows an attempt to log in that was unsuccessful.  

- 🚪 **Logoff** → Event ID **4634**  
  Records when a user logs off the system.  

---

## 📍 Location
Logon events are stored in the Windows Event Logs:  

---

## 🛠️ Tools for Analysis
- **Windows Event Viewer** → Native tool to view and analyze logon events.  
- Can be used to **filter by Event ID** and reconstruct user activity timelines.  

---

## ✨ Summary
Logon artifacts provide **critical evidence** in forensic investigations.  
By analyzing Event IDs 4672, 4624, 4625, and 4634, investigators can reconstruct **who accessed the system, when, and how**.
