### Complete TCP/IP Hands-on Lab

#### Lab objective

By the end of this lab, you should be able to:

1. Identify IP, MAC, gateway, and interface information.
2. Understand ARP resolution.
3. Observe Ethernet frames.
4. Observe IPv4 packets.
5. Observe TCP three-way handshake.
6. Observe TCP ports and connections.
7. Run an HTTP service.
8. Generate real HTTP traffic.
9. Capture the complete communication with tcpdump.
10. Analyze the same traffic in Wireshark.
11. Understand encapsulation/decapsulation from an actual packet.
12. Relate OSI layers to TCP/IP layers.
13. Perform basic network-security analysis.

#### Lab topology

```bash
                 Ubuntu 24.04 Host
                 192.168.56.1
                       │
                  vboxnet0
                       │
             Host-Only Network
              192.168.56.0/24
                       │
              ┌────────┴────────┐
              │                 │
       ┌──────▼───────┐   ┌──────▼────────┐
       │ kali-attacker│   │ ubuntu-target │
       │              │   │               │
       │ .10          │   │ .20           │
       │              │   │               │
       │  ATTACKER    │   │    TARGET     │
       └──────────────┘   └───────────────┘
```

Target addressing

| System  | Role            | IP                |
| ------- | --------------- | ----------------- |
| Host    | VirtualBox host | `192.168.56.1`    |
| Kali    | Attacker        | `192.168.56.10`   |
| Ubuntu  | Target          | `192.168.56.20`   |
| Network | Lab             | `192.168.56.0/24` |

Step-01:

Verify VirtualBox

```bash
VBoxManage list vms
```

Look for your Host-Only adapter

```bash
VBoxManage list hostonlyifs
```

Create the Host-Only network

```bash
VBoxManage hostonlyif create
VBoxManage list hostonlyifs
```

Step-02: Configure Kali

```bash
VBoxManage modifyvm "kali-attacker" \
  --nic1 hostonly \
  --hostonlyadapter1 vboxnet0
```

```bash
VBoxManage showvminfo "kali-attacker" --machinereadable | \
grep -E 'nic1|hostonlyadapter1'
```

Step-03: Configure Ubuntu target

```bash
VBoxManage modifyvm "ubuntu-target" \
  --nic1 hostonly \
  --hostonlyadapter1 vboxnet0
```

```bash
VBoxManage showvminfo "ubuntu-target" --machinereadable | \
grep -E 'nic1|hostonlyadapter1'
```

Step-04: Start the two VMs

```bash
VBoxManage startvm "kali-attacker" --type gui
VBoxManage startvm "ubuntu-target"
```

Step-05: Identify the network interfaces

On Kali

```bash
ip -br addr
ip link
ip route
```

```bash
nmcli connection show
```

```bash
sudo nmcli connection modify "Wired connection 1" \
  ipv4.method manual \
  ipv4.addresses 192.168.56.10/24 \
  ipv4.gateway "" \
  ipv4.dns ""
```

```bash
sudo nmcli connection up "Wired connection 1"
sudo nmcli connection down "Wired connection 1"
```

```bash
ping -c 4 192.168.56.20
```

On Ubuntu

```bash
ip -br addr
ip link
ip route
```

```bash
sudo nano /etc/netplan/50-cloud-init.yaml
```

```bash
network:
  version: 2
  ethernets:
    enp0s3:
      dhcp4: false
      addresses:
        - 192.168.56.20/24
```

```bash
sudo netplan try
sudo netplan apply
```

```bash
ping -c 4 192.168.56.10
```

Your basic lab connectivity is now working

```bash
Kali attacker                    Ubuntu target
192.168.56.10                    192.168.56.20
eth1                             enp0s3
   │                                 │
   └──────── vboxnet0 ───────────────┘
             192.168.56.0/24
```
