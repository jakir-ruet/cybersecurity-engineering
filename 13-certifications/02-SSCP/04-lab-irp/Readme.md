**Lab Setup**

- Ubuntu Linux VM – target server
- Windows Server VM – AD + File Server
- `Tools:` `auditd`, `Syslog`, `Wireshark`, `FTK Imager` or `Autopsy` (for evidence collection), `ClamAV`, `Fail2ban`

**Real-Time Examples**

| Concept          | Example                                                                              |
| ---------------- | ------------------------------------------------------------------------------------ |
| Incident         | Ransomware detected on web server                                                    |
| IR Plan          | Activate IRP → isolate server → notify SOC → eradicate malware → restore from backup |
| Digital Evidence | Capture logs, disk images, or memory snapshots for forensic analysis                 |
| Containment      | Disconnect infected machine from network                                             |
| Recovery         | Restore server from verified backup                                                  |
| Lessons Learned  | Update firewall rules, patch vulnerability, train staff                              |
