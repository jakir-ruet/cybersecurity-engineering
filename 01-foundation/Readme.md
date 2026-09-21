### Course roadmap

| Module | Topic                         | What you'll learn                                        |
| ------ | ----------------------------- | -------------------------------------------------------- |
| 01     | Computer Architecture         | CPU, registers, ALU, instruction cycle, privilege levels |
| 02     | Memory Architecture           | RAM, virtual memory, paging, segmentation, cache         |
| 03     | Storage & Filesystems         | HDD/SSD, blocks, filesystems, permissions, metadata      |
| 04     | Operating System Architecture | Kernel, system calls, processes, threads                 |
| 05     | Process & Thread Management   | Scheduling, context switching, IPC, synchronization      |
| 06     | Virtualization                | Hypervisor, VM, hardware virtualization, isolation       |
| 07     | Containers                    | Namespaces, cgroups, images, container isolation         |
| 08     | Distributed Systems           | Nodes, RPC, consistency, availability, fault tolerance   |
| 09     | Computing Models              | Client-server, P2P, distributed and cloud computing      |
| 10     | Security Architecture         | Trust boundaries, privilege, isolation, attack surface   |
| 11     | Practical Lab                 | Linux system investigation                               |
| 12     | Assessment                    | Quiz + practical assignment                              |

### Final Lab Architecture

```bash
                         INTERNET
                            │
                            ▼
                     Home/ISP Router
                      192.168.66.1
                            │
                         Wi-Fi
                            │
                    Ubuntu 24.04 Host
                     192.168.66.106
                            │
                       VirtualBox
                            │
              ┌─────────────┴─────────────┐
              │                           │
              │ NAT                       │ Host-Only
              │ Internet                  │ vboxnet0
              │                           │ 192.168.56.0/24
              │                           │
      ┌───────┼───────┐          ┌────────┼─────────┐
      │       │       │          │        │         │
     Kali   Ubuntu  Windows     Kali    Ubuntu    Windows
             Server   Server            Server     AD/DC
                      AD/DC
```

Every VM will have

| NIC   | NIC Card Type        | Purpose                     |
| ----- | -------------------- | --------------------------- |
| NIC 1 | `NAT`                | `VM Output Internet Access` |
| NIC 2 | `Host-Only vboxnet0` | `Private Network Only`      |

> The two networks have completely different purposes.

IP Addressing Plan

| System          | Hostname        | LAB IP          | Role            |
| --------------- | --------------- | --------------- | --------------- |
| Ubuntu Host     | `jakir-hp`      | `192.168.56.1`  | VirtualBox host |
| Kali            | `kali`          | `192.168.56.10` | Attacker        |
| Ubuntu Server   | `ubuntu-target` | `192.168.56.20` | Target          |
| Windows 11      | `windows11`     | `192.168.56.30` | Target          |
| Windows Server  | `DC01`          | `192.168.56.40` | AD/DC + DNS     |
| Wazuh           | `WAZUH01`       | `192.168.56.50` | SIEM            |
| Security Sensor | `SENSOR01`      | `192.168.56.60` | Zeek + Suricata |

1. Computer Networking & Operating Systems
2. Elements of Cryptography
3. Network Security
4. Cloud Security
5. Software & Application Security
6. Digital Forensics
7. Industrial Cyber Security
8. Ethical Hacking & Penetration Testing
8. Malware Analysis
9. Information Security Management
10. Blockchain Technologies & Systems
11. Biometric Security
12. Security in IoT
13. Human Factors in Cyber Security
14. Fault-Tolerant Computer Systems
