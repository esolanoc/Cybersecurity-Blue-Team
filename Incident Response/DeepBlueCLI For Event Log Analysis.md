# 📊 DeepBlueCLI For Event Log Analysis

	1. Incident Response
	2. Detection and Analysis Phase
	3. DeepBlueCLI For Event Log Analysis
  
Complete 

 
## 🔎 DeepBlueCLI 
Is a PowerShell script that was created by SANS to aid with the investigation and triage of Windows Event logs. This tool can be provided with exported .evtx log files, or can be run on a live system to analyze the local log files.
This tool is able to identify a range of attacks (provided we have the relevant Windows Event logs, or Sysmon logs) such as:
	• User creation
	• Users being added to groups
	• Password guessing
	• Password spraying
	• Bloodhound offensive tool usage
	• Obfuscated commands
	• PowerShell used to download remote files
	• Suspicious service creation
	• Mimikatz used to dump LSASS.exe for credential collection
	• And much more!
 
Below we'll show you how to use this tool to analyze local log files from the system.
 
 
 

# 🛠️ Using DeepBlueCLI
 
In our Downloads folder, we have the DeepBlueCLI folder downloaded from Github and 2 log files that we're going to analyze.
 

 
Inside the folder are all the files related to the tool, including the core PowerShell script “DeepBlue” (DeepBlue.ps1).
 

 
To run the tool we're going to open an administrator-level PowerShell window by searching for ‘PowerShell’, right-clicking the result, and selecting ‘Open as Administrator’. We then need to navigate to the Downloads folder of our user, and into the DeepBlue folder.
 

 
When running it for the first time, we notice there is an error, but this is expected. As the PowerShell script is not digitally signed, Windows is blocking it from executing to try and protect us.
 

 
We can disable this by changing the Execution Policy applied to our user. The command to achieve this is Set-ExecutionPolicy Bypass -Scope CurrentUser.
 

 
Let's run the command again to process Log1.evtx:
<pre>
./DeepBlue.ps1 ../Log1.evtx
(Execute PowerShell script, go up a directory into Downloads, target Log1.evtx)
</pre>

 
In the above screenshot we can see that within this log file, on 4/30/2019 DeepBlue has detected a password spray attack against local user accounts. We get a lot of useful information from this output, such as:
	• A list of targetted user account names
	• Count of user accounts targeted
	• The username of the account conducting the activity
	• The hostname of the system conducting the activity
	• The Event ID that shows this activity
 
Let's go through another example using Log2.evtx. We'll run the same command as before, but change the target file.
 

 
In the above screenshot we can see what DeepBlue has recognised as ‘Suspicious Command Line’ activity which includes a number of long encoded PowerShell commands that have been executed on this system. Based on these results we can further analyze the commands presented and understand what they actually do.
 
Up until now we have been targeting the tool at specific .evtx files. If we are trying to analyze the system we are currently on, we can tell DeepBlue to point at the local system's Security or System event logs directly. The process is the same as above, however we will use the following commands:
<pre>
./DeepBlue.ps1 -log security
./DeepBlue.ps1 -log system
 </pre>
 
 

# ✅Conclusion
 
DeepBlue is a very simple tool to use and allows us to identify suspicious events using pre-determined signatures and patterns from Windows Event logs without having to manually dig through them in Event Viewer or another program.
Time for a lab!
