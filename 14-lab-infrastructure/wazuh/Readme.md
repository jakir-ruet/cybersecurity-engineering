## Wazuh

Wazuh is an open-source security platform used for **security monitoring**, **threat detection**, **endpoint protection**, and **compliance monitoring**.

It collects and analyzes security events from endpoints and infrastructure to help security teams detect suspicious activity and investigate incidents.

**Core Wazuh architecture** - Wazuh has three principal components

| Component       | Responsibility                                              | Example                                         |
| --------------- | ----------------------------------------------------------- | ----------------------------------------------- |
| Wazuh Agent     | Collects security data from monitored endpoints             | Monitors authentication logs on Ubuntu          |
| Wazuh Server    | Analyzes events, evaluates rules, and generates alerts      | Detects repeated failed SSH logins              |
| Wazuh Indexer   | Stores and indexes security alerts and related data         | Enables searching and filtering security events |
| Wazuh Dashboard | Provides the web interface for monitoring and investigation | Displays alerts, agents, and security events    |

### Our end-to-end learning curriculum

We will organize the course into 15 modules. Each module will contain theory, architecture, configuration, hands-on exercises, troubleshooting, and a practical assessment.

| Module | Topic                                 | Hands-on outcome                                                                                     |
| ------ | ------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| 01     | SIEM and SOC fundamentals             | Understand SIEM, EDR, XDR, SOC workflows, and Wazuh's role                                           |
| 02     | Wazuh architecture and data flow      | Understand agents, server, indexer, dashboard, and event processing                                  |
| 03     | Lab infrastructure and networking     | Build an isolated VirtualBox lab with appropriate network connectivity                               |
| 04     | Wazuh installation                    | Deploy the all-in-one Wazuh stack                                                                    |
| 05     | Agent deployment and enrollment       | Connect Ubuntu and Kali endpoints to Wazuh                                                           |
| 06     | Log collection and analysis           | Collect Linux authentication, system, and application logs                                           |
| 07     | Security alerts and detection rules   | Investigate alert levels, rules, decoders, and event fields                                          |
| 08     | File Integrity Monitoring             | Detect unauthorized changes to files and directories                                                 |
| 09     | Vulnerability detection and inventory | Identify vulnerable packages and review endpoint inventories                                         |
| 10     | Security Configuration Assessment     | Evaluate endpoint configurations against security policies                                           |
| 11     | Threat detection and threat hunting   | Investigate suspicious activity and map detections to MITRE ATT&CK                                   |
| 12     | Custom rules and decoders             | Build and test custom detection logic                                                                |
| 13     | Incident response and Active Response | Investigate incidents and implement controlled responses                                             |
| 14     | Advanced integrations                 | Explore Windows event monitoring, Sysmon, cloud logs, Docker, and other integrations                 |
| 15     | Production deployment and operations  | Design high availability, access controls, backups, monitoring, upgrades, and operational procedures |

### Design our hands-on Wazuh lab

```bash
                 YOUR PHYSICAL COMPUTER
                      Ubuntu 24.04
                            |
                       VirtualBox
                            |
              +-------------+-------------+
              |                           |
          NAT Network                Host-only Network
          Internet access            Isolated lab access
              |                           |
        +-----+---------------------------+------+
        |                 |                      |
        v                 v                      v
 +-------------+   +---------------+   +----------------+
 | Wazuh Server|   | Ubuntu Target |   |  Kali Linux    |
 |             |   |               |   |                |
 | Wazuh       |   | Wazuh Agent   |   | Wazuh Agent    |
 | Manager     |   | SSH           |   | Security tools |
 | Indexer     |   | System logs   |   | Test activity  |
 | Dashboard   |   | FIM            |   |               |
 +-------------+   +---------------+   +----------------+
        |
        v
  Security Dashboard
  Alerts and Investigation
```

| VM              | vCPU |    RAM |  Storage | Purpose                     |
| --------------- | ---: | -----: | -------: | --------------------------- |
| `wazuh-server`  |    4 |   8 GB | 50–80 GB | All-in-one Wazuh deployment |
| `ubuntu-target` |    2 | 2–4 GB |    25 GB | Linux endpoint monitoring   |
| `kali-attacker` |    2 | 2–4 GB |    25 GB | Controlled security testing |

### Lab Setup

Step 1: Create and Configure

```bash
ip -br addr show vboxnet0
```

**Adapter 2 as Host-only Adapter** on all three VMs. Then start the VMs and run.

For **Wazuh Server** & **Ubuntu Target**, remember you should change **IP Address**

```bash
ip -br addr
ip link show enp0s8
sudo ip link set enp0s8 up
ip -br addr
sudo ip addr add 192.168.56.10/24 dev enp0s8
ip -br addr
ping -c 4 192.168.56.10
```

For **IP** persistent of Wazuh server and target machine.

```bash
sudo cp /etc/netplan/50-cloud-init.yaml \
  /etc/netplan/50-cloud-init.yaml.bak
```

```bash
network:
  version: 2
  ethernets:
    enp0s3:
      dhcp4: true

    enp0s8:
      dhcp4: false
      addresses:
        - 192.168.56.10/24
      dhcp6: false
      accept-ra: false
```

```bash
sudo netplan generate
sudo netplan try
sudo netplan apply
```

For **Kali Server**

```bash
ip -br addr
sudo ip link set eth1 up
sudo ip addr add 192.168.56.30/24 dev eth1
ip -br addr
ping -c 4 192.168.56.30
```

For **IP** persistent of Kali Server

```bash
nmcli device status
nmcli connection show
```

```bash
sudo nmcli connection modify "Wired connection 1" \
  ipv4.method manual \
  ipv4.addresses 192.168.56.30/24 \
  ipv4.never-default yes \
  ipv6.method disabled \
  connection.autoconnect yes
```

```bash
sudo nmcli connection up "Wired connection 1"
ip -br addr
```

```bash
nmcli device status
nmcli connection show
```

If there is no connection profile for **eth0**, create one

```bash
sudo nmcli connection add \
  type ethernet \
  con-name nat-internet \
  ifname eth0 \
  ipv4.method auto \
  ipv6.method auto \
  connection.autoconnect yes
```

```bash
sudo nmcli connection up nat-internet
```

```bash
ip -br addr
ip route
```

> - **For**
> - Wazuh Server (192.168.56.10/24)
> - Ubuntu Server (192.168.56.20/24)
> - Kali Server (192.168.56.30/24)

```bash
                  VirtualBox Lab
                        |
            Host-only Network
             192.168.56.1/24
                        |
          +-------------+-------------+
          |             |             |
          v             v             v
    Wazuh Server   Ubuntu Target   Kali Linux
    .56.10         .56.20          .56.30
          |             |             |
          |        Wazuh Agent   Wazuh Agent
          |             |             |
          +-------------+-------------+
                        |
                 Security Events
                        |
                 Wazuh Dashboard
                        |
                 Alert Investigation
```

### Final Host-only network status

| System        | Interface  | Private IP      |
| ------------- | ---------- | --------------- |
| Ubuntu host   | `vboxnet0` | `192.168.56.1`  |
| Wazuh server  | `enp0s8`   | `192.168.56.10` |
| Ubuntu Target | `enp0s8`   | `192.168.56.20` |
| Kali Linux    | `eth1`     | `192.168.56.30` |

| Property                        | Value             | Status  |
| ------------------------------- | ----------------- | ------- |
| Interface                       | `vboxnet0`        | UP      |
| Host IP                         | `192.168.56.1`    | Correct |
| Netmask                         | `255.255.255.0`   | Correct |
| Network                         | `192.168.56.0/24` | Correct |
| Broadcast                       | `192.168.56.255`  | Correct |
| VirtualBox host-only networking | Active            | Ready   |

## Wazuh Server

Step 1: Verify the Wazuh installation

```bash
free -h
dpkg -l | grep -E 'wazuh|filebeat'
sudo systemctl --no-pager --type=service --all |
grep -E 'wazuh|filebeat'
```

Step 2: Verify the operating system and CPU allocation

```bash
cat /etc/os-release
nproc
df -h /
sudo apt update
```

Step 3: Install Wazuh

```bash
curl -sO https://packages.wazuh.com/4.14/wazuh-install.sh
sudo bash ./wazuh-install.sh -a
```

```bash
https://192.168.56.10
```

## Ubuntu Target Machine

```bash
sudo apt update
sudo apt install -y curl gnupg
```

```bash
sudo install -m 0755 -d /etc/apt/keyrings

curl -fsSL https://packages.wazuh.com/key/GPG-KEY-WAZUH \
  | sudo gpg --dearmor --yes \
      -o /etc/apt/keyrings/wazuh.gpg

sudo chmod 644 /etc/apt/keyrings/wazuh.gpg
```

```bash
echo "deb [signed-by=/etc/apt/keyrings/wazuh.gpg] https://packages.wazuh.com/4.x/apt/ stable main" \
  | sudo tee /etc/apt/sources.list.d/wazuh.list
```

```bash
sudo apt update
sudo apt install -y wazuh-agent
dpkg -l | grep wazuh-agent
systemctl list-unit-files wazuh-agent.service
apt-cache policy wazuh-agent
```

```bash
sudo vi /var/ossec/etc/ossec.conf
```

```bash
<client>
  <server>
    <address>192.168.56.10</address>
    <port>1514</port>
    <protocol>tcp</protocol>
  </server>
</client>
```

```bash
sudo grep -n -A 6 '<client>' /var/ossec/etc/ossec.conf
```

> Need to replace `MANAGER_IP` to `SERVER_IP` (192.168.56.10).

```bash
sudo systemctl daemon-reload
sudo systemctl enable wazuh-agent
sudo systemctl start wazuh-agent
```

```bash
sudo systemctl status wazuh-agent --no-pager
sudo tail -n 30 /var/ossec/logs/ossec.log
```

### On Wazuh Server

```bash
sudo systemctl status wazuh-manager --no-pager
sudo /var/ossec/bin/agent_control -l
```

## Kali Server - Attacker

### Network verification

```bash
ip -br addr
ip route
ping -c 4 192.168.56.10
ping -c 4 192.168.56.20
ping -c 4 8.8.8.8
```

### Install the Wazuh agent

```bash
sudo apt update
sudo apt install -y curl gnupg
```

```bash
sudo install -m 0755 -d /etc/apt/keyrings

curl -fsSL https://packages.wazuh.com/key/GPG-KEY-WAZUH \
  | sudo gpg --dearmor --yes \
      -o /etc/apt/keyrings/wazuh.gpg

sudo chmod 644 /etc/apt/keyrings/wazuh.gpg
```

```bash
echo "deb [signed-by=/etc/apt/keyrings/wazuh.gpg] https://packages.wazuh.com/4.x/apt/ stable main" \
  | sudo tee /etc/apt/sources.list.d/wazuh.list
```

```bash
sudo apt update
sudo apt install -y wazuh-agent
dpkg -l | grep wazuh-agent
```

```bash
sudo vi /var/ossec/etc/ossec.conf
```

```bash
<client>
  <server>
    <address>192.168.56.10</address>
    <port>1514</port>
    <protocol>tcp</protocol>
  </server>
</client>
```

> Need to replace `MANAGER_IP` to `SERVER_IP` (192.168.56.10).

```bash
sudo grep -n -A 6 '<client>' /var/ossec/etc/ossec.conf
```

```bash
sudo systemctl daemon-reload
sudo systemctl enable wazuh-agent
sudo systemctl start wazuh-agent
```

### On Wazuh Server

```bash
sudo systemctl status wazuh-manager --no-pager
sudo ss -lntp | grep ':1515'
sudo /var/ossec/bin/agent_control -l
```

## Understand the monitoring pipeline

```bash
Ubuntu Target                 Kali Linux
192.168.56.20                 192.168.56.30
      |                             |
      |       Wazuh Agents          |
      +--------------+--------------+
                     |
                     | TCP 1514
                     v
             Wazuh Manager
             192.168.56.10
                     |
              Rule evaluation
                     |
                     v
              Wazuh Indexer
                     |
                     v
             Wazuh Dashboard
                     |
              Alert investigation
```

### Generate your first security event

Check SSH on Ubuntu Target

```bash
sudo systemctl status ssh --no-pager
sudo apt update
sudo apt install -y openssh-server
sudo systemctl enable --now ssh
```

### Generate a failed login from Kali

```bash
ssh invaliduser@192.168.56.20
```

## SSH Security Lifecycle Management

The security architecture will be

```bash
					KALI LINUX
					192.168.56.30
			Authorized Security Testing
							|
							| SSH / TCP 22
							v
				UBUNTU TARGET
					192.168.56.20
							|
			+------------+-------------+
			|            |             |
	SSH Server   Auth Logs     System Logs
			|            |             |
			+------------+-------------+
							|
					Wazuh Agent
							|
							| TCP 1514
							v
					WAZUH SERVER
					192.168.56.10
							|
					Wazuh Manager
							|
				Detection Rules
							|
					Wazuh Indexer
							|
				Wazuh Dashboard
							|
			Security Investigation
							|
				Incident Response
```

| Phase | Topic                          | What we will implement                                                                                   |
| ----- | ------------------------------ | -------------------------------------------------------------------------------------------------------- |
| 1     | SSH discovery and baseline     | Inspect SSH services, configuration, users, authentication logs, and network exposure                    |
| 2     | SSH hardening                  | Secure SSH daemon settings, authentication methods, root access, and protocol exposure                   |
| 3     | Identity and access management | Manage SSH users, groups, authorized keys, and least privilege                                           |
| 4     | Authentication lifecycle       | Configure password and public-key authentication, key rotation, revocation, and account lockout policies |
| 5     | Logging and auditing           | Collect SSH authentication, session, and privileged activity logs                                        |
| 6     | Wazuh monitoring               | Verify event collection, agent communication, and alert generation                                       |
| 7     | Threat detection               | Detect invalid usernames, repeated failures, suspicious access, and unexpected privileged activity       |
| 8     | Incident response              | Investigate incidents, contain compromised access, revoke credentials, and recover securely              |
| 9     | Security validation            | Test controls and verify that security policies behave as expected                                       |
| 10    | Continuous security management | Monitor configuration drift, review access, rotate credentials, and maintain evidence for audits         |

### Proactive monitoring

Objective: Identify security weaknesses before an attacker exploits them. For example, you want to determine whether your Ubuntu server has known vulnerabilities or insecure configurations.

#### Step 1 — Check SSH configuration on Ubuntu target

```bash
sudo sshd -T | grep -E 'permitrootlogin|passwordauthentication|maxauthtries'
```
