## More About Me – [Take a Look!](https://github.com/jakir-ruet)

### Related Security Terms in Table & Diagram

| **Term**                 | **Scope**             | **Focus**                                      | **Examples**                                            |
| ------------------------ | --------------------- | ---------------------------------------------- | ------------------------------------------------------- |
| **Information Security** | Broadest              | Protecting all forms of information            | Locking file cabinets, encrypting data, access policies |
| **IT Security**          | Subset of InfoSec     | Securing IT systems and digital infrastructure | Antivirus, firewalls, system hardening, secure login    |
| **Cybersecurity**        | Subset of IT Security | Protecting systems from internet-based threats | Phishing protection, DDoS defense, threat hunting, WAF  |

![Set Subset Diagram of Security](/img/security-sets.png)

### Course Roadmap

|      # | Course Name                                 | Main Topics                                                                                                                       | Hands-on / Lab Focus                                                   |
| -----: | ------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------- |
|  **1** | **Computing Foundation**                    | Computer architecture, CPU, memory, storage, processes, virtualization, operating-system fundamentals, distributed computing      | Linux system internals, processes, memory, virtualization              |
|  **2** | **Computer Networking & Operating Systems** | OSI/TCP-IP, Ethernet, IP, TCP/UDP, routing, DNS, DHCP, HTTP/HTTPS, Linux, processes, filesystems, permissions                     | Wireshark, tcpdump, Nmap, Linux networking                             |
|  **3** | **Elements of Cryptography**                | CIA triad, encryption, AES, hashing, SHA, HMAC, RSA, ECC, Diffie-Hellman, digital signatures, PKI, certificates, TLS              | OpenSSL, certificates, TLS, encryption/decryption                      |
|  **4** | **Network Security**                        | Network attacks, firewalls, IDS/IPS, VPN, segmentation, DNS security, ARP attacks, MITM, DDoS, Zero Trust                         | Nmap, Wireshark, Suricata, network firewall, packet analysis           |
|  **5** | **Cloud Security**                          | Cloud security architecture, IAM, encryption, key management, VPC security, logging, container/Kubernetes security, cloud threats | AWS IAM, VPC, CloudTrail, GuardDuty, Security Hub, EKS security        |
|  **6** | **Software & Application Security**         | Secure SDLC, threat modeling, OWASP Top 10, authentication, authorization, API security, secure coding, dependency security       | Java/Spring Security, Burp Suite, SAST, DAST, SCA                      |
|  **7** | **Digital Forensics**                       | Digital evidence, disk forensics, memory forensics, filesystem analysis, log analysis, network forensics, incident investigation  | Autopsy, Sleuth Kit, Volatility, Wireshark, forensic timelines         |
|  **8** | **Industrial Cyber Security**               | ICS, SCADA, PLC, RTU, HMI, OT security, industrial protocols, Purdue Model, critical infrastructure                               | OT/ICS security architecture and threat modeling                       |
|  **9** | **Ethical Hacking & Penetration Testing**   | Reconnaissance, scanning, enumeration, vulnerability assessment, exploitation, privilege escalation, reporting                    | Kali Linux, Nmap, Burp Suite, Metasploit, Gobuster, BloodHound         |
| **10** | **Malware Analysis**                        | Malware types, PE/ELF, static analysis, dynamic analysis, indicators of compromise, persistence, C2 concepts                      | YARA, Ghidra, strings, hashes, sandboxing, analysis VM                 |
| **11** | **Information Security Management**         | Security governance, risk, policies, ISO 27001, NIST CSF, CIS Controls, compliance, incident response, BCP/DR                     | Risk assessment, security policies, controls, enterprise security plan |
| **12** | **Blockchain Technologies & Systems**       | Blockchain architecture, consensus, cryptography, smart contracts, blockchain security                                            | Blockchain security analysis, smart-contract concepts                  |
| **13** | **Biometric Security**                      | Biometrics, fingerprint, face, iris, authentication, biometric attacks, privacy                                                   | Biometric authentication/security concepts                             |
| **14** | **Security in IoT**                         | IoT architecture, device security, protocols, authentication, firmware, IoT attacks                                               | IoT threat modeling and security testing                               |
| **15** | **Human Factors in Cyber Security**         | Social engineering, phishing, insider threats, security awareness, human behavior, usable security                                | Phishing analysis, awareness program, human-risk assessment            |
| **16** | **Fault-Tolerant Computer Systems**         | Availability, reliability, redundancy, fault tolerance, distributed systems, HA, recovery                                         | HA architecture, failure simulation, DR design                         |

```bash
cybersecurity-engineering/
│
├── 01-foundation/
│   ├── 01-computing-foundation/
│   ├── 02-networking-operating-systems/
│   └── README.md
│
├── 02-cryptography/
│   ├── labs/
│   ├── assignments/
│   └── README.md
│
├── 03-network-security/
│   ├── labs/
│   ├── assignments/
│   └── README.md
│
├── 04-cloud-security/
│   ├── labs/
│   ├── docker/
│   ├── kubernetes/
│   ├── ci-cd/
│   ├── aws/
│   └── README.md
│
├── 05-application-security/
│   ├── labs/
│   ├── java-spring/
│   ├── api-security/
│   └── README.md
│
├── 06-ethical-hacking/
│   ├── reconnaissance/
│   ├── scanning/
│   ├── enumeration/
│   ├── vulnerability-assessment/
│   ├── exploitation/
│   ├── web-security/
│   ├── network-security/
│   └── README.md
│
├── 07-digital-forensics/
│   ├── labs/
│   ├── disk/
│   ├── memory/
│   ├── network/
│   └── README.md
│
├── 08-malware-analysis/
│   ├── labs/
│   ├── static-analysis/
│   ├── dynamic-analysis/
│   └── README.md
│
├── 09-industrial-security/
│   ├── labs/
│   ├── ics/
│   ├── scada/
│   └── README.md
│
├── 10-security-management/
│   ├── governance/
│   ├── risk/
│   ├── iso-27001/
│   ├── nist/
│   ├── incident-response/
│   └── README.md
│
├── 11-advanced-topics/
│   ├── blockchain/
│   ├── iot-security/
│   ├── biometric-security/
│   ├── human-factors/
│   └── README.md
│
├── 12-capstone/
│   ├── architecture/
│   ├── threat-model/
│   ├── implementation/
│   ├── security-testing/
│   ├── documentation/
│   └── README.md
│
├── 13-certifications/
│   ├── CC/
│   ├── SSCP/
│   ├── CISSP/
│   └── README.md
│
├── 14-lab-infrastructure/
│   ├── virtualbox/
│   ├── kali/
│   ├── ubuntu/
│   ├── windows/
│   ├── wazuh/
│   ├── suricata/
│   ├── zeek/
│   └── README.md
│
├── docs/
│   ├── roadmap.md
│   ├── glossary.md
│   └── references.md
│
├── img/
│
└── README.md
```

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
