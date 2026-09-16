# 🖥️ Windows Artifact Programs

Windows artifacts are valuable sources of forensic evidence, as they record user and system activity.  
They can help investigators reconstruct what programs were executed, when, and how.

---

## 🔗 LNK Files (Shortcuts)
- Files that **link to another file**, acting as redirectors.  
- When clicked, the system finds the location of the target file and runs it.  
- 📍 Location:  
- 🛠️ Tool: **Windows File Analyzer**  

---

## 📂 Prefetch Files
- Provide valuable information about programs:  
- Path of the file.  
- When the program was run/executed.  
- When it was installed.  
- 📍 Location:  
- 🛠️ Tools: **Prefetch Explorer**, **PECmd.exe** (command line).  

---

## 📌 Jump List Files
- Contain information about applications **pinned in the taskbar**.  
- Useful for reconstructing user activity and file access.  
- 📍 Location:
-   C:\Users\% USERNAME%\AppData\ Roaming\Microsoft\Windows\Recent\AutomaticDestinations

