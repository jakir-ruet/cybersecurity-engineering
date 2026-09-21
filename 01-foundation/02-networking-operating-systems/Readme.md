### Computer Networking & Operating Systems

1. A **computer network** is a collection of interconnected computing devices that communicate with each other using defined communication protocols. A network allows devices to:

- Exchange data
- Share resources
- Provide services
- Access remote systems
- communicate across organizational and geographic boundaries

2. A **networking model** is a conceptual framework that divides network communication into logical layers. Each layer performs specific functions and interacts with the layer above and below it. This provides:

- Modularity
- Interoperability
- Standardization
- Troubleshooting methodology
- Protocol organization
- Security-control placement

> For a security professional, the last point is particularly important.

3. OSI stands for Open Systems Interconnection. The OSI Reference Model is a conceptual networking framework developed by the International Organization for Standardization (ISO) to describe how network communication can be organized into seven logical layers. The seven layers are:

| Layer | OSI Layer        | Hands-on / Protocol Examples                               | Primary Responsibility                                                           | Example Security Issues                                              | Example Security Controls                                               |
| ----: | ---------------- | ---------------------------------------------------------- | -------------------------------------------------------------------------------- | -------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| **7** | **Application**  | HTTP/HTTPS, DNS, SSH, FTP, SMTP, APIs                      | Network services used by applications                                            | SQL injection, XSS, API abuse, command injection                     | WAF, secure coding, API security, input validation                      |
| **6** | **Presentation** | TLS, encoding, encryption, compression                     | Data representation, encoding, encryption concepts                               | TLS/certificate problems, weak encryption, insecure encoding         | PKI, TLS configuration, strong cryptography, certificate management     |
| **5** | **Session**      | Session establishment/maintenance, RPC, session management | Establishing, maintaining, synchronizing, and terminating communication sessions | Session hijacking, session fixation, improper session management     | Secure session management, timeouts, session IDs, re-authentication     |
| **4** | **Transport**    | TCP, UDP, ports, sockets                                   | End-to-end transport, reliability, flow control, port addressing                 | SYN flood, port scanning, UDP flood, connection abuse                | Stateful firewall, rate limiting, connection controls, IDS/IPS          |
| **3** | **Network**      | IPv4/IPv6, IP, ICMP, routing                               | Logical addressing and packet routing                                            | IP spoofing, routing attacks, reconnaissance                         | ACLs, firewalls, routing controls, network segmentation                 |
| **2** | **Data Link**    | Ethernet, Wi-Fi, MAC, ARP, VLAN                            | Framing, MAC addressing, local network delivery                                  | ARP spoofing, MAC flooding, VLAN attacks, rogue DHCP                 | VLAN segmentation, port security, DHCP snooping, Dynamic ARP Inspection |
| **1** | **Physical**     | NIC, virtual NIC, copper, fiber, radio, signals/bits       | Transmission of raw bits/signals over the physical medium                        | Cable tapping, hardware tampering, device theft, physical disruption | Physical access control, locked racks, CCTV, secure facilities          |

```bash
OSI                         TCP/IP 5-Layer

7 Application ───────────┐
6 Presentation ──────────┤
5 Session ───────────────┴── 5 Application
```

#### The Most Important Concept: Encapsulation

As data moves down the networking stack, each layer adds information required for its own operation.

Suppose a user accesses: `https://example.com`

Conceptually

```bash
Application Data
      ↓
Transport Header + Data
      ↓
Network Header + Segment
      ↓
Data-Link Header + Packet + Trailer
      ↓
Bits
```

![Encapsulation](/img/Encapsulation-osi-tcp.png)
