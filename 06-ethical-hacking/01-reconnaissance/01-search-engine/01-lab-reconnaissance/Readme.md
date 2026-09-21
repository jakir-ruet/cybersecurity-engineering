## Overview

The reconnaissance phase is the first step in penetration testing where information about a target system is collected, such as open ports, services, and network details.

### Tools Used

- ping
- netdiscover
- nmap
- nikto
- netcat (nc)

### For Ubuntu

- Go to `/etc/netplan/`

```bash
cp 00-installer-config.yaml 00-installer-config.yaml_bak # take backup
sudo vi 00-installer-config.yaml
```

```bash
# This is the network config written by 'subiquity'
network:
  version: 2
  renderer: networkd
  ethernets:
    enp0s8:
      dhcp4: no
      addresses:
        - 192.168.1.31/24
      routes:
        - to: default
          via: 192.168.1.1
      nameservers:
        addresses:
          - 8.8.8.8
          - 8.8.4.4
```

```bash
netplan try
netplan apply
sudo systemctl restart systemd-networkd
netplan –debug  apply
ifconfig
```

### For Kali Linux

```bash
sudo vi /etc/network/interfaces
```

```bash
auto eth0
iface eth0 inet static
    address 192.168.1.31
    netmask 255.255.255.0
    gateway 192.168.1.1
    dns-nameservers 8.8.8.8 8.8.4.4

auto lo
iface lo inet loopback
```

```bash
sudo systemctl restart NetworkManager
sudo service networking restart
```

### On Kali Linux

| Step | Command                         | Purpose                   | Expected Outcome                                 |
| ---- | ------------------------------- | ------------------------- | ------------------------------------------------ |
| 1    | `ping -c 4 192.168.1.51`        | Check connectivity        | Confirms target is alive (ICMP reply)            |
| 2    | `netdiscover -r 192.168.1.0/24` | Discover hosts in network | Lists active devices + MAC addresses             |
| 3    | `nmap 192.168.1.51`             | Basic scan                | Shows open ports                                 |
| 4    | `nmap -sV 192.168.1.51`         | Service version detection | Identifies service versions (e.g., SSH, Apache)  |
| 5    | `nmap -O 192.168.1.51`          | OS detection              | OS (Linux/Ubuntu)                                |
| 6    | `nmap -A 192.168.1.51`          | Aggressive scan           | Full details (OS, services, scripts, traceroute) |
| 7    | `nmap -p- 192.168.1.51`         | Scan all ports            | Finds hidden/open ports (1–65535)                |
| 8    | `nikto -h http://192.168.1.51`  | Web vulnerability scan    | Detects vulnerabilities & misconfigurations      |
| 9    | `nc 192.168.1.51 80`            | Banner grabbing           | Retrieves server info (e.g., Apache version)     |
