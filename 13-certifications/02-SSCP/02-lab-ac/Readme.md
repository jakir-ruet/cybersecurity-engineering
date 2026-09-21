**Lab Setup**

- Use **VM environment**:
  - Active Directory + File Server
  - Ubuntu Linux VM: Server tasks
- **Tools needed:** `OpenLDAP`, `Kerberos`, `sudo`, `auditd`, `Wireshark`

**Real-Time Examples**

| Concept          | Example                                                                                |
| ---------------- | -------------------------------------------------------------------------------------- |
| AAA              | AD login (Authentication), group permissions (Authorization), login audit (Accounting) |
| MFA              | Google Authenticator, hardware token, SMS OTP                                          |
| RBAC             | “Admin” can delete files, “User” can only read                                         |
| Least Privilege  | Service account has access only to the database, not the full server                   |
| Federated Access | OAuth2 login for web apps using Google or Microsoft accounts                           |
