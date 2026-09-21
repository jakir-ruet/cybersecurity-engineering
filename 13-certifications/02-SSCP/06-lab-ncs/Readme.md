**Lab Setup**

- Ubuntu Linux VM – server & client
- Windows VM – domain controller or endpoint
- Router/Firewall VM – pfSense or virtual router
- Tools: `Wireshark`, `nmap`, `iptables`/`ufw`, `OpenVPN`, `tcpdump`

**Real-Time Examples**

| Concept        | Example                                                            |
| -------------- | ------------------------------------------------------------------ |
| Firewall       | Block all incoming traffic except ports 22/80/443                  |
| IDS/IPS        | Detect suspicious network traffic patterns                         |
| VPN            | Secure remote employee access                                      |
| Segmentation   | Separate HR and Finance VLANs                                      |
| MITM           | Attacker intercepts HTTP traffic → solved with HTTPS/TLS           |
| IoT Security   | Smart cameras require unique credentials & encrypted communication |
| DNSSEC         | Prevents DNS cache poisoning attacks                               |
| Email Security | SPF + DKIM + DMARC prevent email spoofing                          |
