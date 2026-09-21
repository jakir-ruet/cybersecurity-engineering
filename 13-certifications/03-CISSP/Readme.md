## Overview

`Certified Information Systems Security Professional` (`CISSP`) is one of the most respected cybersecurity certifications in the world. It is offered by ISC2 and is designed for experienced security professionals who want to prove expertise in information security management and architecture. The `CISSP` course is based on 8 domains from the `CISSP` `Common Body of Knowledge` (`CBK`).

### Course Outline

| Domain | Domain                              | Weight | Key Topics                                      | Real-World Focus                     | Your Mapping               |
| :----: | ----------------------------------- | :----: | ----------------------------------------------- | ------------------------------------ | -------------------------- |
|   1    | Security & Risk Management          |  16%   | CIA Triad, Risk, Compliance, BCP/DR             | Policies, governance, risk decisions | Terraform, Cloud design    |
|   2    | Asset Security                      |  10%   | Data classification, ownership, lifecycle       | Data protection, handling            | Storage, encryption        |
|   3    | Security Architecture & Engineering |  13%   | Security models, crypto, secure design          | System architecture, secure design   | Kubernetes, Infra design   |
|   4    | Communication & Network Security    |  13%   | OSI, TCP/IP, TLS, VPN, Firewalls                | Secure communication                 | Networking, pfSense        |
|   5    | Identity & Access Management (IAM)  |  13%   | RBAC, ABAC, MFA, SSO                            | Access control systems               | AWS IAM, K8s RBAC          |
|   6    | Security Assessment & Testing       |  12%   | Vulnerability scan, pentest (high-level), audit | Security validation                  | Monitoring, scanning tools |
|   7    | Security Operations                 |  13%   | Incident response, SIEM, DRP                    | Day-to-day security ops              | Linux, logs, automation    |
|   8    | Software Development Security       |  10%   | Secure SDLC, OWASP, DevSecOps                   | Secure coding & pipeline             | CI/CD, Jenkins             |

### Agenda: Information security governance

- Introduction to information security concepts
- Overview of governance
- Roles and responsibilities
- Control frameworks
- Liabilities
- Laws and regulations
- Intellectual property
- Privacy

### Domain 1 Security & Risk Management

#### Information Security Concept

The CIA Triad is a foundational concept in Information Security that defines the three core principles used to protect data and systems: `Confidentiality`, `Integrity`, and `Availability`.

**Confidentiality** Confidentiality ensures that information is only accessible to authorized users.

- Prevents unauthorized access or disclosure
- Common methods:
  - Encryption (e.g., passwords, secure protocols)
  - Access control (user permissions, authentication)
- Example: Only you can read your email or bank account details.

**Integrity** Integrity ensures that data remains accurate, consistent, and unaltered unless changed by authorized users.

- Protects against unauthorized modification or tampering
- Common methods:
  - Hashing (e.g., checksums)
  - Digital signatures
  - Version control
- Example: A downloaded file hasn’t been modified or corrupted.

**Availability** Availability ensures that information and systems are accessible when needed.

- Prevents disruptions (like system crashes or cyberattacks)
- Common methods:
  - Regular backups
  - Redundancy (multiple servers)
  - Protection against Denial-of-Service (DoS) attack
- Example: A website is always up and running when users try to access it.

#### 5 Pillars of Information Security

The `5 Pillars of Information Security` are an extension of the `classic Information Security CIA Triad`, adding two more principles to strengthen overall security. These `five` pillars are:

**1. Confidentiality** Ensures that only authorized people can access information.

- Methods: encryption, passwords, access control
- Example: Private messages are not visible to others

**2. Integrity** Ensures that data remains accurate and unaltered.

- Methods: hashing, digital signatures
- Example: Financial records are not tampered with

**3. Availability** Ensures that systems and data are accessible when needed.

- Methods: backups, redundancy, protection from Denial-of-Service (DoS) attack
- Example: A website stays online 24/7

**4. Authenticity** Ensures that users and data are genuine and verified.

- Confirms identity (who you are)
- Methods: login systems, biometrics, digital certificates
- Example: Verifying a user before allowing access

**5. Non-Repudiation** Ensures that a user cannot deny their actions after performing them.

- Provides proof of origin and actions
- Methods: digital signatures, audit logs
- Example: A sender cannot deny sending an email or transaction

**Easy Way to Remember**

| **Confidentiality** | **Integrity** | **Availability** | **Authenticity** | **Non-repudiation** |
| ------------------- | ------------- | ---------------- | ---------------- | ------------------- |
| Secret              | Correct       | Accessible       | Real             | Cannot deny         |

#### Governance

Governance refers to the system of `rules`, `practices`, and `processes` by which an `organization` or `society` is directed and controlled. In the context of `Information Security`, governance ensures that security strategies align with `business goals` and `risks` are properly managed.

##### Goals of corporate governance

- **Provide oversight and support to enterprise activities** - Ensures management activities are supervised and aligned with objectives
- **Oversee risk management** - Identifies and reduces risks that could harm the organization
- **Comply with laws, regulations, contracts, etcetera** - Follows laws, regulations, and contractual obligations
- **Determine organizational strategy** - Sets long-term goals and direction
- **Deliver value to stakeholders** - Ensures shareholders, customers, and employees benefit
- **Facilitate effective monitoring and audit** - Enables transparency through audits and performance checks
- **Ensure business continuity** - Keeps operations running during disruptions (e.g., disasters, cyber-attacks)

##### Information security governance `ISG`

Information Security Governance (ISG) is a part of Information Security that focuses on protecting and managing data throughout its lifecycle. ISG is the framework and practices used to manage data securely, including: `Creation`, `Storage`, `Usage`, `Archiving`, `Deletion`.

> Key Idea (ISG is proactive)

- Anticipates risks
- Strengthens policies
- Builds a security-focused culture
- Helps legal, compliance, and IT teams work together

##### Goals of information security governance

The main goals of ISG are:

**1. Manage Risk Effectively**

- Identify and reduce cybersecurity threats
- Protect systems from attacks and failures

**2. Ensure Compliance**

- Follow laws, standards, and regulations
- Avoid legal penalties and data breaches

**3. Support Business Strategy**

- Align security with organizational goals
- Enable safe innovation and technology use

**4. Protect CIA Triad - Ensure:**

- Confidentiality → Data is kept secret
- Integrity → Data remains accurate
- Availability → Data is accessible when needed

#### Planning Horizon (Levels of Goals) - Organizations operate on three levels of planning

**1. Strategic Goals (Top Level)**

- Managed by upper management (CEO, board)
- Long-term and broad
- Provide overall direction for the organization
- Supported by tactical and operational goals
- Example: `Improve overall cybersecurity posture`

**2. Tactical Goals (Middle Level)**

- Managed by middle managers (e.g., security managers, CISSP professionals)
- Mid-term focus
- Translate strategic goals into actionable plans
- Example: `Implement a new firewall system within 6 months`

**3. Operational Goals (Lower Level)**

- Managed by administrators/technical staff
- Short-term, day-to-day tasks
- Focus on execution and productivity
- Example: `Monitor firewall logs daily`

> **Simple Flow**

- `Strategic` → `Tactical` → `Operational`
- `Big vision` → `Planning` → `Daily work`

#### Accountable vs Responsible

**Accountable**

- Final decision-maker
- Owns outcomes and results
- `The buck stops here`
- May involve legal liability
- Senior leadership is accountable for organizational security
- Data owners are accountable for the security of their data

**Responsible**

- Carries out the work
- Follows policies and procedures set by leadership
- Everyone in the organization is responsible
- Implements security controls and daily operations
- Data custodians handle day-to-day maintenance and configuration

#### Board of Directors & CEO

- Provide overall governance and strategic direction
- Ensure alignment with organizational goals
- Establish policies and risk management practices

#### Steering Committees

- Work under the board
- Provide guidance for projects and initiatives
- Ensure alignment with strategy

#### Chief Operating Officer (COO)

- Manages day-to-day operations
- Handles staffing, administration, execution
- Usually second-in-command

#### Chief Risk Officer (CRO)

- Oversees enterprise risk management
- Focuses mainly on non-IT risks

#### Chief Information Officer (CIO)

- Responsible for IT strategy, budgeting, and performance
- Aligns IT with business goals

#### Information Security Manager

- Leads risk identification and mitigation
- Develops security strategies and frameworks
- Works with leadership to assess risks regularly

#### Data Owner

- **Accountable** for data
- Responsibilities:
  - Decide access rights
  - Define data usage
  - Assign classification
- Usually **business/unit leaders**

#### Data Custodian

- **Responsible** for data
- Responsibilities:
  - Maintain systems
  - Apply security controls
  - Handle daily operations
- Also called **security practitioners**

#### Summary Table

| **Role**          | **Type**    | **Responsibility**            |
| ----------------- | ----------- | ----------------------------- |
| Senior Leadership | Accountable | Overall security & governance |
| Data Owner        | Accountable | Data protection decisions     |
| Employees/Admins  | Responsible | Implement security controls   |
| Data Custodian    | Responsible | Maintain and secure data      |

> Easy Way to Remember

- Accountable = Owns it (decision-maker)
- Responsible = Does it (worker)

#### Control Framework

A Control Framework is a `structured set of guidelines`, `best practices`, and `standards that organizations` use to `manage risk`, `ensure compliance`, and `implement security controls effectively`. It provides a roadmap for aligning security practices with business objectives.

##### Purpose of a Control Framework

- Establish policies and procedures for security and risk management
- Provide consistency across the organization
- Enable audits, monitoring, and compliance
- Support regulatory requirements

#### Common Control Frameworks

| Framework         | Focus / Purpose                                                             |
| ----------------- | --------------------------------------------------------------------------- |
| **COSO**          | Enterprise risk management, internal controls, financial reporting          |
| **COBIT**         | IT governance and management                                                |
| **NIST CSF**      | Cybersecurity risk management (Identify, Protect, Detect, Respond, Recover) |
| **ISO/IEC 27001** | Information security management systems (ISMS)                              |
| **ITIL**          | IT service management, process optimization                                 |

#### Scoping and Tailoring

`Scoping` and `Tailoring` are processes used to adapt a `security control framework` to the specific needs, risks, and environment of an organization. Not all controls are always relevant, so these processes ensure efficiency and relevance.

##### Scoping

Determining which parts of the organization, systems, or data are covered by the security framework.

> Key Points:

- Identify applicable systems, processes, and assets
- Focus on relevant threats and regulatory requirements
- Helps avoid unnecessary implementation of controls

> Example:
A company may scope out HR systems separately from production systems, as each has different risks and requirements.

##### Tailoring

Adjusting or customizing controls to fit the organization’s size, risk profile, and regulatory environment.

> Key Points:

- Modify control objectives or implementation details
- Can add, remove, or modify controls
- Ensures controls are practical and effective

> Example:
ISO 27001 requires access controls, but a small company may tailor the control by using simpler authentication methods instead of complex enterprise systems.

##### Benefits of Scoping and Tailoring

- Reduces costs and complexity
- Improves effectiveness of controls
- Aligns security with business goals and risk appetite
- Avoids implementing irrelevant or excessive controls

#### Simple Way to Remember

- Scoping = `What do we cover?`
- Tailoring = `How do we implement it?`

#### Control Framework

A control framework is a structured approach to managing information security risks, ensuring compliance, and aligning security practices with business objectives, like `COBIT`, `ISO 27001`, `NIST CSF`, and `COSO`.

##### Select or Adopt Framework

Choose a framework based on industry standards, regulations, and organizational needs, like

- `ISO/IEC 27001` – Information Security Management Systems (ISMS)
- `NIST CSF` – Cybersecurity risk management
- `COBIT` – IT governance and control
- `COSO` – Enterprise risk and internal controls

##### Implement Controls

Assign responsibility and accountability:

- `Accountable` → Senior leadership, data owners
- `Responsible` → IT staff, security practitioners
- Deploy controls according to policies and procedures
- Include technical, administrative, and physical controls

> Example: Implement multi-factor authentication for remote access.

##### Categories of Control Frameworks

| **Category**          | **Focus Area**                   | **Purpose**                            | **Examples**             |
| --------------------- | -------------------------------- | -------------------------------------- | ------------------------ |
| Governance Frameworks | Strategy & oversight             | Align IT/security with business goals  | COBIT, COSO              |
| Management Frameworks | Processes & operations           | Implement and manage security controls | ISO/IEC 27001, ITIL      |
| Technical/Security    | Technical controls               | Protect systems, networks, and data    | NIST CSF, NIST SP 800-53 |
| Compliance Frameworks | Laws & regulations               | Ensure legal and regulatory compliance | GDPR, PCI DSS            |
| Risk Management       | Risk identification & mitigation | Manage and reduce organizational risks | NIST RMF, ISO 31000      |

##### Comparison: ISO 27001 vs NIST vs COBIT

| **Feature**      | **ISO/IEC 27001**               | **NIST (CSF/RMF)**                | **COBIT**                        |
| ---------------- | ------------------------------- | --------------------------------- | -------------------------------- |
| Type             | Management Framework            | Technical & Risk Framework        | Governance Framework             |
| Focus            | Information Security Management | Cybersecurity & Risk Management   | IT Governance & Management       |
| Purpose          | Build ISMS (security program)   | Manage and reduce cyber risks     | Align IT with business goals     |
| Approach         | Risk-based, certification       | Flexible, guideline-based         | Process and control-based        |
| Certification    | Yes (ISO certification)         | No formal certification           | No certification (framework use) |
| Scope            | Organization-wide security      | Systems, networks, operations     | Enterprise IT governance         |
| Audience         | Security managers, auditors     | Security professionals, engineers | Executives, management           |
| Key Strength     | Globally recognized standard    | Detailed technical guidance       | Strong governance structure      |
| Example Use Case | Build formal security program   | Improve cybersecurity posture     | Manage IT strategy & controls    |

#### CMMI (Capability Maturity Model Integration)

It's a framework used to improve organizational `processes`, `performance`, and `maturity`. It helps organizations develop efficient, consistent, and high-quality processes in areas like software development, services, and security.

##### CMMI Maturity Levels

CMMI defines 5 maturity levels that show how well an organization’s processes are developed.

| **Level** | **Name**               | **Description**                                    |
| --------- | ---------------------- | -------------------------------------------------- |
| 1         | Initial                | Processes are unpredictable and unstructured       |
| 2         | Managed                | Basic project management processes are in place    |
| 3         | Defined                | Processes are standardized across the organization |
| 4         | Quantitatively Managed | Processes are measured and controlled using data   |
| 5         | Optimizing             | Continuous improvement and innovation              |

##### 7 steps of the NIST Risk Management Framework (RMF)

- `Prepare` → Establish context, roles, and risk strategy
- `Categorize` → Define system impact (CIA: low, moderate, high)
- `Select` → Choose appropriate security controls
- `Implement` → Apply and configure controls
- `Assess` → Test and evaluate control effectiveness
- `Authorize` → Approve system operation (ATO)
- `Monitor` → Continuously track and improve security

#### Liability

Liability refers to the legal responsibility for one’s actions or failure to act, especially when it results in harm, damage, or loss.

##### Types of Liability

- `Legal responsibility` → Obligation for actions or failure that causes harm
- `Accountability under law` → Can result in fines, penalties, or lawsuits
- `Civil liability` → Involves lawsuits and financial compensation
- `Criminal liability` → Involves law violations leading to fines or imprisonment
- `Organizational liability` → Companies are responsible for protecting data and systems
- `Leadership liability` → Senior management may be legally liable for failures
- `Due care` → Taking reasonable steps to prevent harm
- `Due diligence` → Continuously maintaining and improving security measures
- `Security breach impact` → Failure to secure systems can lead to legal consequences

#### Laws and Regulations

Laws and regulations are rules that govern how organizations and individuals must handle information and conduct business, especially regarding data protection and security.

- `Laws` → Legally binding rules created by governments. Violation can result in legal penalties or prosecution.
- `Regulations` → Detailed rules issued by authorities to enforce laws. They provide specific requirements to ensure compliance.

##### Types of Laws and Regulations

- `Laws` → Legally binding rules created by governments that must be followed
- `Regulations` → Detailed rules issued by authorities to enforce laws
- `Compliance` → Requirement for organizations to follow laws and regulations
- `Data protection laws` → Protect personal and sensitive information (e.g., GDPR)
- `Industry regulations` → Specific rules for certain sectors (e.g., PCI DSS for payment systems)
- `Privacy laws` → Ensure individuals’ personal data is collected and used properly
- `Enforcement` → Government agencies monitor and enforce compliance
- `Penalties` → Non-compliance can result in fines, legal action, or business restrictions
- `Global vs local laws` → Organizations must follow laws in all regions where they operate
- `Information security role` → Ensures systems and data handling meet legal requirements

> Examples

- `General Data Protection Regulation (GDPR)` – EU law protecting personal data
- `Health Insurance Portability and Accountability Act (HIPAA)` – US law protecting health information
- `Payment Card Industry Data Security Standard (PCI DSS)` – Industry regulation for payment card security
- `Sarbanes-Oxley Act (SOX)` – Ensures financial and IT controls in corporations

> Simple Way to Remember

- `Law` = What must be done (legal requirement)
- `Regulation` = How it is enforced (detailed rules)

#### GDPR Principles

The General Data Protection Regulation (GDPR) is an EU law that governs how organizations collect, store, and process personal data. It is based on 7 core principles.

- **Lawfulness, Fairness, Transparency** → Process personal data legally, fairly, and openly
- **Purpose Limitation** → Collect data only for specific, legitimate purposes
- **Data Minimization** → Only collect data necessary for the intended use
- **Accuracy** → Keep data correct and up-to-date
- **Storage Limitation** → Retain data only as long as needed, then securely delete
- **Integrity and Confidentiality (Security)** → Protect data from unauthorized access, loss, or breaches
- **Accountability** → Demonstrate compliance through policies, audits, and records

> Quick Memory Trick:
`L-P-M-A-S-A` → Law, Purpose, Minimization, Accuracy, Storage, Security, Accountability

##### GDPR – 6 Key Features

- **Data Protection by Design and by Default** → Incorporate privacy measures from the start of systems and processes
- **Consent** → Organizations must obtain explicit and informed consent to process personal data
- **Right to Access** → Individuals can access the personal data an organization holds about them
- **Right to Erasure (Right to be Forgotten)** → Individuals can request deletion of their personal data
- **Data Portability** → Individuals can transfer their data between organizations in a structured format
- **Breach Notification** → Organizations must report data breaches to authorities and affected individuals promptly

#### Intellectual Property (IP)

Intellectual Property (IP) refers to creations of the mind that are legally protected, giving the creator certain rights to use and control them.

- **Copyright** → Protects original works like books, software, music, and art
- **Trademark** → Protects brand identifiers such as logos, names, and slogans
- **Patent** → Protects new inventions or processes with exclusive rights
- **Trade Secret** → Protects confidential business information like formulas or strategies
- **Importance** → Secures software, algorithms, and digital assets from theft or misuse
- **Legal Consequences** → Violations can lead to fines, lawsuits, or business loss

> Quick Memory Trick
`CPPT` → Copyright, Patent, Patent, Trade Secret

#### Privacy

Privacy is the right of individuals to control their personal information and decide how it is collected, used, shared, and stored.

- **Right to Control** → Individuals control how their personal data is collected, used, and shared
- **Collection Limitation** → Only collect data that is necessary for the purpose
- **Purpose Specification** → Clearly define why data is being collected
- **Use Limitation** → Data must only be used for its stated purpose
- **Data Quality** → Ensure collected data is accurate and up-to-date
- **Security Safeguards** → Protect data from unauthorized access or breaches
- **Openness & Transparency** → Inform individuals about data practices
- **Individual Participation** → Allow individuals to access and correct their personal data

### Domain 2 Asset Security

#### Asset

Assets refer to everything a company owns, from cash to equipment to intellectual property.

#### Asset Security

Asset Security ensures that valuable assets (data, systems, devices) are properly classified, handled, stored, and protected based on their importance.

#### Asset Classification

| Asset                | Type               | Classification  | Why Important                 |
| -------------------- | ------------------ | --------------- | ----------------------------- |
| Customer Database    | Intangible         | Confidential    | Contains PII (very sensitive) |
| Web Server           | Tangible           | Internal        | Runs application              |
| Inventory (Products) | Current + Tangible | Internal        | Business operations           |
| Company Building     | Fixed + Tangible   | Public/Internal | Physical infrastructure       |
| Brand Name           | Intangible         | Confidential    | Business value                |
| Shares/Stock/Bond    | Financial          | Internal        | Financial health              |

#### Data Classification

| Level            | Meaning           | Example                 |
| ---------------- | ----------------- | ----------------------- |
| **Public**       | Anyone can access | Website content         |
| **Internal**     | Only employees    | Internal emails         |
| **Confidential** | Sensitive         | Customer data           |
| **Restricted**   | Highly sensitive  | Passwords, private keys |

#### IT Asset Management

- `Hardware Asset Management:` Servers, laptops, network devices
- `Software Asset Management:` OS, applications, licenses
- `Data & digital resources:` Databases, cloud resources, virtual machines

#### Why IT asset management important

- **Visibility & Control** – Knowing what assets exist allows you to manage and secure them effectively.
- **Security & Risk Management** – Identifies sensitive or high-risk assets so appropriate protections can be applied.
- **Compliance & Legal Requirements** – Ensures adherence to software licenses, regulatory standards, and audits.
- **Cost Optimization** – Helps reduce unnecessary spending by tracking unused or underutilized assets.
- **Operational Efficiency** – Simplifies maintenance, updates, and assignment of assets to the right users.
- **Data Protection & Privacy** – Supports secure storage, handling, and disposal of sensitive information.
- **Supports Strategic Decisions** – Provides insight for future IT investments, capacity planning, and scaling.

#### Asset Ownership

| Role        | Responsibility                                                    |
| ----------- | ----------------------------------------------------------------- |
| Asset Owner | Decides classification, approves access, accountable for security |
| Custodian   | Implements controls, maintains asset operationally                |
| User        | Uses asset according to policies                                  |

#### Asset valuation

It's determining the monetary or business value of an asset, which helps prioritize security measures and risk management.

### Domain 3 Security Architecture & Engineering

### Domain 4 Communication & Network Security

### Domain 5 Identity & Access Management (IAM)

### Domain 6 Security Assessment & Testing

### Domain 7 Security Operations

### Domain 8 Software Development Security
