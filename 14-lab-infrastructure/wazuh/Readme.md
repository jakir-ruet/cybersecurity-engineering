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

| VM              | Host-only IP    | vCPU |    RAM | Virtual Disk | Purpose                                               |
| --------------- | --------------- | ---: | -----: | -----------: | ----------------------------------------------------- |
| `wazuh-server`  | `192.168.56.10` |    4 | 4–8 GB |     50–80 GB | All-in-one Wazuh SIEM/XDR                             |
| `ubn-endpoint`  | `192.168.56.20` |    2 | 2–4 GB |        30 GB | Linux endpoint monitoring                             |
| `kali-attacker` | `192.168.56.30` |    2 | 2–4 GB |        30 GB | Authorized security testing                           |
| `elk-server`    | `192.168.56.40` |  2–4 | 6–8 GB |     60–80 GB | Elasticsearch, Logstash, and Kibana                   |
| `win-endpoint`  | `192.168.56.50` |    2 |   4 GB |     50–80 GB | Windows endpoint monitoring with OpenEDR and Filebeat |

```bash
                   PHYSICAL COMPUTER
                      Ubuntu 24.04
                           |
                       VirtualBox
                           |
              +------------+------------+
              |                         |
              v                         v
       NAT NETWORK               HOST-ONLY NETWORK
       Internet Access           192.168.56.0/24
              |                  Isolated Lab Network
              |                         |
              +-------------------------+
                                        |
       +----------------+---------------+----------------+----------------+
       |                |               |                |                |
       v                v               v                v                v
+---------------+ +--------------+ +--------------+ +--------------+ +--------------+
| Wazuh Server  | | Ubuntu       | | Kali Linux   | | ELK Server   | | Windows      |
|               | | Endpoint     | |              | |              | | Endpoint     |
| 192.168.56.10 | | .20          | | .30          | | .40          | | .50          |
|               | |              | |              | |              | |              |
| Wazuh Manager | | Wazuh Agent  | | Security     | | Logstash     | | OpenEDR      |
| Wazuh Indexer | | SSH          | | Tools        | | Elasticsearch| | Filebeat     |
| Dashboard     | | System Logs  | | Test Activity| | Kibana       | | Telemetry    |
|               | | File Integrity| |              | |              | |              |
+-------+-------+ +--------------+ +--------------+ +--------------+ +--------------+
        |
        v
+----------------------+
| Wazuh Security       |
| Dashboard            |
|                      |
| Alerts, Monitoring,  |
| and Investigation    |
+----------------------+
```

**Note** The diagram assumes that each VM has a host-only interface on `192.168.56.0/24`. Configure NAT separately on VMs that need Internet access. NAT alone does not automatically create a shared network between all VMs.

**OpenEDR-to-ELK data flow** The Windows endpoint will send OpenEDR telemetry to the ELK server through Filebeat and Logstash.

```text
+--------------------------------+
| Windows Endpoint               |
| 192.168.56.50                  |
|                                |
|  +--------------------------+  |
|  | OpenEDR Agent            |  |
|  +------------+-------------+  |
|               |                |
|               v                |
|  +--------------------------+  |
|  | OpenEDR Telemetry Files  |  |
|  +------------+-------------+  |
|               |                |
|               v                |
|  +--------------------------+  |
|  | Filebeat                 |  |
|  +------------+-------------+  |
+---------------|----------------+
                |
                | TCP 5044
                v
+--------------------------------+
| ELK Server                     |
| 192.168.56.40                  |
|                                |
|  +--------------------------+  |
|  | Logstash                 |  |
|  +------------+-------------+  |
|               |                |
|               v                |
|  +--------------------------+  |
|  | Elasticsearch            |  |
|  +------------+-------------+  |
|               |                |
|               v                |
|  +--------------------------+  |
|  | Kibana                   |  |
|  | Search and Analysis      |  |
|  +--------------------------+  |
+--------------------------------+
```

### Lab Setup

Step 1: Create and Configure

```bash
ip -br addr show vboxnet0
```

Add Adapter 2 as **Host-only Adapter** on all three VMs. Then start the VMs and run.

Step 2: Create medias in Virtual Box

```bash
VBoxManage clonemedium disk \
  "/media/jakir/Resources/ubuntu-server.vdi" \
  "/media/jakir/Resources/iso/vdi/wazuh-server.vdi" \
  --format VDI
```

```bash
VBoxManage clonemedium disk \
  "/media/jakir/Resources/ubuntu-server.vdi" \
  "/media/jakir/Resources/iso/vdi/ubn-endpoint.vdi" \
  --format VDI
```

```bash
VBoxManage clonemedium disk \
  "/media/jakir/Resources/ubuntu-server.vdi" \
  "/media/jakir/Resources/iso/vdi/elk-server.vdi" \
  --format VDI
```

Step 3: Create Install and COnfigure VM

1. Create `wazuh-server` VM using `wazuh-server.vdi`
2. Create `ubn-endpoint` VM using `ubn-endpoint.vdi`
3. Create `kali-attacker` VM using `kali-linux-2026.2-installer-amd64.iso`
4. Create `elk-server` VM using `elk-server.vdi`
5. Create `win-endpoint` VM using `Windows 10 English x64.iso`

For **wazuh-server**, **ubn-endpoint** & **elk-server**, remember you should change **IP Address**

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

### Final Host-only network status

| System        | Interface  | Private IP      |
| ------------- | ---------- | --------------- |
| Ubuntu host   | `vboxnet0` | `192.168.56.1`  |
| wazuh-server  | `enp0s8`   | `192.168.56.10` |
| ubn-endpoint  | `enp0s8`   | `192.168.56.20` |
| kali-attacker | `eth1`     | `192.168.56.30` |
| elk-server    | `eth1`     | `192.168.56.40` |
| win-endpoint  | `eth1`     | `192.168.56.50` |

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
sudo systemctl status wazuh-indexer --no-pager
sudo systemctl status wazuh-manager --no-pager
sudo systemctl status wazuh-dashboard --no-pager
sudo ss -lntp | grep -E ':443|:5601'
curl -k -I https://localhost
sudo ufw status verbose
sudo ufw allow from 192.168.56.0/24 to any port 443 proto tcp
```

```bash
https://192.168.56.10
```

## Ubn-Endpoint Machine

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
wget https://packages.wazuh.com/4.x/apt/pool/main/w/wazuh-agent/wazuh-agent_4.14.8-1_amd64.deb && sudo WAZUH_MANAGER='192.168.56.10' WAZUH_AGENT_NAME='ubn-endpoint' dpkg -i ./wazuh-agent_4.14.8-1_amd64.deb
```

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

### Open-source Endpoint Detection and Response - OpenEDR

Its endpoint security software designed to monitor endpoint activity and provide security telemetry for investigation.
In your lab, OpenEDR runs on the Windows endpoint. Its role includes:

- Monitoring endpoint activity.
- Generating security telemetry.
- Recording events that can help with threat investigation.
- Supporting endpoint detection and response workflows.

### ELK Stack

Its a collection of three open-source data processing and analytics components: `Elasticsearch`, `Logstash`, and `Kibana`. It is used to `collect`, `process`, `store`, `search`, `analyze`, and `visualize data`, including `application logs`, `infrastructure logs`, and `security events`.

| Component         | Function                                                      |
| ----------------- | ------------------------------------------------------------- |
| **Elasticsearch** | Stores, indexes, and searches security events.                |
| **Logstash**      | Receives, processes, and transforms incoming events.          |
| **Kibana**        | Provides dashboards, visualizations, and investigation tools. |

**Architecture for your cybersecurity lab** Using your configured IP addresses

```bash
┌────────────────────────────────────────────┐
│ WINDOWS ENDPOINT                            │
│ IP: 192.168.56.50                           │
│                                            │
│  ┌──────────────────┐                      │
│  │ OpenEDR Agent    │                      │
│  └────────┬─────────┘                      │
│           │                                │
│           ▼                                │
│  ┌──────────────────┐                      │
│  │ Telemetry Files  │                      │
│  └────────┬─────────┘                      │
│           │                                │
│           ▼                                │
│  ┌──────────────────┐                      │
│  │ Filebeat         │                      │
│  └────────┬─────────┘                      │
└───────────┼────────────────────────────────┘
            │
            │ TCP 5044
            ▼
┌────────────────────────────────────────────┐
│ ELK SERVER                                  │
│ IP: 192.168.56.40                           │
│                                            │
│  ┌──────────────────┐                      │
│  │ Logstash         │                      │
│  └────────┬─────────┘                      │
│           │                                │
│           ▼                                │
│  ┌──────────────────┐                      │
│  │ Elasticsearch    │                      │
│  └────────┬─────────┘                      │
│           │                                │
│           ▼                                │
│  ┌──────────────────┐                      │
│  │ Kibana           │                      │
│  │ Dashboards       │                      │
│  │ Event Search     │                      │
│  └──────────────────┘                      │
└────────────────────────────────────────────┘
```

**Investigating suspicious activity** Suppose a process executes on your Windows endpoint.

| Step | Component     | Activity                                                                                   |
| ---- | ------------- | ------------------------------------------------------------------------------------------ |
| 1    | Windows       | A process executes.                                                                        |
| 2    | OpenEDR       | Monitors the activity and generates relevant telemetry, if supported by its configuration. |
| 3    | Filebeat      | Reads the telemetry from the configured output files.                                      |
| 4    | Logstash      | Receives and processes the event.                                                          |
| 5    | Elasticsearch | Indexes the event for searching.                                                           |
| 6    | Kibana        | Allows an analyst to search and investigate the event.                                     |

**OpenEDR + ELK versus Wazuh** Since your lab already includes Wazuh, it is useful to understand the difference.

| Capability                     | OpenEDR + ELK                                  | Wazuh                                             |
| ------------------------------ | ---------------------------------------------- | ------------------------------------------------- |
| Endpoint monitoring            | OpenEDR provides endpoint telemetry            | Wazuh agents collect endpoint security data       |
| Log collection                 | Filebeat can forward OpenEDR telemetry         | Wazuh agents send collected data to the manager   |
| Centralized storage and search | Elasticsearch                                  | Wazuh indexer                                     |
| Security visualization         | Kibana                                         | Wazuh dashboard                                   |
| Primary learning objective     | Endpoint telemetry ingestion and investigation | SIEM, endpoint monitoring, and security detection |

**Implementation plan for your lab**

| Phase | Task                                                  | VM             |
| ----- | ----------------------------------------------------- | -------------- |
| 1     | Verify the virtual disk and Ubuntu filesystem         | `elk-server`   |
| 2     | Install Elasticsearch                                 | `elk-server`   |
| 3     | Install Logstash                                      | `elk-server`   |
| 4     | Install Kibana                                        | `elk-server`   |
| 5     | Install OpenEDR                                       | `win-endpoint` |
| 6     | Install and configure Filebeat                        | `win-endpoint` |
| 7     | Configure the Logstash input and Elasticsearch output | `elk-server`   |
| 8     | Validate telemetry ingestion and investigate events   | Both           |

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
