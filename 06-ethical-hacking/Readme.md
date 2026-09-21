## More About Me – [Take a Look!](http://www.mjakaria.me)

## Overview

This series of courses and hands-on labs provides comprehensive preparation for the EC-Council® C|EH® (Certified Ethical Hacker) certification. It covers all the essential topics and skills required for both the `312-50 (ECC EXAM)` and `312-50 (VUE)` exam formats, helping learners gain practical experience and exam readiness.

### Ethical Hacking (white-hat hacking)

Ethical hacking is the `legal` and `authorized` practice of `testing computer systems`, `networks`, or `applications` to find and `fix security vulnerabilities` before they can be exploited by malicious attackers. In a word `Ethical hacking means hacking with permission to improve security.`

> **Key Points**

- Done with permission from the owner
- Aims to identify weaknesses in systems
- Helps protect data and prevent cyber attacks
- Follows legal and ethical guidelines

**Necessary Courses**

Let me break it down clearly so you don’t waste time or money.

1. [Certified Ethical Hacker - Beginner](https://github.com/jakir-ruet/ethical-acking-mastering/tree/master/01-ceh), [More](https://www.eccouncil.org/train-certify/certified-ethical-hacker-ceh/)
2. [Cybrary Ethical Hacking - Intermediate](https://github.com/jakir-ruet/ethical-acking-mastering/tree/master/02-ceh), [More](https://www.cybrary.it/certification-prep-courses/penetration-testing-and-ethical-hacking)
3. [Penetration Testing with Kali - Advanced](https://github.com/jakir-ruet/ethical-acking-mastering/tree/master/03-ptk), [More](https://www.offsec.com/courses/pen-200/)
4. [SANS Ethical Hacking Bootcamp - Advanced](https://github.com/jakir-ruet/ethical-acking-mastering/tree/master/04-sans-ceh), [More](https://www.sans.org/mlp/ethical-hacking)

### Understanding Ethical Hacking Series

full Ethical Hacking Series with detailed subcategories for every main topic. I’ve structured it as a comprehensive learning roadmap from Beginner → Advanced

| Level        | Topic                              | Subcategories                                                                                      | What You Learn                                                    |
| ------------ | ---------------------------------- | -------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------- |
| Beginner     | Introducing Ethical Hacking        | –                                                                                                  | Basics, legality, types of hackers, methodologies                 |
| Beginner     | Reconnaissance / Footprinting      | Website, Whois, DNS, IP mapping, Open ports, Social media                                          | Gathering info about targets, both passive and active methods     |
| Beginner     | Scanning Networks                  | Network scanning, Port scanning, Service detection, OS fingerprinting                              | Finding live systems, open ports, and services                    |
| Beginner     | Enumeration                        | User enumeration, Share enumeration, Service enumeration, SNMP, NetBIOS                            | Extracting detailed information about systems and users           |
| Beginner     | Vulnerability Analysis             | Automated tools, Manual assessment, CVE database, Risk prioritization                              | Identifying system and application weaknesses                     |
| Intermediate | System Hacking                     | Password cracking, Privilege escalation, Backdoors, Rootkits                                       | Gaining access, escalating privileges, maintaining access         |
| Intermediate | Malware Threats                    | Viruses, Worms, Trojans, Ransomware, Spyware, Adware                                               | Understanding malware types, attack vectors, and mitigation       |
| Intermediate | Sniffing                           | Packet capturing, Protocol analysis, MITM attacks, ARP poisoning                                   | Capturing and analyzing network traffic to extract sensitive data |
| Intermediate | Social Engineering                 | Phishing, Pretexting, Baiting, Tailgating, Vishing                                                 | Manipulating humans to gain confidential info or access           |
| Intermediate | Denial of Service (DoS)            | Flood attacks, Botnets, Resource exhaustion, SYN/ACK floods                                        | Disrupting system or network availability                         |
| Intermediate | Session Hijacking                  | Cookie theft, TCP/IP hijacking, Man-in-the-middle, Token theft                                     | Taking control of active sessions for unauthorized access         |
| Intermediate | Evading IDS, Firewalls & Honeypots | IDS evasion, Firewall bypass, Honeypot detection, Packet fragmentation                             | Avoiding detection while performing attacks                       |
| Advanced     | Hacking Web Servers                | Apache, Nginx, IIS, Misconfigurations, Directory traversal                                         | Exploiting server vulnerabilities to gain control or data         |
| Advanced     | Hacking Web Applications           | XSS, CSRF, Authentication bypass, File upload attacks, Remote code execution                       | Identifying and exploiting web app vulnerabilities                |
| Advanced     | SQL Injection                      | Error-based, Blind, Union-based, Time-based, Second-order                                          | Exploiting database query flaws for unauthorized access           |
| Advanced     | Hacking Wireless                   | WEP/WPA/WPA2 cracking, Evil Twin, Rogue AP, Packet injection                                       | Attacking Wi-Fi networks and intercepting traffic                 |
| Advanced     | Hacking Mobile                     | Android app vulnerabilities, iOS app vulnerabilities, Reverse engineering, Jailbreak/root exploits | Testing mobile devices and apps for security issues               |
| Advanced     | IoT & OT Hacking                   | Smart devices, SCADA systems, Industrial protocols, Default credentials                            | Attacking connected devices and operational tech systems          |
| Advanced     | Cloud Computing                    | AWS, Azure, Google Cloud, Misconfigurations, API security, IAM flaws                               | Security in cloud environments and SaaS platforms                 |
| Advanced     | Cryptography                       | Symmetric encryption, Asymmetric encryption, Hashing, Digital signatures, Cryptanalysis            | Protecting data and breaking weak encryption schemes              |

**Some Interesting Statistics**

- Cyberattacks occur continuously around the world.
- New malware is created every day.
- Governments invest heavily in cybersecurity.
- Cybercrime is an extremely profitable global industry.
- Skilled hackers can breach networks very quickly.

### Fundamentals of Information Security

| Principle           | Description                                    | Example                          | Control Mechanisms                          |
| ------------------- | ---------------------------------------------- | -------------------------------- | ------------------------------------------- |
| **Confidentiality** | Protect data from unauthorized access          | Encrypting sensitive files       | Encryption (AES), Access Control (IAM)      |
| **Integrity**       | Ensure data is not altered                     | File hash verification           | Hashing (SHA-256), Digital signatures       |
| **Availability**    | Ensure systems/data are accessible when needed | Website uptime                   | Load balancing, backups, DR                 |
| **Authenticity**    | Verify identity of users/systems               | Login with username/password     | MFA, certificates, authentication protocols |
| **Non-repudiation** | Prevent denial of actions                      | Email sender cannot deny sending | Digital signatures, logging, PKI            |

### Types of Attacks

| Attack Type              | Description                      | Example                          | Mitigation                            |
| ------------------------ | -------------------------------- | -------------------------------- | ------------------------------------- |
| **Passive Attacks**      | Monitor data without altering it | Packet sniffing                  | Encryption (TLS), VPN                 |
| **Active Attacks**       | Modify or disrupt systems        | Man-in-the-middle, DoS           | IDS/IPS, firewalls                    |
| **Insider Attacks**      | Performed by trusted users       | Employee stealing data           | Least privilege, monitoring           |
| **Close-in Attacks**     | Require physical proximity       | Shoulder surfing, Wi-Fi sniffing | Physical security, network encryption |
| **Distribution Attacks** | Tampering during supply chain    | Backdoored hardware/software     | Vendor validation, integrity checks   |

### Attack Formula

`Attacks = Motive + Method + Vulnerability`

| Component         | Meaning              | Example                   |
| ----------------- | -------------------- | ------------------------- |
| **Motive**        | Reason behind attack | Financial gain, espionage |
| **Method**        | Technique used       | Phishing, malware         |
| **Vulnerability** | Weakness exploited   | Unpatched system          |

### Cyber Kill Chain Methodology - `R → W → D → E → I → C → A`

| Phase                      | Description                         | Attacker Activity                        | Example                                  | Defense Strategy                      |
| -------------------------- | ----------------------------------- | ---------------------------------------- | ---------------------------------------- | ------------------------------------- |
| **Reconnaissance**         | Gather information about the target | Scanning, OSINT, social engineering      | Collecting employee emails from LinkedIn | WAF, IDS/IPS, threat intelligence     |
| **Weaponization**          | Create malicious payload            | Combine exploit + malware                | Embedding malware in Word/PDF            | Threat intelligence, malware analysis |
| **Delivery**               | Send payload to victim              | Phishing email, USB, malicious link      | Email with infected attachment           | Email filtering, sandboxing           |
| **Exploitation**           | Execute the attack                  | Trigger vulnerability                    | User opens malicious file                | Patch management, EDR                 |
| **Installation**           | Establish persistence               | Install malware/backdoor                 | Registry changes, scheduled tasks        | Application control, EDR              |
| **Command & Control (C2)** | Connect to attacker server          | Remote control communication             | Malware connects to C2 server            | Network monitoring, DNS filtering     |
| **Action on Objectives**   | Achieve attack goal                 | Data theft, ransomware, lateral movement | Exfiltration of database                 | DLP, SIEM, Zero Trust                 |

> - **Reconnaissance:** Is the preliminary survey, exploration, or inspection of an area to gather information about enemy forces, terrain, or resources.
> - **Weaponization**: Is the process of adapting a substance, object, or concept into a tool for causing harm, inflicting injury, or gaining a tactical advantage.
> - **Exploitation:** Is the unfair, manipulative use of a person or resource for personal advantage, often involving coercion, abuse of power, or taking advantage of vulnerability.

### Tactics, Techniques, and Procedures (TTPs)

| Component      | Description                               | Focus Area                    | Example                                            | Detection / Defense                |
| -------------- | ----------------------------------------- | ----------------------------- | -------------------------------------------------- | ---------------------------------- |
| **Tactics**    | High-level goal of the attacker           | *Why* the attack is happening | Initial Access, Persistence, Data Exfiltration     | Security strategy, threat modeling |
| **Techniques** | Methods used to achieve the tactic        | *How* the attack is done      | Phishing, Exploiting vulnerabilities               | IDS/IPS, EDR, SIEM                 |
| **Procedures** | Step-by-step implementation of techniques | *Exactly how* it is executed  | Sending crafted phishing email with malicious link | Threat hunting, behavior analysis  |

### Adversary (Oponent) Behavioral Identification

Its the process of detecting and analyzing malicious actors by observing their patterns of behavior, actions, and techniques within a system or network, rather than relying solely on known signatures or indicators.

| Behavior                              | Description                                                 | Indicators (What to Look For)                                       | Example                                     | Detection / Mitigation                                     | MITRE ATT&CK     |
| ------------------------------------- | ----------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------- | ---------------------------------------------------------- | ---------------- |
| **Internal Reconnaissance**           | Attacker discovers internal assets after initial compromise | Network scans, LDAP queries, account & host enumeration             | Compromised user scanning subnet            | NDR, IDS/IPS, Zero Trust, AD monitoring                    | T1087, T1018     |
| **Suspicious Proxy Events**           | Abnormal outbound traffic via proxy infrastructure          | Rare domains, unusual bandwidth, policy bypass attempts             | User accessing unknown or risky domains     | Proxy log analysis, URL filtering, CASB                    | T1071            |
| **PowerShell Abuse**                  | Malicious use of PowerShell for execution or persistence    | Encoded commands, remote script execution, obfuscation              | Base64-encoded PowerShell payload           | EDR, PowerShell logging, AMSI, script control              | T1059.001        |
| **HTTP User-Agent Anomalies**         | Use of fake or non-standard client identifiers              | Uncommon agents, mismatched browser behavior                        | `curl/7.68.0`, scripted malware agent       | WAF, web log analysis, anomaly detection                   | T1071.001        |
| **CLI Processes**                     | Suspicious command-line activity using native tools         | Abnormal admin commands, privilege escalation attempts              | `whoami`, `net user`, `ipconfig` misuse     | Endpoint monitoring, audit logs, EDR                       | T1059            |
| **Command & Control (C2)**            | Communication with attacker-controlled infrastructure       | Beaconing patterns, repeated outbound traffic, unknown destinations | Periodic connection to suspicious IP/domain | DNS filtering, NDR, firewall rules, threat intel           | T1071, T1095     |
| **Data Exfiltration (DNS Tunneling)** | Stealthy data transfer using trusted protocols like DNS     | High DNS query volume, long/random subdomains, encoded payloads     | `data.exfil.attacker.com`                   | DNS monitoring, DLP, anomaly detection, DNS security tools | T1048, T1071.004 |

### Indicators of Compromise (IoC)

Indicators of Compromise (IoCs) are observable signs or evidence that a system or network may have been breached or is under attack. Some common IoCs mention below table

| Category             | IoC                             | What It Means                            |
| -------------------- | ------------------------------- | ---------------------------------------- |
| **Files & Software** | Unauthorized software/files     | Malware, backdoors, unknown binaries     |
| **Email**            | Suspicious emails               | Phishing, malicious attachments/links    |
| **System Changes**   | Registry & file system changes  | Persistence mechanisms, malware activity |
| **Network**          | Unknown ports/protocols         | Backdoors, covert communication          |
| **Bandwidth**        | Excessive usage                 | Possible data exfiltration               |
| **Hardware**         | Rogue devices                   | Unauthorized USB, network devices        |
| **Availability**     | Service disruption / defacement | DoS or web compromise                    |
| **Identity**         | Unauthorized account usage      | Account takeover, privilege abuse        |

### `IoCs` vs `Behavioral` Detection

| Aspect              | **IoCs (Indicators of Compromise)**                        | **Behavioral Detection (Adversary Behavior)**       |
| ------------------- | ---------------------------------------------------------- | --------------------------------------------------- |
| **Definition**      | Observable evidence that a system **has been compromised** | Detection based on **patterns of attacker actions** |
| **Focus**           | **What happened (evidence)**                               | **How it happened (behavior/pattern)**              |
| **Nature**          | Static (IP, hash, file, domain)                            | Dynamic (activities, sequences, patterns)           |
| **Detection Type**  | Signature-based                                            | Behavior / anomaly-based                            |
| **Effectiveness**   | Good for **known threats**                                 | Effective for **unknown / zero-day attacks**        |
| **Evasion Risk**    | Easy to evade (change IP, hash)                            | Harder to evade (behavior is consistent)            |
| **Examples**        | Malicious IP, file hash, suspicious domain                 | Reconnaissance, lateral movement, C2 communication  |
| **Tools Used**      | Antivirus, IOC feeds, threat intel                         | EDR, SIEM, UEBA                                     |
| **Response Speed**  | Fast for known attacks                                     | May require correlation and analysis                |
| **False Positives** | Lower (specific indicators)                                | Higher (needs tuning)                               |

#### EDR vs SIEM vs UEBA

| Tool     | Full Form                                 | Purpose                                                          | Focus                       | Data Source                                 | Strength                                 |
| -------- | ----------------------------------------- | ---------------------------------------------------------------- | --------------------------- | ------------------------------------------- | ---------------------------------------- |
| **EDR**  | Endpoint Detection & Response             | Detect and respond to threats on endpoints (laptops, servers)    | Endpoint activity           | Process, file, registry, memory logs        | Deep visibility on host attacks          |
| **SIEM** | Security Information and Event Management | Collect, correlate, and analyze logs from all systems            | Centralized log correlation | Network, server, apps, firewall, cloud logs | Enterprise-wide visibility               |
| **UEBA** | User and Entity Behavior Analytics        | Detect abnormal behavior of users and systems using analytics/AI | Behavioral anomalies        | User login patterns, access behavior        | Detect insider threats & unknown attacks |

### Diamond Model of Intrusion Analysis

The Diamond Model was developed by Center for Cyber Intelligence Analysis and Threat Research. It helps analysts understand cyber intrusions by linking four core elements.

| Component          | Description                     | Key Question                     | Example                  |
| ------------------ | ------------------------------- | -------------------------------- | ------------------------ |
| **Adversary**      | The attacker or threat actor    | Who is attacking?                | Hacker group, insider    |
| **Capability**     | Tools, malware, techniques used | How is the attack performed?     | Malware, exploit kits    |
| **Infrastructure** | Systems used to launch attack   | Where does the attack come from? | C2 servers, domains, IPs |
| **Victim**         | Target of the attack            | Who is being attacked?           | Organization, user       |

### Hacking Concepts

`Hacking is exploiting security controls either in a technical, physical or a human-based element` by `Kevin Mitnick`

#### Three areas of exploitation

##### 1. Technical exploitation

Attacking software, hardware, or network vulnerabilities, like

- `Buffer overflows`– injecting malicious code into memory.
- `SQL injection` – manipulating database queries.
- `Exploiting` unpatched vulnerabilities (e.g., EternalBlue).

> **Why it works:** Software is complex, and bugs are inevitable.

##### 2 Physical exploitation

Bypassing physical barriers to access systems or data, like:

- `Tailgating` – following an authorized person through a secure door.
- `Dumpster diving` – retrieving discarded documents or devices.
- `Lock picking` or bypassing badge readers.

> **Why it works:** Physical security is often overlooked or poorly enforced.

##### 3. Human-based exploitation (Social Engineering)

Manipulating people into revealing information or performing actions, like

- `Phishing` – fake emails tricking users into clicking malicious links.
- `Pretexting` – inventing a scenario to extract data (e.g., calling IT support for a password reset).
- `Baiting` – leaving an infected USB drive in a parking lot.

> **Why it works:** Humans are often the weakest link due to trust, helpfulness, or lack of awareness.

**Summary**

| Layer     | Controls Needed                                 |
| --------- | ----------------------------------------------- |
| Technical | Firewalls, IAM, encryption, patching            |
| Physical  | CCTV, access control, biometric locks           |
| Human     | Security awareness, phishing training, policies |

#### Types of Hackers

| Type                  | Description                                         | Motivation                          | Skill Level                    | Example                                                   |
| --------------------- | --------------------------------------------------- | ----------------------------------- | ------------------------------ | --------------------------------------------------------- |
| **Black Hat Hackers** | Malicious hackers who exploit systems illegally     | Financial gain, revenge, cybercrime | High to advanced               | Ransomware attackers stealing data                        |
| **White Hat Hackers** | Ethical hackers who test and secure systems legally | Security improvement                | High (certified professionals) | Penetration testers, bug bounty hunters                   |
| **Gray Hat Hackers**  | Operate between legal and illegal boundaries        | Curiosity, reputation               | Medium to high                 | Access system without permission but report vulnerability |
| **Suicide Hackers**   | Attack without concern for consequences             | Ideology, revenge                   | Varies                         | Hackers exposing systems publicly without hiding identity |
| **Script Kiddies**    | Use pre-made tools without deep knowledge           | Fun, curiosity                      | Low                            | Running downloaded hacking tools                          |

#### Types of Cyber Threat Actors

| Threat Actor Type                          | Description                                                               | Motivation                                | Characteristics                                     | Example                      |
| ------------------------------------------ | ------------------------------------------------------------------------- | ----------------------------------------- | --------------------------------------------------- | ---------------------------- |
| **Spy/Cyber Spy**                          | Individuals or groups conducting espionage to steal sensitive information | Intelligence gathering, corporate secrets | Stealthy, long-term access, avoids detection        | Corporate espionage attacker |
| **Cyber Criminals / Organized Crime**      | Groups focused on financial gain through cyber attacks                    | Money (ransomware, fraud, data theft)     | Highly structured, uses malware-as-a-service        | Ransomware gangs             |
| **State-Sponsored Actors**                 | Advanced groups backed by governments                                     | Political, military, strategic advantage  | Highly skilled, well-funded, persistent (APT-level) | Nation-state APT groups      |
| **Hacktivists (Political/Religious)**      | Attackers driven by ideology                                              | Political or religious beliefs            | Defacement, DDoS, data leaks                        | Ideology-driven groups       |
| **Terrorist / Extremist Actors**           | Use cyber attacks to spread fear or disrupt systems                       | Fear, disruption, propaganda              | Targets critical infrastructure                     | Cyber-terror campaigns       |
| **Insider Threats** *(important addition)* | Employees or trusted users misusing access                                | Financial gain, revenge, coercion         | Hard to detect, already inside perimeter            | Disgruntled employee         |

### Hacktivism

Hacktivism refers to cyber attacks carried out by individuals or groups motivated by political, social, or ideological beliefs. Their primary goal is protest or disruption, often targeting governments or corporations through activities like website defacement and DDoS attacks.

#### Hacktivism – Key Characteristics

| Feature                          | Description                                                                 |
| -------------------------------- | --------------------------------------------------------------------------- |
| **Motivation**                   | Ideological / political / social justice / religious beliefs                |
| **Skill Level**                  | Low to medium (some groups can be highly advanced)                          |
| **Visibility**                   | High (they often want publicity and media attention)                        |
| **Impact Style**                 | Disruption, embarrassment, protest, reputation damage                       |
| **Stealth**                      | Low (compared to state-sponsored or cyber espionage actors)                 |
| **Primary Goal**                 | Send a message rather than financial gain                                   |
| **Target Selection**             | Symbolic targets (governments, corporations, controversial orgs)            |
| **Attack Types**                 | Website defacement, DDoS, data leaks, social media hijacking                |
| **Persistence**                  | Low to medium (usually short-term campaigns)                                |
| **Organization Level**           | Loose groups or decentralized communities (sometimes anonymous collectives) |
| **Tool Usage**                   | Publicly available tools (DDoS scripts, leak platforms, exploit kits)       |
| **OpSec (Operational Security)** | Weak to moderate (often careless due to publicity goals)                    |
| **Risk to Organization**         | Reputation damage, service disruption, public trust loss                    |
| **Legal Status**                 | Illegal cybercrime in most jurisdictions                                    |
| **Typical Response**             | Rapid incident response, DDoS mitigation, public communication              |

### Hacking Lifecycle

Hacking follows a lifecycle starting from reconnaissance, scanning, gaining access, maintaining access, and finally clearing tracks. Since no system is fully secure, the goal of cybersecurity is to discourage, misdirect, and slow down attackers while detecting them as early as possible

| Phase                  | ATT&CK Mapping         |
| ---------------------- | ---------------------- |
| **1. Reconnaissance**  | Discovery tactics      |
| **2. Scanning**        | Recon + Discovery      |
| **3. Gaining Access**  | Initial Access         |
| **4. Persistence**     | Persistence techniques |
| **5. Clearing Tracks** | Defense Evasion        |

#### 1. Reconnaissance

Reconnaissance is the first phase of a cyber attack where attackers gather information about a target system, organization, or individuals to find possible entry points.

##### Types of Reconnaissance

| Category | Type         | Risk   | Detection     | How Detection Works                                                             |
| -------- | ------------ | ------ | ------------- | ------------------------------------------------------------------------------- |
| Method   | Passive      | Low    | Hard          | No direct system logs; only OSINT monitoring or external threat intel           |
| Method   | Active       | High   | Easy          | Detected via SIEM/IDS/Firewall (port scans, unusual traffic, repeated requests) |
| Identity | Anonymous    | High   | Hard          | Tracked via IP reputation, VPN/Tor detection, behavior patterns                 |
| Identity | Pseudonymous | Medium | Medium        | Detected through behavioral correlation, device/browser fingerprinting          |
| Target   | Organization | High   | Easy–Medium   | Internal logs, EDR alerts, SIEM correlation, user activity anomalies            |
| Target   | Internet     | Medium | Easy at scale | Honeypots, threat intel feeds, global scan detection                            |

##### Real-World

| Step                              | Type of Recon |
| --------------------------------- | ------------- |
| Search company on Google/LinkedIn | Passive       |
| Scan open ports of server         | Active        |
| Use VPN to hide IP                | Anonymous     |
| Use fake email to collect info    | Pseudonymous  |
| Target internal employees         | Organization  |
| Collect website DNS info          | Internet      |

##### Goal of Reconnaissance

| Goal                      | Description                                                                 |
| ------------------------- | --------------------------------------------------------------------------- |
| Identify Target           | Understand the organization, system, or person being targeted               |
| Collect Information       | Gather IPs, domains, emails, employees, technologies used                   |
| Find Attack Surface       | Discover exposed services, ports, applications, entry points                |
| Identify Vulnerabilities  | Detect weak points (unpatched systems, misconfigurations, weak credentials) |
| Map Network / System      | Understand architecture and infrastructure layout                           |
| Gather Credentials Clues  | Find usernames, emails, patterns for phishing or password attacks           |
| Reduce Risk for Attacker  | Plan attack strategy with minimal detection and maximum success             |
| Enable Next Attack Phases | Prepare for scanning, exploitation, and access                              |

##### Social Engineering

Social Engineering is manipulating people to gain confidential information instead of hacking systems directly. Common Techniques;

- Phishing emails
- Fake phone calls (vishing)
- Fake websites
- Pretexting (fake identity)
- Baiting (malicious USB)

##### ARIN

It's a Regional Internet Registry (RIR) responsible for managing and distributing internet number resources such as:

- IP addresses (IPv4 and IPv6)
- Autonomous System Numbers (ASNs)

**Why it matters in cybersecurity**

ARIN plays an important role in internet infrastructure and security:

- **IP ownership tracking:** Security analysts use ARIN’s database (WHOIS/RDAP) to identify who owns an IP address involved in attacks or suspicious activity.
- **Incident investigation:** Helps trace the origin of malicious traffic.
- **Network accountability:** Organizations registered with ARIN are easier to contact in case of abuse reports.
- **Routing security:** Works alongside global efforts to improve trust in internet routing (like RPKI).

**Where ARIN operates** ARIN covers:

- United States
- Canada
- Parts of the Caribbean and North Atlantic

**Is ARIN in Bangladesh?**

`No` — American Registry for Internet Numbers (ARIN) does not operate in Bangladesh.

**Who manages IP addresses in Bangladesh?**

? Bangladesh is under: 👉 **APNIC**

**APNIC is the Regional Internet Registry (RIR) for:**

- Bangladesh 🇧🇩
- India
- Pakistan
- China
- Australia
- Most of Asia-Pacific

**Local authority in Bangladesh** 👉 Bangladesh Telecommunication Regulatory Commission (BTRC), They regulate ISPs and telecoms, but IP allocation comes from APNIC.

#### 2. Scanning

Scanning is the phase where attackers actively gather detailed technical information about target systems to identify live hosts, open ports, services, and vulnerabilities.

**Key Activities**

| Activity                | Description                                                   |
| ----------------------- | ------------------------------------------------------------- |
| Information Gathering   | Collect technical details about systems and network structure |
| System Identification   | Identify live hosts, operating systems, and running services  |
| Vulnerability Discovery | Detect weaknesses in services, configurations, or software    |

**Tooling**

| Tool Type              | Examples                | Purpose                                 |
| ---------------------- | ----------------------- | --------------------------------------- |
| Port Scanners          | Nmap, Masscan           | Identify open ports and services        |
| Vulnerability Scanners | Nessus, OpenVAS, Qualys | Detect known vulnerabilities in systems |

#### 3. Gaining Access

Gaining Access is the phase where an attacker exploits vulnerabilities to enter a system, network, or application and obtain unauthorized control or access.

**Ways of Gaining Access**

| Method          | Description                                        | Example                                 |
| --------------- | -------------------------------------------------- | --------------------------------------- |
| Via Network     | Exploiting network services or weak configurations | Open ports, unsecured services          |
| Via Application | Exploiting application-level vulnerabilities       | SQL Injection, XSS, vulnerable web apps |
| Via OS          | Exploiting operating system weaknesses             | Privilege escalation, unpatched OS      |

**Goals of Attacker**

| Goal                        | Description                                                 |
| --------------------------- | ----------------------------------------------------------- |
| Access Data                 | Steal sensitive information (files, credentials, databases) |
| Reconfigure or Crash System | Change system settings or cause instability                 |
| Exhaust Resources           | Overload system resources (CPU, memory, bandwidth)          |

**Common Techniques**

| Technique               | Description                           | Example                              |
| ----------------------- | ------------------------------------- | ------------------------------------ |
| Password Cracking       | Guessing or brute-forcing credentials | Weak passwords, credential stuffing  |
| Buffer Overflows        | Exploiting memory handling errors     | Injecting malicious code into memory |
| Session Hijacking       | Stealing active user sessions         | Cookie theft, token interception     |
| Denial of Service (DoS) | Making system unavailable             | Flooding server with requests        |
| Privilege Escalation    | Gaining higher-level access           | User → Admin/root access             |

#### 4. Persistence

Maintaining Access is the phase where an attacker ensures persistent control over a compromised system or network so they can return later and continue operations.

**Activities in Maintaining Access**

| Activity                   | Description                                       | Example                          |
| -------------------------- | ------------------------------------------------- | -------------------------------- |
| PWNing the system          | Full control over the compromised machine         | Root/Admin access gained         |
| Use system as a launch pad | Use compromised host to attack other systems      | Lateral movement inside network  |
| Inject backdoors / trojans | Install hidden access mechanisms                  | Web shell, reverse shell         |
| Revisit system later       | Persistent access even after reboot/login changes | Scheduled tasks, startup scripts |
| Sniff / monitor network    | Capture traffic and credentials                   | Packet sniffing tools            |
| Use system resources       | Use CPU, memory, bandwidth for attacker goals     | Botnets, crypto mining           |
| Hardening by attacker      | Disable logs, hide presence, evade detection      | Log tampering, rootkits          |

**Goals of Maintaining Access**

| Goal              | Description                                      |
| ----------------- | ------------------------------------------------ |
| Persistent Access | Stay connected even after reboots or fixes       |
| Lateral Movement  | Move deeper into the network                     |
| Data Collection   | Continuously steal sensitive data                |
| Stealth Operation | Avoid detection by security tools                |
| Control Expansion | Turn single compromise into full network control |

#### 5. Clearing Tracks

Clearing Tracks is the phase where an attacker removes or hides evidence of their activities to avoid detection and investigation.

**Activities in Clearing Tracks**

| Activity                | Description                                | Example                                      |
| ----------------------- | ------------------------------------------ | -------------------------------------------- |
| Destroy proof           | Delete logs and evidence of activity       | Clearing event logs, bash history            |
| Hide malicious activity | Obfuscate or disguise actions              | Renaming tools, hiding processes             |
| Cyber blind             | Disable or bypass monitoring tools         | Disabling antivirus, stopping logging agents |
| Hide files              | Store malware or tools in hidden locations | Hidden directories, steganography            |
| Log manipulation        | Modify or erase audit trails               | Editing system logs                          |
| Anti-forensics          | Techniques to prevent investigation        | Timestamp manipulation, log wiping           |

**Goals of Clearing Tracks**

| Goal                | Description                          |
| ------------------- | ------------------------------------ |
| Remove Evidence     | Eliminate proof of intrusion         |
| Avoid Detection     | Stay invisible to SOC/EDR teams      |
| Delay Investigation | Make forensic analysis harder        |
| Maintain Access     | Ensure persistence without suspicion |

### Types of Attackers, Attack Lifecycle (Stages), Their Methods and Attackers’ Goals

#### Types of Attackers

| Attacker Type                    | Description                                   | Main Goal                                        | Risk Level       |
| -------------------------------- | --------------------------------------------- | ------------------------------------------------ | ---------------- |
| Black Hat Hacker                 | Malicious hacker who breaks systems illegally | Steal data, financial gain, damage systems       | Very High        |
| White Hat Hacker                 | Ethical hacker working legally                | Improve security by finding vulnerabilities      | Low (controlled) |
| Gray Hat Hacker                  | Mix of ethical and unethical behavior         | Explore systems, sometimes report flaws          | Medium           |
| Script Kiddie                    | Unskilled attacker using ready-made tools     | Fun, attention, disruption                       | Medium           |
| Insider Threat                   | Employee or contractor inside organization    | Data theft, sabotage (intentional or accidental) | Very High        |
| APT (Advanced Persistent Threat) | Organized, often state-sponsored attackers    | Espionage, long-term infiltration                | Critical         |

#### Attack Lifecycle (Stages)

| Stage                 | What Happens                                             |
| --------------------- | -------------------------------------------------------- |
| Reconnaissance        | Collect target information (emails, IPs, systems)        |
| Scanning              | Identify open ports, services, vulnerabilities           |
| Gaining Access        | Exploit vulnerabilities or use phishing/password attacks |
| Maintaining Access    | Install backdoors or malware for persistence             |
| Privilege Escalation  | Gain admin/root-level access                             |
| Actions on Objectives | Steal data, disrupt systems, or spy                      |
| Covering Tracks       | Delete logs, hide activity, avoid detection              |

#### Attack Methods

| Method             | Description                    | Example                              |
| ------------------ | ------------------------------ | ------------------------------------ |
| Social Engineering | Manipulating humans            | Phishing email pretending to be bank |
| Malware            | Malicious software             | Ransomware encrypting files          |
| Exploits           | Using software vulnerabilities | Buffer overflow attack               |
| Password Attacks   | Cracking credentials           | Brute force, credential stuffing     |
| DoS/DDoS           | Overloading systems            | Website crash via traffic flood      |
| MITM Attack        | Intercepting communication     | Capturing login credentials on Wi-Fi |

#### Attackers’ Goals

| Method             | Description                    | Example                              |
| ------------------ | ------------------------------ | ------------------------------------ |
| Social Engineering | Manipulating humans            | Phishing email pretending to be bank |
| Malware            | Malicious software             | Ransomware encrypting files          |
| Exploits           | Using software vulnerabilities | Buffer overflow attack               |
| Password Attacks   | Cracking credentials           | Brute force, credential stuffing     |
| DoS/DDoS           | Overloading systems            | Website crash via traffic flood      |
| MITM Attack        | Intercepting communication     | Capturing login credentials on Wi-Fi |

#### Common Techniques Used by Attackers

| Technique         | Purpose                             |
| ----------------- | ----------------------------------- |
| Phishing          | Steal credentials via fake messages |
| Spear Phishing    | Target specific individuals         |
| Keylogging        | Capture keystrokes                  |
| Backdoors         | Maintain long-term access           |
| Botnets           | Control infected devices            |
| Zero-day Exploits | Use unknown vulnerabilities         |

#### Modern Attacker Trends

| Trend                   | Description                             |
| ----------------------- | --------------------------------------- |
| Automation              | Use of bots and AI for attacks          |
| Cloud Targeting         | Attacking AWS, Azure, GCP environments  |
| Hybrid Attacks          | Combining phishing + malware + exploits |
| Human Focus             | Targeting employees more than systems   |
| Ransomware-as-a-Service | Renting ransomware tools                |

### The Levels of Defense in Depth

#### Defense in Depth (Layered Security)

| Layer                              | Description                        | Security Controls                     | Example                                |
| ---------------------------------- | ---------------------------------- | ------------------------------------- | -------------------------------------- |
| Physical Security                  | Protect physical access to systems | CCTV, guards, locks, biometric access | Data center access control             |
| Perimeter Security                 | First line of network defense      | Firewalls, IDS/IPS, VPN               | Blocking unauthorized internet traffic |
| Network Security                   | Internal network protection        | Network segmentation, VLANs, NAC      | Separate HR and Finance networks       |
| Host Security                      | Protect servers and endpoints      | Antivirus, patching, hardening        | Secured Linux/Windows servers          |
| Application Security               | Secure applications and APIs       | WAF, secure coding, input validation  | Prevent SQL injection                  |
| Data Security                      | Protect sensitive data             | Encryption, DLP, access control       | Encrypt database or backups            |
| Identity & Access Management (IAM) | Control user access                | MFA, RBAC, least privilege            | Admin vs user roles                    |
| Monitoring & Logging               | Detect and respond to threats      | SIEM, log monitoring, alerts          | Detect suspicious login                |
| Incident Response                  | Handle security incidents          | Playbooks, SOC, response team         | Respond to ransomware attack           |
| Policies & Awareness               | Human and organizational controls  | Security policies, training           | Employee phishing awareness            |

#### Defense Layers vs Attack Stages

| Attack Stage         | Defense Layer That Stops It    |
| -------------------- | ------------------------------ |
| Reconnaissance       | Perimeter Security, Monitoring |
| Scanning             | Firewall, IDS/IPS              |
| Gaining Access       | IAM, Application Security      |
| Maintaining Access   | Host Security, EDR             |
| Privilege Escalation | IAM, System Hardening          |
| Data Exfiltration    | Data Security, DLP             |
| Covering Tracks      | Logging, SIEM                  |

#### Types of Controls in Each Layer

| Control Type | Description                     | Example                               |
| ------------ | ------------------------------- | ------------------------------------- |
| Preventive   | Stop attacks before they happen | Firewall, MFA                         |
| Detective    | Identify attacks in progress    | SIEM alerts, IDS                      |
| Corrective   | Fix issues after attack         | Patch systems, restore backups        |
| Deterrent    | Discourage attackers            | Warning banners, policies             |
| Compensating | Alternative controls            | Extra monitoring if patch unavailable |

#### Real-World

| Layer       | Example Implementation              |
| ----------- | ----------------------------------- |
| Perimeter   | AWS Security Group + Firewall       |
| Network     | VPC with private/public subnets     |
| Host        | Hardened EC2 (disable root login)   |
| Application | WAF + secure API validation         |
| IAM         | IAM roles + MFA                     |
| Data        | S3 encryption + database encryption |
| Monitoring  | CloudWatch + SIEM                   |
| Response    | Incident response playbook          |

### Risk

Risk is the potential for loss or damage when a threat exploits a vulnerability.

`Risk` = `Threat` `×` `Vulnerability` `×` `Impact`

#### Key Components of Risk

| Component     | Description                    | Example                             |
| ------------- | ------------------------------ | ----------------------------------- |
| Asset         | What you want to protect       | Database, server, application       |
| Threat        | Anything that can cause harm   | Hacker, malware, insider            |
| Vulnerability | Weakness that can be exploited | Weak password, unpatched system     |
| Impact        | Damage if attack happens       | Data loss, financial loss, downtime |

#### Types of Risk

| Risk Type         | Description                      | Example                  |
| ----------------- | -------------------------------- | ------------------------ |
| Technical Risk    | System or software weakness      | Unpatched Linux server   |
| Human Risk        | User mistakes or insider threats | Clicking phishing email  |
| Operational Risk  | Process failure                  | No backup strategy       |
| Compliance Risk   | Violation of laws/regulations    | Not following GDPR/HIPAA |
| Financial Risk    | Monetary loss                    | Ransomware payment       |
| Reputational Risk | Brand damage                     | Data breach exposure     |

#### Risk Management Process

| Step     | Description                           |
| -------- | ------------------------------------- |
| Identify | Find assets, threats, vulnerabilities |
| Assess   | Evaluate likelihood and impact        |
| Treat    | Reduce or control risk                |
| Monitor  | Continuously track risk               |

#### Risk Treatment Strategies

| Strategy | Description                 | Example                      |
| -------- | --------------------------- | ---------------------------- |
| Avoid    | Eliminate the risk          | Stop using vulnerable system |
| Mitigate | Reduce the risk             | Apply patch, enable MFA      |
| Transfer | Shift risk to another party | Insurance, outsourcing       |
| Accept   | Accept the risk             | Low-impact system            |

#### Risk Matrix

| Likelihood ↓ / Impact → | 1 (Low) | 2      | 3      | 4        | 5 (Critical) |
| ----------------------- | ------- | ------ | ------ | -------- | ------------ |
| **5 - Almost Certain**  | Medium  | High   | High   | Critical | Critical     |
| **4 - Likely**          | Medium  | Medium | High   | High     | Critical     |
| **3 - Possible**        | Low     | Medium | Medium | High     | High         |
| **2 - Unlikely**        | Low     | Low    | Medium | Medium   | High         |
| **1 - Rare**            | Low     | Low    | Low    | Medium   | Medium       |

#### Practical Use in Cybersecurity

| Area              | Usage                     |
| ----------------- | ------------------------- |
| SOC               | Prioritize alerts         |
| DevOps            | Secure deployments        |
| Cloud (AWS/Azure) | Risk-based architecture   |
| Compliance        | ISO 27001 risk assessment |
| Management        | Decision making           |

### Threat Modeling

Threat modeling is the process of, `Identifying threats`, `Finding vulnerabilities`, `Improving system security design`.

#### Threat Modeling Process

| Step                         | Description                    | Key Output                                     |
| ---------------------------- | ------------------------------ | ---------------------------------------------- |
| Identify Security Objectives | Define what must be protected  | CIA (Confidentiality, Integrity, Availability) |
| Application Overview         | Understand system architecture | High-level design diagram                      |
| Decompose Application        | Break system into components   | Data flow diagrams (DFD)                       |
| Identify Threats             | Find possible attacks          | Threat list                                    |
| Identify Vulnerabilities     | Find weaknesses                | Vulnerability list                             |
| Improve Design               | Apply security controls        | Secure architecture                            |

#### Identify Threats (STRIDE Model)

| Threat Type            | Description                   | Example                 |
| ---------------------- | ----------------------------- | ----------------------- |
| Spoofing               | Pretending to be someone else | Fake login identity     |
| Tampering              | Changing data                 | Modify database records |
| Repudiation            | Denying actions               | User denies transaction |
| Information Disclosure | Data leakage                  | Exposed API data        |
| Denial of Service      | System unavailability         | Traffic flood           |
| Elevation of Privilege | Gaining higher access         | User → Admin            |

#### Identify Vulnerabilities

| Category                | Example                      |
| ----------------------- | ---------------------------- |
| Authentication Weakness | Weak passwords, no MFA       |
| Authorization Issues    | Improper role control        |
| Input Validation        | SQL Injection, XSS           |
| Configuration Issues    | Open ports, default settings |
| Patch Management        | Outdated software            |
| Logging Gaps            | No monitoring or alerts      |

### Incident Management

Incident management is a structured process to detect, analyze, prioritize, and resolve security incidents to minimize impact and improve system resilience.

#### Think Outside the Box (Security Mindset)

In cybersecurity, this means, Thinking like an attacker, Not relying only on standard patterns, Finding hidden or unexpected risks.

#### Creative Security Thinking Process

| Step       | Description                      | Key Question               |
| ---------- | -------------------------------- | -------------------------- |
| Identify   | Find unusual risks or behaviors  | “What could go wrong?”     |
| Analyze    | Understand impact and root cause | “How can it be exploited?” |
| Prioritize | Rank based on risk level         | “What is most critical?”   |
| Resolve    | Fix and improve controls         | “How do we prevent it?”    |

#### Incident Management Lifecycle

| Phase                    | Description               | Example                    |
| ------------------------ | ------------------------- | -------------------------- |
| Identify                 | Detect incident           | SIEM alert, unusual login  |
| Analyze                  | Investigate and confirm   | Check logs, trace attacker |
| Prioritize               | Assess severity           | Critical vs low incident   |
| Resolve                  | Contain and fix issue     | Block IP, patch system     |
| Recover                  | Restore normal operations | Bring system back online   |
| Review (Lessons Learned) | Improve future response   | Update playbooks           |

#### Benefits of Incident Management

| Benefit                    | Description                        |
| -------------------------- | ---------------------------------- |
| Proactive Security         | Detect threats early before damage |
| Better Service Quality     | Systems remain stable and reliable |
| Reduced Impact             | Minimize damage and downtime       |
| Efficiency                 | Faster detection and response      |
| Productivity               | Less disruption for teams          |
| Availability               | Systems stay online (uptime)       |
| Customer/User Satisfaction | Trust and reliability increase     |

### Incident Handling & Response (IH&R)

IH&R is a structured process to detect, manage, and recover from security incidents while minimizing damage and improving future defense.

**IH&R Process (Step-by-Step)**

| Step  | Phase                           | Description                                              | Example                                    |
| :---: | ------------------------------- | -------------------------------------------------------- | ------------------------------------------ |
|   1   | Preparation                     | Get ready before incidents occur (tools, team, policies) | SIEM setup, IR playbooks, trained SOC team |
|   2   | Incident Recording & Assignment | Log the incident and assign to responsible team          | Ticket created in Jira/ServiceNow          |
|   3   | Triage                          | Validate and classify incident severity                  | False positive vs real attack              |
|   4   | Notification                    | Inform stakeholders and response team                    | Alert SOC, management                      |
|   5   | Containment                     | Limit spread and damage                                  | Isolate infected server                    |
|   6   | Forensic Examination            | Investigate root cause and evidence                      | Analyze logs, malware, memory              |
|   7   | Eradication                     | Remove threat from environment                           | Delete malware, patch vulnerability        |
|   8   | Recovery                        | Restore systems to normal operation                      | Bring services back online                 |
|   9   | Post-Incident Actions           | Learn and improve security                               | Update policies, lessons learned           |

#### Phase Mapping

| Category        | Steps Included                               |
| --------------- | -------------------------------------------- |
| Before Incident | Preparation                                  |
| During Incident | Recording, Triage, Notification, Containment |
| Investigation   | Forensics, Eradication                       |
| After Incident  | Recovery, Post-incident review               |

### AI and ML use in Cybersecurity

AI and ML enhance cybersecurity by detecting anomalies, automating responses, and identifying unknown threats, but they cannot completely stop attacks and must be combined with human expertise and layered security.

#### Role of AI & ML in Cybersecurity

| Area              | How AI/ML Helps                         | Example                        |
| ----------------- | --------------------------------------- | ------------------------------ |
| Threat Detection  | Identifies unusual behavior (anomalies) | Detect abnormal login patterns |
| Malware Detection | Recognizes new/unknown malware          | Zero-day malware detection     |
| Automation        | Responds faster than humans             | Auto-block malicious IP        |
| Prediction        | Anticipates future attacks              | Risk scoring systems           |

#### AI-Based Antivirus

| Feature              | Description                                      |
| -------------------- | ------------------------------------------------ |
| Behavior Analysis    | Detects suspicious actions instead of signatures |
| Zero-Day Detection   | Finds unknown threats                            |
| Real-Time Protection | Continuous monitoring                            |
| Self-Learning        | Improves over time                               |

#### AI vs Botnets

| Aspect    | Traditional Botnet | AI-Enhanced Defense               |
| --------- | ------------------ | --------------------------------- |
| Behavior  | Repetitive traffic | Detects abnormal traffic patterns |
| Detection | Signature-based    | Behavior-based detection          |
| Response  | Manual             | Automated blocking                |

### Payment Card Industry Data Security Standard (PCI DSS)

| Category                                        | Requirement                        | Description                              |
| ----------------------------------------------- | ---------------------------------- | ---------------------------------------- |
| Build & Maintain Secure Network                 | Firewalls, secure configs          | Protect network from unauthorized access |
| Protect Cardholder Data                         | Encryption, masking                | Secure stored and transmitted card data  |
| Maintain Vulnerability Management Program (VMP) | Anti-virus, patching               | Regularly update and fix vulnerabilities |
| Strong Access Control                           | RBAC, MFA                          | Limit access to card data                |
| Monitor & Test Networks                         | Logging, SIEM, penetration testing | Detect and respond to threats            |
| Information Security Policy                     | Policies & training                | Define security rules for organization   |

### ISO/IEC 27001:2013

Global standard for Information Security Management System (ISMS)

| Phase     | Description                    |
| --------- | ------------------------------ |
| Establish | Define ISMS policies and scope |
| Implement | Apply security controls        |
| Maintain  | Operate and monitor controls   |
| Improve   | Continuously enhance security  |

### Health Insurance Portability and Accountability Act (HIPAA)

Protect healthcare data (PHI – Protected Health Information)

| Rule                             | Description                                    |
| -------------------------------- | ---------------------------------------------- |
| Privacy Rule                     | Protect patient data confidentiality           |
| Security Rule                    | Safeguard electronic health data (ePHI)        |
| Transaction & Code Set Standards | Standardize electronic healthcare transactions |
| National Identifier              | Unique IDs for providers/employers             |
| Enforcement Rule                 | Penalties for non-compliance                   |

### PCI DSS vs ISO 27001 vs HIPAA

| Standard  | Focus                | Industry            | Key Goal                |
| --------- | -------------------- | ------------------- | ----------------------- |
| PCI DSS   | Payment security     | Banking, e-commerce | Protect cardholder data |
| ISO 27001 | Information security | All industries      | Build ISMS              |
| HIPAA     | Health data security | Healthcare          | Protect patient data    |

## With Regards, `Jakir`

[![LinkedIn][linkedin-shield-jakir]][linkedin-url-jakir]
[![Facebook-Page][facebook-shield-jakir]][facebook-url-jakir]
[![Youtube][youtube-shield-jakir]][youtube-url-jakir]

### Wishing you a wonderful day! Keep in touch

<!-- Personal profile -->

[linkedin-shield-jakir]: https://img.shields.io/badge/linkedin-%230077B5.svg?style=for-the-badge&logo=linkedin&logoColor=white
[linkedin-url-jakir]: https://www.linkedin.com/in/jakir-ruet/
[facebook-shield-jakir]: https://img.shields.io/badge/Facebook-%231877F2.svg?style=for-the-badge&logo=Facebook&logoColor=white
[facebook-url-jakir]: https://www.facebook.com/jakir.ruet/
[youtube-shield-jakir]: https://img.shields.io/badge/YouTube-%23FF0000.svg?style=for-the-badge&logo=YouTube&logoColor=white
[youtube-url-jakir]: https://www.youtube.com/@mjakaria-ruet/featured
