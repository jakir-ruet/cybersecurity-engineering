## Types of Scanning in Cybersecurity

| Scan Type            | Goal                               | What It Actually Does                                | Output                                                              | Tools Used                          | Risk Level  |
| -------------------- | ---------------------------------- | ---------------------------------------------------- | ------------------------------------------------------------------- | ----------------------------------- | ----------- |
| Network Scan         | Find live systems in a network     | Sends ICMP/ARP requests to discover active hosts     | List of active IP addresses + reachable devices                     | Nmap, Angry IP Scanner, Netdiscover | Low         |
| Port Scan            | Identify open ports and services   | Probes TCP/UDP ports to check which are listening    | Open ports, service names, service states (open/closed/filtered)    | Nmap, Masscan, Netcat               | Medium      |
| Service/Version Scan | Identify software running on ports | Extracts service banner and version info             | Service name + version (e.g., Apache 2.4.41, OpenSSH 8.2)           | Nmap (-sV), WhatWeb                 | Medium      |
| OS Fingerprinting    | Detect operating system of target  | Analyzes TCP/IP stack behavior                       | OS type (Windows/Linux), kernel version estimate                    | Nmap (-O), Xprobe2                  | Medium      |
| Vulnerability Scan   | Find security weaknesses           | Compares services/configuration against CVE database | Vulnerability report with severity (Low–Critical) + fix suggestions | Nessus, OpenVAS, Nmap scripts       | High        |
| Web App Scan         | Detect web application flaws       | Tests HTTP inputs, parameters, directories           | SQLi, XSS, auth issues, misconfigurations                           | Nikto, Burp Suite, OWASP ZAP        | High        |
| Credential Scan      | Check weak/default credentials     | Tries common passwords or default logins             | Weak login accounts found                                           | Hydra, Ncrack                       | High        |
| Wireless Scan        | Analyze Wi-Fi networks             | Detects SSIDs, encryption type, clients              | Wi-Fi networks + security level (WEP/WPA/WPA2)                      | Aircrack-ng suite                   | Medium–High |

### Complete Scanning Flow (Real Attack Chain)

`Network Scan` → `Port Scan` → `Service Detection` → `OS Detection` → `Vulnerability Scan` → `Exploitation`

### Example

| Scan Type            | Goal                                   | What It Does                                              | Output                                       | Tools                               | Example Command                       | Risk Level  |
| -------------------- | -------------------------------------- | --------------------------------------------------------- | -------------------------------------------- | ----------------------------------- | ------------------------------------- | ----------- |
| Network Scan         | Find live hosts in a network           | Sends ICMP/ARP requests to detect active systems          | List of active IPs and reachable devices     | Nmap, Netdiscover, Angry IP Scanner | `nmap -sn 192.168.1.0/24`             | Low         |
| Port Scan            | Identify open ports                    | Probes TCP/UDP ports to see which are listening           | Open/closed/filtered ports                   | Nmap, Masscan, Netcat               | `nmap 192.168.1.15`                   | Medium      |
| Service/Version Scan | Identify running services and versions | Extracts service banners from open ports                  | Service name + version (e.g., Apache 2.4.41) | Nmap (-sV), WhatWeb                 | `nmap -sV 192.168.1.15`               | Medium      |
| OS Fingerprinting    | Detect operating system                | Analyzes network stack behavior                           | OS type + kernel estimate                    | Nmap (-O), Xprobe2                  | `nmap -O 192.168.1.15`                | Medium      |
| Full Port Scan       | Scan all ports (1–65535)               | Checks entire port range instead of default top ports     | Complete list of open ports                  | Nmap                                | `nmap -p- 192.168.1.15`               | High        |
| Vulnerability Scan   | Identify security weaknesses           | Matches services against known CVEs and misconfigurations | Vulnerability report with severity + fixes   | Nessus, OpenVAS, Nmap scripts       | `nmap --script vuln 192.168.1.15`     | High        |
| Web App Scan         | Find web application vulnerabilities   | Tests HTTP parameters, directories, inputs                | SQLi, XSS, auth issues, misconfigs           | Nikto, Burp Suite, OWASP ZAP        | `nikto -h http://target`              | High        |
| Credential Scan      | Detect weak/default passwords          | Attempts login with common credentials                    | Weak/compromised accounts                    | Hydra, Ncrack                       | `hydra -l admin -P pass.txt ssh://IP` | High        |
| Wireless Scan        | Analyze Wi-Fi networks                 | Detects SSIDs, encryption, clients                        | Wi-Fi networks + security type               | Aircrack-ng suite                   | `airodump-ng wlan0`                   | Medium–High |

### Scanning Tools

| Category               | Tool Name                   | Type    | Purpose / Use Case                                                    |
| ---------------------- | --------------------------- | ------- | --------------------------------------------------------------------- |
| Multi-Purpose Scanner  | Nmap                        | CLI     | Network discovery, port scanning, OS detection, vulnerability scripts |
| IP Scanner             | Angry IP Scanner            | GUI     | Fast scanning of IP ranges, detects live hosts and open ports         |
| Enterprise Monitoring  | SolarWinds                  | GUI     | Network monitoring, performance tracking, scanning & alerting         |
| Packet Analysis / Scan | Colasoft Ping Tool          | GUI     | Ping testing, latency monitoring, basic network diagnostics           |
| Ping Monitoring        | Visual Ping Tester          | GUI     | Visualizes ping responses, latency tracking                           |
| Ping Scanner           | Ping Scanner Pro            | GUI     | Scans IP ranges using ping sweep                                      |
| Network Discovery      | Ping Sweep                  | CLI/GUI | Detects active hosts via ICMP requests                                |
| Monitoring Tool        | Ping Monitor                | GUI     | Continuously monitors host availability                               |
| Lightweight Tool       | Pinkie                      | GUI     | Includes ping, traceroute, port scan utilities                        |
| Network Utility        | PingInfoView                | GUI     | Simple ping monitoring tool                                           |
| MSP Tool               | PacketTrap MSP              | GUI     | Network monitoring and scanning for managed services                  |
| Vulnerability Scanner  | GFI LanGuard                | GUI     | Patch management and vulnerability scanning                           |
| Network Scanner        | SoftPerfect Network Scanner | GUI     | Scans shared folders, SNMP, network devices                           |
| Vulnerability Scanner  | Nessus                      | GUI     | Industry-standard vulnerability scanning and assessment               |
| Wireless Scanner       | NetStumbler                 | GUI     | Detects Wi-Fi networks and signal strength                            |
| Connectivity Tool      | Ping Tester                 | CLI/GUI | Tests reachability of hosts                                           |
| General Category       | Scanning Tools (Various)    | CLI/GUI | Includes hundreds of tools for different scanning purposes            |

### TCP 3-Way Handshake

Establish a reliable connection between client and server before data transfer.

### TCP 3-Way Handshake

| Step | Packet  | Direction       | TCP Flags        | Purpose                                    | Seq/Ack              | State Change         | Security Insight                         |
| ---- | ------- | --------------- | ---------------- | ------------------------------------------ | -------------------- | -------------------- | ---------------------------------------- |
| 1    | SYN     | Client → Server | SYN = 1          | Initiates connection request               | Seq = x              | Client: SYN-SENT     | Used in **SYN scan** to probe open ports |
| 2    | SYN-ACK | Server → Client | SYN = 1, ACK = 1 | Acknowledges request and agrees to connect | Seq = y, Ack = x+1   | Server: SYN-RECEIVED | If received → port is **open**           |
| 3    | ACK     | Client → Server | ACK = 1          | Final confirmation to establish connection | Seq = x+1, Ack = y+1 | Both: ESTABLISHED    | Skipped in **stealth scans** (half-open) |

> - Seq > Sequence
> - Syn > Synchronize
> - Ack > Acknowlwdgement
