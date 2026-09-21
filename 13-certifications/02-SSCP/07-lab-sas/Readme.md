**Lab Setup**

- Ubuntu Linux VM – server tasks
- Windows Server / Client VM – endpoint and application tasks
- Docker/Kubernetes VM – container tasks
- Tools: `ufw`/`iptables`, `ClamAV`, `auditd`, `OpenSSL`, `Docker`, `Kubernetes`, `AWS CLI`

**Real-Time Examples**

| Concept                 | Example                                                                     |
| ----------------------- | --------------------------------------------------------------------------- |
| Endpoint Security       | Anti-virus + host firewall on Windows/Linux                                 |
| System Hardening        | Disable SSH root login, remove unused packages, enforce password complexity |
| Backup                  | Daily incremental backup of /home directory to NAS or cloud storage         |
| Secure Coding           | Validate inputs, prevent SQL injection or XSS attacks                       |
| Virtualization Security | Limit VM privileges, apply snapshots, isolate networks                      |
| Cloud Security          | AWS S3 bucket with encryption and least privilege IAM policies              |
| Data Lifecycle          | Classify sensitive files → Encrypt → Retire securely                        |
