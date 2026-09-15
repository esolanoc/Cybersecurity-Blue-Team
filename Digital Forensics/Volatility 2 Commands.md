Volatility 2 Commands


Command List
<pre>
volatility -f memdump.mem imageinfo // Take memory image “memdump.mem” and determine the suggested profile for analysis. The profile is the operating system, version, and architecture.
</pre>
<pre>
volatility -f memdump.mem --profile=PROFILE pslist // Take memory image, provide the profile, then use the pslist plugin to print a list of processes to the terminal.
</pre>
<pre>
volatility -f memdump.mem --profile=PROFILE pstree // Use the pstree plugin to print a process tree to the terminal.
</pre>
<pre>
volatility -f memdump.mem --profile=PROFILE psscan // Use the psscan plugin to print all available processes, including hidden ones often used by malware (compare this to pslist to see if there’s any differences!).
</pre>
<pre>
volatility -f memdump.mem --profile=PROFILE psxview // Use the plugin psxview plugin to print expected and hidden processes. This is a combination of pslist and psscan plugins.
</pre>
<pre>
volatility -f memdump.mem --profile=PROFILE procdump -p PIDHERE // Use the procdump plugin to save a process as a file. You must provide a process ID using the -p flag.
</pre>
<pre>
volatility -f memdump.mem --profile=PROFILE netscan // Use the plugin netscan to identify any active or closed network connections.
</pre>
<pre>
volatility -f memdump.mem --profile=PROFILE timeliner // Use the timeliner plugin to create a timeline of events from the memory image.
</pre>
<pre>
volatility -f memdump.mem --profile=PROFILE iehistory // Use the iehistory plugin to pull internet browsing history.
</pre>
<pre>
volatility -f memdump.mem --profile=PROFILE filescan // Use the filescan plugin to identify any files on the system from the memory image.
</pre>
<pre>
volatility -f memdump.mem --profile=PROFILE cmdline -p PIDHERE // Use the cmdline plugin to retrieve any command-line arguments passed to a process. You must provide a process ID using the -p flag.
</pre>
<pre>
volatility -f memdump.mem --profile=PROFILE dumpfiles -n --dump-dir=./ // Use the dumpfiles plugin to retrieve files from the memory image. In this case our terminal is open in the Desktop (root@SBTLab2:~/Desktop) and we are using the output location ./ which tells Volatility to put the files in our current location, the Desktop.
 </pre>
