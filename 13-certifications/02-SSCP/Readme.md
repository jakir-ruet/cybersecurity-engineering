## Overview

Before diving into deep technical topics, ensure you are comfortable with core IT and security concepts:

- **Networking fundamentals:** TCP/IP, DNS, DHCP, routing, switching
- **Operating systems:** Windows Server, Linux (Ubuntu, Red Hat)
- **Security fundamentals:** CIA triad (Confidentiality, Integrity, Availability), AAA (Authentication, Authorization, Accounting)

| **Domain** | **Description**                               | **Weight (%)** |
| :--------: | --------------------------------------------- | :------------: |
|     1      | Security Concepts and Principles              |      16%       |
|     2      | Access Controls                               |      15%       |
|     3      | Risk Identification, Monitoring, and Analysis |      15%       |
|     4      | Incident Response & Recovery                  |      14%       |
|     5      | Cryptography                                  |       9%       |
|     6      | Network & Communications Security             |      16%       |
|     7      | Systems & Application Security                |      15%       |

## Domain 1 Security Concepts and Principles

### Key Topics

- **Security Fundamentals**
  - `CIA Triad` – Confidentiality, Integrity, Availability
  - `AAA` – Authentication, Authorization, Accounting
  - `Security Governance` – Policies, Standards, Procedures
- **Information Security vs Cybersecurity**
  - `InfoSec:` Protecting all forms of information
  - `CyberSec:` Protecting systems, networks, and data from cyber threats
- **Threats and Threat Actors**
  - Malware, ransomware, phishing, social engineering
  - Internal vs external threats, script kiddies, hacktivists, nation-state actors
- **Advanced Persistent Threats (APT) & TTPs**
  - Long-term targeted attacks on organizations
  - Tactics, Techniques, Procedures (TTPs) mapping
- **Risk Management Overview**
  - Threat identification, vulnerability assessment
  - Risk evaluation, mitigation, and reporting
- **Security Controls**
  - Preventive, Detective, Corrective
  - Physical, Technical, Administrative controls
  - Defense in Depth
- **Security Standards & Frameworks**
  - NIST, ISO 27001, COBIT, CIS Controls
  - Legal & regulatory requirements (GDPR, HIPAA, PCI-DSS)
- **Social Engineering & Human Threats**
  - Phishing, Quishing (QR code phishing), baiting
  - Security awareness programs

## Domain 2 Access Controls

### Key Topics

- **AAA Framework** – Identification, Authentication, Authorization, Accounting
  - Ensures only authorized users access resources and tracks activity
- **Authentication Methods**
  - Password-based, Password-less, MFA, Biometric
  - SSO (Single Sign-On), RSO (Remote Sign-On)
- **Authorization Models**
  - DAC – Discretionary Access Control
  - MAC – Mandatory Access Control
  - RBAC – Role-Based Access Control
  - ABAC – Attribute-Based Access Control
- **Access Control Concepts**
  - Principle of Least Privilege
  - Separation of Duties
  - Privileged Account Management
  - Trust relationships (1-way, 2-way, transitive, zero-trust)
- **Accounting/Auditing**
  Tracking user activity for compliance & monitoring
- **Identity & Access Management (IAM) Solutions**
  - Active Directory, LDAP
  - Federated access (OAuth2, SAML)

## Domain 3 Risk Identification, Monitoring, and Analysis

### Key Topics

- **Risk Management Basics**
  - Risk: The potential for loss or harm
  - Threat: Any potential cause of unwanted impact
  - Vulnerability: Weakness in a system
  - Impact/Consequence: Severity of loss
- **Risk Levels and Types**
  - Low, Medium, High, Critical
  - Strategic, Operational, Technical, Compliance risks
- **Risk Identification**
  - Identify assets, threats, vulnerabilities
  - Map which assets are critical
- **Risk Analysis**
  - Qualitative: High, Medium, Low
  - Quantitative: Monetary or numerical analysis
- **Risk Evaluation and Response**
  - Avoidance: Remove the risky activity
  - Mitigation/Reduction: Reduce likelihood/impact
  - Acceptance: Accept the risk
  - Transfer: Insurance or outsourcing
- **Risk Monitoring and Reporting**
  - Continuous assessment
  - Update risk register regularly
- **Risk Frameworks & Standards**
  - NIST RMF, ISO 27005, FAIR
  - Align with policies, compliance, and business objectives

## Domain 4 Incident Response & Recovery

### Key Topics

- **Incident Management Overview**
  - Understanding what constitutes a security incident
  - Types: Malware, unauthorized access, data breach, DoS/DDoS attacks
- **Incident Response Planning (IRP)**
  - Phases of incident response:
  - Preparation – Policies, procedures, tools, training
  - Identification – Detect potential incidents via monitoring/logs
  - Containment – Short-term (stop spread), long-term (prevent recurrence)
  - Eradication – Remove cause (malware, rogue accounts)
  - Recovery – Restore systems to normal operation
  - Lessons Learned – Document, improve future response
- **Digital Evidence Collection**
  - First responder actions
  - Chain of custody
  - Preservation and documentation
- **Incident Metrics & Reporting**
  - Time to detect (TTD), time to respond (TTR)
  - Incident severity levels
  - Reporting to management and compliance bodies
- **Disaster Recovery & Business Continuity**
  - DRP: Restore critical systems quickly
  - BCP: Maintain essential business operations
  - Alternate processing strategies and facilities

## Domain 5 Cryptography

### Key Topics

- **Cryptography Basics**
  - Symmetric Encryption – Same key to encrypt/decrypt (AES, DES)
  - Asymmetric Encryption – Public/private key pair (RSA, ECC)
  - Hashing – Ensures data integrity (SHA-256, MD5)
  - Salting – Protects hashed passwords
  - Digital Signatures – Verify authenticity and integrity
  - Certificates & PKI – Public Key Infrastructure
- **Encryption in Action**
  - Protecting files, emails, network traffic
  - TLS/SSL for secure web communication
- **Key Management**
  - Secure key storage, rotation, and revocation
- **Applications of Encryption**
  - Data at rest: Disk encryption (LUKS, BitLocker)
  - Data in transit: HTTPS, VPN
  - Email: PGP/GPG
- **Web of Trust (WOT)**
  - Decentralized trust model for verifying identities

## Domain 6 Network & Communications Security

### Key Topics

- **Network Fundamentals**
  - OSI Model (Layers 1–7)
  - TCP/IP Protocol Suite
  - LAN, WAN, VLAN, VPN
- **Network Devices & Placement**
  - Switches, routers, firewalls, IDS/IPS, proxies
  - Physical vs logical placement
  - DMZ (Demilitarized Zone)
- **Network Security Concepts**
  - Segmentation, isolation, and air gaps
  - In-band vs out-of-band management
  - Network monitoring & traffic analysis
- **Network Threats & Attacks**
  - DOS, DDOS, MITM (Man-in-the-Middle)
  - Sniffing, spoofing, ARP poisoning
  - Wireless vulnerabilities (RF, Bluetooth, NFC)
- **Security Tools & Technologies**
  - Firewalls (stateful/stateless), VPNs, IDS/IPS
  - Proxy servers, Content filtering
  - Network segmentation and zero-trust concepts
- **IoT & Edge Computing Security**
  - Securing IoT devices and edge nodes
  - Device authentication, encryption, and segmentation
- **DNS & Email Security**
  - Secure DNS (DNSSEC), SPF, DKIM, DMARC for email protection

## Domain 7 Systems & Application Security

### Key Topics

- **Endpoint Security Best Practices**
  - Anti-virus/anti-malware, host firewalls, patch management
  - Device hardening, system updates, and configuration management
- **System Hardening**
  - Secure OS configuration (Windows, Linux)
  - Remove unnecessary services, enforce strong passwords, configure audit policies
- **Data Backup & Recovery**
  - Full, incremental, differential backups
  - Offsite or cloud backup strategies
- **Software Development Security**
  - SDLC & secure coding practices
  - Vulnerability scanning, code review, penetration testing
- **Virtualization & Container Security**
  - Secure VM templates
  - Isolate containers, apply security context, scan container images
- **Enterprise Computing & Cloud Security**
  - Shared responsibility model
  - Storage, computing, network security in the cloud
- **Data Lifecycle Security**
  - Classification, retention, destruction
  - DLP (Data Loss Prevention), DRM (Digital Rights Management)
