# 🖥️ Network Commands Overview

## 🌐 IP Config
- Displays the **IP configuration** of your host.  
- Shows IP address, subnet mask, default gateway, and DNS servers.  
- Useful for troubleshooting connectivity issues.  

---
#  ipconfig (Windows) / ifconfig - ip (Linux)
Displays the local network configuration of the machine. It is the first command executed to validate your own connectivity.

| Command / Parameter | Purpose | Example of use |
| :--- | :--- | :--- |
| ipconfig | Shows basic network information (IPv4, subnet mask, gateway). | ipconfig |
| ipconfig /all | Displays detailed configuration: MAC address, DNS servers, DHCP server, and lease status. | ipconfig /all |
| ipconfig /flushdns | Clears and resets the local DNS resolver cache (useful for troubleshooting DNS issues or after changing a record). | ipconfig /flushdns |
| ipconfig /release and /renew | Releases the current IP address assigned by DHCP and requests a new one from the server. | ipconfig /release<br>ipconfig /renew |

In modern Linux (iproute2), the standard command is *ip*, replacing the obsolete ifconfig.

| Command / Parameter | Purpose | Example of use |
| :--- | :--- | :--- |
| ip a (or ip addr) | Displays all network interfaces, IPv4/IPv6 addresses, and their states (UP/DOWN). | ip a |
| ip r (or ip route) | Shows the main routing table and the default gateway. | ip r |
| ip -s link show <interface> | Displays detailed interface statistics (packets transmitted/received, errors, collisions, drops). | ip -s link show eth0 |
| nmcli dev show | If using NetworkManager, shows the complete network profile including active DNS servers and search domains. | nmcli dev show |
---

## 🛣️ Traceroute / Tracert (Windows)
- Allows you to see the **path data takes** from one host to another.  
- Displays each hop along the route, including latency.  
- Helps identify where packets may be delayed or dropped.  

---
#  tracert (Windows) / traceroute (Linux/Mac)
Shows the hop-by-hop route that packets take to reach a destination, allowing identification of latency or failures at specific hops.

| Command / Parameter | Purpose | Example of use |
| :--- | :--- | :--- |
| tracert <destination> | Traces hops to a domain or IP using ICMP. | tracert 8.8.8.8 |
| tracert -d <destination> | Performs the trace without resolving domain names of the hops, which greatly speeds up the output. | tracert -d google.com |
| tracert -h <max_hops> <destination> | Defines the maximum number of hops to evaluate before stopping the test. | tracert -h 15 192.168.1.1 |

# tracert equivalents in Linux
Linux mainly uses *traceroute* and more advanced interactive alternatives such as *mtr*.

| Command / Parameter | Purpose | Example of use |
| :--- | :--- | :--- |
| traceroute <destination> | Traces hops by sending UDP packets by default (unlike ICMP in Windows). | traceroute 8.8.8.8 |
| traceroute -I <destination> | Forces the use of ICMP echo (same as tracert in Windows) when UDP or TCP are blocked on intermediate routers. | traceroute -I google.com |
| traceroute -T -p <port> <destination> | Uses TCP SYN to a specific port to bypass firewall rules and validate reachability at the service level. | traceroute -T -p 443 target.com |
| mtr <destination> | *(Recommended for Blue Team)* Combines ping and traceroute in a dynamic real-time report measuring packet loss per hop. | mtr --report -c 10 1.1.1.1 |

---

## 🔎 Dig / Nslookup
- Performs **DNS server queries**.  
- Retrieves information about a specific domain (e.g., IP address, MX records).  
- Useful for diagnosing DNS resolution problems.  

---
# nslookup (Windows/Linux) / dig (Linux/Mac)
Used to query DNS records directly from a server and verify name resolution.

| Command / Parameter | Purpose | Example of use |
| :--- | :--- | :--- |
| nslookup <domain> | Direct query of the A record (IP address) of a domain using the default DNS. | nslookup github.com |
| nslookup <domain> <dns_server> | Queries the resolution of a domain pointing to a specific DNS server (e.g., Google 8.8.8.8 or Cloudflare 1.1.1.1). | nslookup malware-domain.com 1.1.1.1 |
| nslookup -type=<type> <domain> | Queries specific record types (MX for mail, TXT, NS, CNAME, ANY). | nslookup -type=MX google.com |
| dig <domain> <type> (Linux) | Returns detailed technical DNS information (ANSWER section, TTL, flags). | dig example.com TXT |

---

## 📊 Netstat
- Monitors all **TCP and UDP connections** on your host.  
- Shows active

---
# netstat
Displays active network connections, listening ports (LISTENING), and TCP/UDP protocol statistics.

| Command / Parameter | Purpose | Example of use |
| :--- | :--- | :--- |
| netstat -ano | Shows all active connections (-a), addresses and ports in numeric format (-n), along with the process ID (-o PID). | netstat -ano |
| netstat -abno | Displays active connections including the executable (.exe) responsible for opening the port/connection. (Requires Administrator privileges). | netstat -abno |
| netstat -ano \ | findstr :<port> | Filters connections to or from a specific port (useful for detecting unusual traffic or verifying local services). | netstat -ano \ | findstr :443 |
| netstat -e -r | Shows network interface statistics (-e) and the local routing table (-r). | netstat -r |

#  netstat equivalents in Linux
Although netstat still exists (via net-tools), the modern and preferred tool for forensic and incident analysis is *ss* (socket statistics), along with direct inspection in /proc.

| Command / Parameter | Purpose | Example of use |
| :--- | :--- | :--- |
| ss -tulpn | Shows all listening sockets (-l) and active connections for TCP (-t) and UDP (-u), displaying PID and process (-p) with numeric IPs (-n). (Requires sudo). | sudo ss -tulpn |
| ss -tan state established | Filters only active TCP connections in ESTABLISHED state (key for detecting beaconing or active C2). | ss -tan state established |
| lsof -i :<port> | Identifies which executable file, user, and PID have a specific network port or socket open. | sudo lsof -i :443 |
| lsof -i -p <PID> | Displays all incoming or outgoing network connections associated with a specific suspicious process. | sudo lsof -i -p 1337 |
