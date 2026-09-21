**Lab Setup**

- Use **VM environment**:
  - Windows Server (AD + File Server)
  - Ubuntu Linux (server + tools)
  - Kali Linux (optional for scanning)
- **Tools needed:** `Nmap`, `Wireshark`, `OpenVAS`, `OpenSSL`, `Syslog`/`journalctl`

**Real-Time Examples**

| Concept            | Example                                                                                                                                              |
| ------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------- |
| CIA Triad          | Encrypt sensitive customer data (Confidentiality), implement file integrity monitoring (Integrity), ensure database backup & failover (Availability) |
| AAA                | Active Directory login (Authentication), group-based permissions (Authorization), logging login/logout events (Accounting)                           |
| Threat Actor       | Hacktivist defacing a website, internal employee stealing files                                                                                      |
| Defense in Depth   | Firewall → IDS/IPS → Anti-malware → Endpoint controls → Security awareness training                                                                  |
| Social Engineering | An attacker sends a fake email claiming “Reset your password now” to gain credentials                                                                |
