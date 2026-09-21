### Welcome to Certified in Cybersecurity `CC` - Begineer Level

The Certified in Cybersecurity (CC) is an entry-level cybersecurity certification offered by ISC2. Those are the official 5 domains of the Certified in Cybersecurity (CC) from ISC2.

| Domain       | Name                                                          | Weight |
| ------------ | ------------------------------------------------------------- | ------ |
| **Domain 1** | Security Principles                                           | ~26%   |
| **Domain 2** | Business Continuity, Disaster Recovery, and Incident Response | ~10%   |
| **Domain 3** | Access Control Concepts                                       | ~22%   |
| **Domain 4** | Network Security                                              | ~24%   |
| **Domain 5** | Security Operations                                           | ~18%   |

## Domain 1 `Security Principles`

Security principles are the foundational guidelines used to `design`, `implement`, and `manage` secure systems. This chapter is foundational; all other domains build on it.

**Topics**

- Information Security, IT Security, Cybersecurity
- CIA Triad & IAAA
- Privacy
- Risk & Incident Management
- Access Control
- Governance, Laws, Regulations
- ISC² Ethics

### Information Security, IT Security, Cybersecurity

- **Information Security:** All information (paper, voice, data, human knowledge).
- **IT Security:** Hard/software + data (servers, networks, computers, firmware).
- **Cybersecurity:** IT Security accessible via the internet.

**Summary Table**

| **Term**                 | **Scope**             | **Focus**                                      | **Examples**                                            |
| ------------------------ | --------------------- | ---------------------------------------------- | ------------------------------------------------------- |
| **Information Security** | Broadest              | Protecting all forms of information            | Locking file cabinets, encrypting data, access policies |
| **IT Security**          | Subset of InfoSec     | Securing IT systems and digital infrastructure | Antivirus, firewalls, system hardening, secure login    |
| **Cybersecurity**        | Subset of IT Security | Protecting systems from internet-based threats | Phishing protection, DDoS defense, threat hunting, WAF  |

![Set Subset Diagram of Security](/img/security-sets.png)

### CIA (Confidentiality, Integrity & Availability) Model with Diagram

In cybersecurity and information security, the CIA Triad is a foundational model that outlines the three core principles for protecting information.

#### Confidentiality - Keep data secret

- **Tools:** AES256, SSL/TLS, access control, MFA
- **Threats:** Social engineering, keyloggers, IoT backdoors

#### Integrity - Data is not altered, keep accuiracy

- **Tools:** Checksums, message digests (MD5, SHA1/2), digital signatures
- **Threats:** Code injection, encryption attacks

#### Availability - Data accessible when needed

- **Tools:** IPS/IDS, patch management, redundancy, HA
- **Threats:** DDoS, hardware failure, application failure

| **Component**       | **Meaning**                                  | **Goal**                                                         | **Example**                                                  |
| ------------------- | -------------------------------------------- | ---------------------------------------------------------------- | ------------------------------------------------------------ |
| **Confidentiality** | Ensure only authorized users can access data | Prevent unauthorized access, leaks, or spying                    | Using encryption, passwords, and access control lists (ACLs) |
| **Integrity**       | Ensure data is accurate and unchanged        | Prevent unauthorized modification or tampering                   | Checksums, hashes (e.g., SHA-256), digital signatures        |
| **Availability**    | Ensure systems and data are accessible       | Prevent outages and ensure legitimate users can access resources | Redundant servers, load balancing, backups, DDoS protection  |

![CIA (Confidentiality, Integrity & Availability) Model with Diagram](/01-CC/img/domain-1/cia-triad.png)

### Opposite of CIA Triad is DAD (Disclosure, Alteration & Destruction)

- **Disclosure:** Unauthorized access
- **Alteration:** Data changed
- **Destruction:** Data or systems destroyed

It's also need to know for security.

| **Component**   | **Meaning**                                             | **Purpose**                  |
| --------------- | ------------------------------------------------------- | ---------------------------- |
| **Disclosure**  | Unauthorized access to information                      | Violates **confidentiality** |
| **Alteration**  | Unauthorized modification of information                | Violates **integrity**       |
| **Destruction** | Unauthorized removal or denial of access to information | Violates **availability**    |

### IAAA – Identity & Access (Identification, Authentication, Authorization, and Accountability)

- **Identification:** Who you are (username, ID, SSN)
- **Authentication:** Prove it (MFA recommended)
  - **Type 1 (Knowledge):** Passwords, PINs, passphrases
  - **Type 2 (Possession):** ID cards, tokens, single-use passwords
  - **Type 3 (Biometrics):** Fingerprint, iris, face
- **Authorization:** What you can access (DAC, MAC, RBAC, ABAC, Context/Content-based)
- **Accountability:** Track actions → non-repudiation, Traces an Action to a Subject's Identity.

> **Biometric Notes:**

- **Errors:** FRR (False Reject), FAR (False Accept), CER (Crossover Error Rate)
- **Types:** Physiological (fingerprint, iris), Behavioral (typing rhythm, gait)
- **Privacy is critical:** biometrics cannot be “replaced” like passwords

> **Notes**

- **DAC** → Discretionary Access Control
- **MAC** → Mandatory Access Control,
- **RBAC** → Role-Based Access Control,
- **ABAC** → Attribute-Based Access Control

| **Component**      | **Meaning**                                                         | **Purpose**                                   | **Example**                                                 |
| ------------------ | ------------------------------------------------------------------- | --------------------------------------------- | ----------------------------------------------------------- |
| **Identification** | Claiming an identity                                                | Establish *who* the user is                   | Username, user ID, email address                            |
| **Authentication** | Verifying the claimed identity                                      | Ensure the user is who they say they are      | Password, biometric scan, OTP, security token               |
| **Authorization**  | Granting permissions based on authenticated identity                | Control what the user is allowed to do        | Read/write access, admin rights, resource roles             |
| **Accountability** | Tracing actions to a specific identity and holding them responsible | Ensure user actions can be logged and audited | Logs, user activity tracking, audit trails, non-repudiation |

#### Classification with example

1. Identification, example - Your name, username, ID number, employee number, SSN etc.
2. Authentication
   - Type 1 Authentication (passwords, pass phrase, PIN, etc.).
   - Type 2 Authentication (ID, passport, smart card, token, cookie on PC, etc.).
   - Type 3 Authentication (Biometrics, Fingerprint, iris scan, facial geometry, etc.).
3. Authorization, example - it's cover ACL, DAC, MAC, RBAC, ABAC, and RUBAC.
4. Accountability, example - Traces an Action to a Subject's Identity.

### Privacy

In cybersecurity, Human right; protection from unauthorized observation or intrusion. Privacy refers to the rights and control individuals have over their personal information, including how it is collected, used, stored, and shared.

**`General Data Protection Regulation` (GDPR):** It is a comprehensive legal framework enacted by the European Union (EU) that governs how organizations collect, process, and protect the personal data of individuals within the EU and the European Economic Area (EEA).

**Individual Rights Under GDPR**

The regulation grants several key rights to individuals, including:

- **Right to Access:** The right to see what data an organization has about them.
- **Right to Erasure:** Also known as the "right to be forgotten," allowing individuals to ask for their data to be deleted.
- **Right to Portability:** The right to move their data from one service provider to another.
- **Right to Rectification:** The right to have inaccurate personal data corrected.

#### Privacy vs Confidentiality

| **Aspect**         | **Privacy**                                        | **Confidentiality**                                |
| ------------------ | -------------------------------------------------- | -------------------------------------------------- |
| **Focus**          | Protecting personal or sensitive information       | Preventing unauthorized access to data             |
| **Concerned With** | Data ownership, user rights, and consent           | Data security and access control                   |
| **Legal Basis**    | Often governed by privacy laws (e.g., GDPR, HIPAA) | Typically enforced by security policies            |
| **Example**        | GDPR compliance, cookie consent                    | Encryption, firewalls, access control lists (ACLs) |

### Risk Management?

Risk management is the process of identifying, assessing, and controlling threats to an organization's digital assets, systems, and data. The goal is to reduce the likelihood and impact of cybersecurity incidents. Risk calculation by following formula;

- `Risk` = `Threat` x `Vulnerability (Likelihood)` Or
- `Risk` = `Threat` x `Vulnerability (Likelihood)` x `Impact`
- `Total Risk` = `Threat` x `Vulnerability (Likelihood)` x `Asset Value`
- `Residual Risk` = `Total Risk` - `Countermeasures`

**Key Components**

1. `Asset` 👉 Example: database, server, credentials
2. `Threat` 👉 Example: hacker, malware, insider
3. `Vulnerability` 👉 Example: open port, weak password
4. `Impact` 👉 Example: data loss, downtime

#### Risk Lifecycle: Identify → Assess → Respond → Monitor

- **Qualitative:** Likelihood & impact (High/Medium/Low/Extreme)
- **Quantitative:** Assign numeric cost ($), calculate ALE, SLE, TCO
- **Risk Response:** Accept, Mitigate, Transfer, Avoid (Never reject)

**Indicators: In Summary Table**

| Acronym | Full Name                 | Purpose                  | Example                                 |
| ------- | ------------------------- | ------------------------ | --------------------------------------- |
| KPI     | Key Performance Indicator | Tracks ongoing progress  | Number of sales calls per week          |
| KGI     | Key Goal Indicator        | Confirms final outcome   | Total annual revenue target             |
| KRI     | Key Risk Indicator        | Warns of potential risks | Number of cybersecurity breach attempts |

#### Steps of Risk Management

| **Step**                | **Description**                                                           |
| ----------------------- | ------------------------------------------------------------------------- |
| **1. Identify Risks**   | Discover vulnerabilities, threats, assets, and potential attack vectors   |
| **2. Assess Risks**     | Evaluate likelihood and impact `Risk = Likelihood × Impact`               |
| **3. Prioritize Risks** | Rank risks based on criticality and business impact                       |
| **4. Threat Risks**     | Choose mitigation strategy: avoid, transfer, mitigate, or accept the risk |
| **5. Monitor & Review** | Continuously track risk posture and update strategies as threats evolve   |

#### Risk Assessment

Risk Assessment is the process of evaluating risks to determine their likelihood, impact, and priority so organizations can decide how to manage them. `Two` ways measeure risk like

![Risk Assessment Process](/01-CC/img/domain-1/risk-assessments.png)

1. **Qualitative Risk Analysis** It's a subjective method used to `prioritize risks` by `evaluating` their `likelihood` and `impact` using descriptive scales (e.g., `Low`, `Medium`, `High`) rather than numerical data.

**Key Characteristics**

- No complex calculations (unlike ARO, ALE)
- Uses ratings (High/Medium/Low)
- Fast and easy to perform
- Based on expert opinion and experience
- Often visualized using a risk matrix

**Example**

| Risk         | Likelihood | Impact | Risk Level |
| ------------ | ---------- | ------ | ---------- |
| DDoS Attack  | High       | High   | Critical   |
| Data Leak    | Medium     | High   | High       |
| Laptop Theft | Low        | Medium | Medium     |

**Risk Matrix Concept**

| Likelihoods | Low Impact | Medium Impact | High Impact |
| ----------- | ---------- | ------------- | ----------- |
| High        | Medium     | High          | Critical    |
| Medium      | Low        | Medium        | High        |
| Low         | Low        | Low           | Medium      |

**When to Use**

- Early stage risk assessment
- When data is limited
- Quick decision-making needed
- Business-level discussions

1. **Quantitative Risk Analysis** It's a `systematic`, `data-driven` process that evaluates risks by `assigning numerical values`vsuch as monetary `cost`, `time impact`, or `probability` to determine their potential effect on project objectives.

It provides an objective and detailed assessment of risk exposure, particularly in complex environments, by applying analytical techniques such as `Monte Carlo simulation` and `Expected Monetary Value` (EMV).

**Key Quantitative Risk Terms**

| Term                                | Meaning / Formula                                         | Notes                        |
| ----------------------------------- | --------------------------------------------------------- | ---------------------------- |
| **Asset Value (AV)**                | The monetary value of the asset being protected           | E.g., a server worth $50,000 |
| **Exposure Factor (EF)**            | % of asset lost if risk occurs                            | E.g., 25% damage → EF = 0.25 |
| **Single Loss Expectancy (SLE)**    | Monetary loss from a single incident                      | **SLE = AV × EF**            |
| **Annual Rate of Occurrence (ARO)** | Estimated frequency per year a risk may occur             | E.g., 2 times/year → ARO = 2 |
| **Annual Loss Expectancy (ALE)**    | Expected annual monetary loss                             | **ALE = SLE × ARO**          |
| **Risk Score**                      | Could be qualitative (High/Med/Low) or quantitative (ALE) | Helps prioritize risk        |

**Risk Table**

| Asset           | Threat      | AV ($)  | EF (%) | SLE ($) | ARO (per year) | ALE ($) | Notes                         |
| --------------- | ----------- | ------- | ------ | ------- | -------------- | ------- | ----------------------------- |
| Web Server      | DDoS Attack | 50,000  | 20%    | 10,000  | 2              | 20,000  | Could mitigate with WAF       |
| Database        | Ransomware  | 100,000 | 50%    | 50,000  | 0.5            | 25,000  | Backup reduces EF             |
| Employee Laptop | Theft       | 2,000   | 100%   | 2,000   | 1              | 2,000   | Use encryption & policies     |
| Network Switch  | Fire        | 20,000  | 30%    | 6,000   | 0.1            | 600     | Fire suppression reduces risk |

##### Qualitative Risk Analysis with the Risk Analysis Matrix

![Qualitative Risk Analysis with the Risk Analysis Matrix](/01-CC/img/domain-1/risk-analysis-matrix.png)

Where, L = Low, M = Medium, H = High, E = Extreme Risk

##### Qualitative vs Quantitative

| Feature   | Qualitative     | Quantitative  |
| --------- | --------------- | ------------- |
| Data Type | Descriptive     | Numerical     |
| Speed     | Fast            | Slower        |
| Accuracy  | Lower           | Higher        |
| Example   | High/Medium/Low | ARO, SLE, ALE |

**Key Characteristics**

- Data-driven and numerical (cost, time, probability)
- Objective and fact-based
- Uses mathematical/statistical methods (Monte Carlo, EMV)
- Produces measurable outputs (ARO, SLE, ALE)
- Focuses on financial impact
- Detailed and in-depth analysis
- Supports decision-making and budgeting
- Requires time, tools, and reliable data

**When to Use**

- For high-value or critical systems
- When financial impact needs to be measured
- In complex projects with many variables
- When reliable historical data is available
- For strategic and business decisions
- After qualitative risk analysis to refine priorities

#### Risk Threatment Strategies

| **Strategy** | **Meaning**                                 | **Example**                                   |
| ------------ | ------------------------------------------- | --------------------------------------------- |
| **Avoid**    | Eliminate the risk entirely                 | Shut down unused services                     |
| **Transfer** | Shift the risk to a third party             | Buy cybersecurity insurance                   |
| **Mitigate** | Reduce the impact or likelihood of the risk | Implement firewalls, patch systems            |
| **Accept**   | Acknowledge the risk and take no action     | Accept low-risk vulnerability due to low cost |

#### Security Control Categories

1. **Administrative (Managerial) Controls**

- Policies, procedures, guidelines
- Security awareness training
- Risk assessments
- Access control policies

2. **Technical (Logical) Controls**

- Firewalls, IDS/IPS
- Encryption, MFA
- Access control systems
- Antivirus, patch management

3. **Physical Controls**

- Locks, fences, security guards
- CCTV, biometric access
- Alarm systems
- Data center security

4. **Operational Controls**

- Incident response procedures
- Backup and recovery processes
- Change management
- Patch management
- Monitoring and logging
- Job rotation and separation of duties
- Security awareness training
- Data handling procedures

#### Functional Types of Security Controls

- **Preventive Controls** – stop incidents (firewall, access control)
- **Detective Controls** – detect incidents (logs, IDS)
- **Corrective Controls** – fix after incident (backup, patching)
- **Deterrent Controls** – discourage attacks (warning signs)
- **Compensating Controls** – alternative when primary control not possible
- **Recovery Controls** – restore systems (disaster recovery, backups)

#### Access Control Models

| Model                     | Key Feature / Focus                          | Notes / Example                                                                      |
| ------------------------- | -------------------------------------------- | ------------------------------------------------------------------------------------ |
| **DAC**                   | Owner discretion; focus on availability      | Users control access to their own resources                                          |
| **MAC**                   | Labels & clearance; focus on confidentiality | Access based on security labels and clearances                                       |
| **RBAC**                  | Role-based; focus on integrity               | Users assigned roles with specific permissions                                       |
| **ABAC**                  | Attributes-based; environment-aware          | Access determined by user, resource, and environment attributes                      |
| **Context/Content-based** | Access based on time, location, data content | Example: restricting sensitive data outside office hours or from untrusted locations |

> **Notes**

- **DAC** → Discretionary Access Control
- **MAC** → Mandatory Access Control
- **RBAC** → Role-Based Access Control
- **ABAC** → Attribute-Based Access Control
- **Rule-Based** → Rule-Based Access Control

### Governance vs Management

**Governance (C-Level):** Strategy, direction, objectives, risk appetite
**Management:** Execution, risk tolerance, alignment with governance

> **Key C-Level Roles:** `CEO`, `CIO`, `CTO`, `CSO`, `CISO`, `CFO`

### Laws & Regulations

- **Criminal Law:** Society as victim
- **Civil Law:** Individuals as victims
- **Administrative/Regulatory Law:** HIPAA, FDA, FAA, etc.
- **Private Regulations:** PCI-DSS, Contracts
- **Religious & Customary Law:** Region-specific conduct rules

> **Notes**

- `HIPAA` – Health Insurance Portability and Accountability Act.
- `PHI` - Protected Health Information.
- `ECPA` – Electronic Communications Privacy Act.
- `PATRIOT` - Providing Appropriate Tools Required to Intercept and Obstruct Terrorism.
- `CFAA` – Computer Fraud and Abuse Act.
- `PCI-DSS` – Payment Card Industry Data Security Standard.
- `GDPR` – General Data Protection Regulation.
- `FDA` – Food and Drug Administration.
- `FAA` – Federal Aviation Administration.

### ISC2 Code of Ethics

The ISC2 Code of Ethics is a set of `professional` rules and guidelines for `cybersecurity` professionals.

- It defines `how security practitioners should behave in a professional and ethical way`.
- It applies to `everyone` holding ISC2 certifications like `CC`, `SSCP` `CISSP`, etc.
- It ensures actions protect people, organizations, and society while maintaining trust in the cybersecurity profession.

> Key idea: `It’s not just laws—it’s about morality, responsibility, and professionalism in cybersecurity.`

#### The Code has two main parts

1. Preamble - `General Principles`
2. Four Canons - `Core Rules`

##### Preamble - `General Principles`/`Ethical Foundation`

The preamble emphasizes:

- Protecting `society`, `public trust`, and `infrastructure`
- Acting with `honesty`, `justice`, `responsibility`
- Providing `competent` and `diligent service`
- Advancing the `security` profession

> In simple terms: `Use your cybersecurity skills for good — not harm.`

##### Four Canons - `Core Rules`

###### Canon 1: Protect Society, the Common Good, Public Trust, and Infrastructure

**Meaning:** This is the `highest priority`. Always think about impact on `people` and `society`.

**Key Responsibilities**

- Avoid actions that could harm public systems
- Report security vulnerabilities responsibly
- Do not exploit systems for personal gain
- Protect critical infrastructure (banks, hospitals, govt systems)

> Real-world Example
If you discover a vulnerability in a banking system → report it responsibly (not exploit it)

###### Canon 2: Act Honorably, Honestly, Justly, Responsibly, and Legally

**Meaning:** Be ethical and lawful in all actions.

**Key Responsibilities**

- Follow laws and regulations
- Do not engage in hacking without authorization
- Avoid conflicts of interest
- Be truthful in reports and communications

> Real-world Example

- Do not falsify security audit results
- Do not access systems without permission

###### Canon 3: Provide Diligent and Competent Service to Principals

**Meaning:** Do your job `properly` and `professionally`. 👉 `Principals` = your employer, client, or organization

**Key Responsibilities**

- Maintain and improve your skills
- Give accurate advice
- Protect client data
- Deliver quality work

> Real-world Example
If you are designing a security system → use best practices, not shortcuts

###### Canon 4: Advance and Protect the Profession

**Meaning:** Help improve the cybersecurity field

**Key Responsibilities**

- Share knowledge
- Support ethical behavior
- Avoid damaging the reputation of cybersecurity professionals
- Mentor others

> Real-world Example

- Contribute to open-source security tools
- Help juniors learn security concepts

##### Easy Way to Remember `Mnemonic: 'SHDP'`

| Canon | Mnemonic | Focus      | Key Idea             |
| :---: | :------: | ---------- | -------------------- |
|   1   |    S     | Society    | Protect people first |
|   2   |    H     | Integrity  | Be legal & honest    |
|   3   |    D     | Work       | Do your job well     |
|   4   |    p     | Profession | Improve the field    |

## Domain 2 Business Continuity Plan `BCP`, Disaster Recovery Plan `DRP`, and Incident Response

### Business Continuitity Plan

Long-term strategic plan to ensure continued operations after a disruptive event. Covers the entire organization, not just IT. The purpose lists of disaster scenarios and steps to return to regular operations.

**Iterative Process:** Written ahead of time and continually improved with input from key staff and external consultants.

![Business Continuitity Plan](/01-CC/img/domain-2/business-continuitity-plan.png)

**Senior Management Role**

- Initiates, approves, and owns the plan.
- Ensures due diligence and top-down IT security.

### Related Plans included in BCP

- **COOP (Continuity of Operations Plan):** Alternate site operations, reduced capacity operations for up to 30 days.
- **CIRP (Cyber Incident Response Plan):** Response to cyber events (DDOS, malware, viruses).
- **OEP (Occupant Emergency Plan):** Staff/facility protection, evacuation procedures, drills.
- **BRP (Business Recovery Plan):** Steps to restore normal business operations.
- **Continuity of Support Plan (IT Contingency Plan):** Focused on IT systems.
- **CMP (Crisis Management Plan):** Coordination among management during emergencies.
- **CCP (Crisis Communications Plan):** Internal/external communications, who talks to the press.

### Offsite Copies & EOC

- Keep digital & physical copies offsite.
- Emergency Operations Center (EOC) – command/control during disasters.

### BCP Development Steps

- Project Initiation
- Scope the Project
- Business Impact Analysis (BIA)
- Identify Preventive Controls
- Recovery Strategy
- Plan Design & Development
- Implementation, Training & Testing
- Maintenance (iterative, review/update every 12 months)

### Disater Recovery Plan

Short-term plan to restore critical IT systems after a disaster. Subset of BCP. It focus on IT systems supporting critical business functions.

- **Lifecycle of Disater Recovery Plan**
  `Mitigation → Preparation → Response → Recovery`

  ![Disater Recovery Plan](/01-CC/img/domain-2/disater-recovery-plan.png)

  - `Mitigation:` Reduce likelihood & impact of disaster.
  - `Preparation:` Build procedures, programs, tools.
  - `Response:` Follow procedures, notify appropriate staff, contain damage.
  - `Recovery:` Restore basic and full functionality.

- **Simulated Tests:** DRP Review, Read-through, Walkthrough/Tabletop, Simulation Drill.
- **Physical Tests:** Partial interruption, failover to secondary systems.
- **Business Impact Analysis (BIA)** Terms:
  - **RPO (Recovery Point Objective):** Maximum acceptable data loss.
  - **RTO (Recovery Time Objective):** Time to restore systems.
  - **WRT (Work Recovery Time):** Time to configure recovered systems.
  - **MTD (Maximum Tolerable Downtime):** Maximum downtime before severe impact.
  - **MTBF (Mean Time Between Failures):** Predict hardware failure frequency.
  - **MTTR (Mean Time to Repair):** Time to repair failed systems.
  - **MOR (Minimum Operating Requirements):** Minimum environment & system specs for recovery.
- **Recovery Strategies:**
  - **Redundant Site:** Full replication, automatic failover
  - **Hot Site:** Houses critical systems, near-real-time data.
  - **Warm Site:** Restores from backups, manual failover (4–24+ hrs).
  - **Cold Site:** No hardware/backups, manual setup, weeks to recover.
  - **Reciprocal Agreement Site:** Partner organization shares space.
  - **Cloud/Subscription Site:** Paid provider hosts minimal/full replica.
  - **Mobile Site:** Data center on wheels, moveable.
- **Lessons Learned:**
  - Focus on improving processes, not blaming.
  - Updates feed into BCP/DRP improvements.

### Incident Management

Monitoring, detecting, and responding to security events. The purpose of predictable and well-understood responses to events or intrusions.

- **Disaster Categories:**
  - Natural,
  - Human,
  - Environmental (same as BCP/DRP).
- **Event Hierarchy:**
  - **Event:** Observable change in state (neutral).
  - **Alert:** Trigger warning for specific events.
  - **Incident:** Multiple adverse events, often human-caused.
  - **Problem:** Incident with unknown cause, needs root-cause analysis.
  - **Inconvenience:** Minor non-disruptive failures.
  - **Emergency:** Potential loss of life or property.
  - **Disaster:** Facility unusable ≥24 hours.
  - **Catastrophe:** Facility destroyed.
- **CIRT (Cyber Incident Response Team):**
  - Senior Management,
  - Incident Manager,
  - IT Security,
  - Technical Leads,
  - Public Relations - PR,
  - Human Resouce - HR,
  - Legal,
  - Auditors.
- **Incident Response Lifecycle (8 Steps):**
  1. **Preparation** – Policies, procedures, training, tools.
  2. **Detection** – Analyze events, use IDS/IPS, correlate across network.
  3. **Response** – Contain incident, isolate affected systems.
  4. **Mitigation** – Eradicate threat, patch vulnerabilities.
  5. **Reporting** – Technical & non-technical updates to management.
  6. **Recovery** – Restore systems carefully, monitor for persistence.
  7. **Remediation** – Broader fixes, patch all affected systems.
  8. **Lessons Learned** – Improve future response, feed into preparation.
- **Root-Cause Analysis:** Identify underlying weaknesses to prevent recurrence.

## Domain 3 Access Controls Concepts

### Access Controls

Access Control is the process of deciding `Who` can access `What` resources and `How` they can use them.

#### Basic Components

| Component   | Meaning                           |
| ----------- | --------------------------------- |
| **Subject** | User / system requesting access   |
| **Object**  | Resource (file, database, system) |
| **Action**  | Read, write, execute              |

#### Access Control Process Flow - IAAA

1. `Identification` → Who are you? (Username)
2. `Authentication` → Prove it (Password, biometrics)
3. `Authorization` → What can you access?
4. `Accounting (Auditing)` → What did you do?

#### Access Control Categories

| Type                           | Description                                          | Example                                |
| ------------------------------ | ---------------------------------------------------- | -------------------------------------- |
| **Administrative (Directive)** | Policies, procedures, governance (management-level)  | Security policy, training, standards   |
| **Technical (Logical)**        | Technology-based controls (systems & software)       | Firewall, IAM, encryption              |
| **Physical**                   | Protect physical environment                         | Locks, guards, CCTV                    |
| **Operational**                | Day-to-day security procedures carried out by people | Incident response, backups, monitoring |

#### Access Control Types

| Type             | Purpose       | Example        |
| ---------------- | ------------- | -------------- |
| **Preventative** | Stop attack   | Firewall       |
| **Detective**    | Detect attack | IDS            |
| **Corrective**   | Fix issue     | Patch          |
| **Recovery**     | Restore       | Backup         |
| **Deterrent**    | Discourage    | Guard          |
| **Compensating** | Alternative   | Manual control |

#### Access Control Models (Very Important)

| Model          | Key Idea                                      | Security Focus     | Control Type    | Flexibility            | Real-World Example                     |
| -------------- | --------------------------------------------- | ------------------ | --------------- | ---------------------- | -------------------------------------- |
| **DAC**        | Owner decides access                          | Availability       | Identity-based  | High (but less secure) | Linux/Windows file permissions         |
| **MAC**        | Labels & clearance (no user control)          | Confidentiality    | System-enforced | Very Low (very strict) | Military / Government systems          |
| **RBAC**       | Access based on job roles                     | Integrity          | Role-based      | Medium                 | AWS IAM roles, enterprise apps         |
| **ABAC**       | Uses attributes (user, resource, environment) | Flexible (All CIA) | Policy-based    | Very High              | Access based on time, location, device |
| **Rule-Based** | IF-THEN rules                                 | Depends on rule    | System rules    | Medium                 | Firewalls (allow/deny traffic)         |

> **Notes**

- **DAC** → Discretionary Access Control
- **MAC** → Mandatory Access Control
- **RBAC** → Role-Based Access Control
- **ABAC** → Attribute-Based Access Control
- **Rule-Based** → Rule-Based Access Control

## Domain 4 Network Security

### Network Basics

| Concept         | Description                      | Key Point                   |
| --------------- | -------------------------------- | --------------------------- |
| **Network**     | Computers sharing data/resources | Foundation of communication |
| **Simplex**     | One-way communication            | TV broadcast                |
| **Half-Duplex** | One at a time                    | Walkie-talkie               |
| **Full-Duplex** | Both directions simultaneously   | Phone call                  |
| **Baseband**    | Single channel                   | Ethernet                    |
| **Broadband**   | Multiple channels                | Cable internet              |

### Network Types

| Type    | Full Form                 | Coverage             | Example           |
| ------- | ------------------------- | -------------------- | ----------------- |
| **PAN** | Personal Area Network     | Very small           | Bluetooth         |
| **LAN** | Local Area Network        | Building/campus      | Office network    |
| **MAN** | Metropolitan Area Network | City                 | City-wide network |
| **WAN** | Wide Area Network         | Country/global       | Internet          |
| **GAN** | Global Area Network       | Worldwide mobility   | Mobile networks   |
| **VPN** | Virtual Private Network   | Secure over internet | Remote access     |

### Switching Types

| Type                  | Description            | Key Point              |
| --------------------- | ---------------------- | ---------------------- |
| **Circuit Switching** | Dedicated path         | Reliable, expensive    |
| **Packet Switching**  | Data in packets        | Efficient, widely used |
| **QoS**               | Traffic prioritization | Used for VoIP          |

### OSI Model (Very Important)

| Layer | Name         | Key Function           | Examples     |
| ----- | ------------ | ---------------------- | ------------ |
| 7     | Application  | User interface         | HTTP, FTP    |
| 6     | Presentation | Encryption, formatting | SSL/TLS      |
| 5     | Session      | Connection control     | Session mgmt |
| 4     | Transport    | End-to-end delivery    | TCP, UDP     |
| 3     | Network      | Routing                | IP, ICMP     |
| 2     | Data Link    | MAC addressing         | Ethernet     |
| 1     | Physical     | Hardware transmission  | Cables       |

### TCP/IP Model

| Layer          | Maps to OSI | Function                 |
| -------------- | ----------- | ------------------------ |
| Application    | OSI 5–7     | User services            |
| Transport      | OSI 4       | End-to-end communication |
| Internet       | OSI 3       | Routing (IP)             |
| Network Access | OSI 1–2     | Physical transmission    |

### IP Address & Ports

| Concept         | Description         |
| --------------- | ------------------- |
| **IP Address**  | Identifies device   |
| **Port**        | Identifies service  |
| **MAC Address** | Hardware identifier |

### Port Ranges

| Range       | Type       |
| ----------- | ---------- |
| 0–1023      | Well-known |
| 1024–49151  | Registered |
| 49152–65535 | Dynamic    |

### Common Ports (Important)

| Port  | Protocol | Use                 |
| ----- | -------- | ------------------- |
| 20/21 | FTP      | File transfer       |
| 22    | SSH      | Secure remote login |
| 23    | Telnet   | Insecure login      |
| 25    | SMTP     | Email sending       |
| 80    | HTTP     | Web                 |
| 110   | POP3     | Email receive       |
| 143   | IMAP     | Email access        |
| 443   | HTTPS    | Secure web          |
| 3389  | RDP      | Remote desktop      |

### IPv4 vs IPv6

| Feature       | IPv4         | IPv6                          |
| ------------- | ------------ | ----------------------------- |
| Size          | 32-bit       | 128-bit                       |
| Format        | Decimal      | Hexadecimal                   |
| Address Count | ~4.3 billion | Massive (virtually unlimited) |
| Security      | Added later  | Built-in (IPSec)              |

### Key Protocols

| Protocol  | Function             | Risk          |
| --------- | -------------------- | ------------- |
| **ARP**   | IP → MAC mapping     | ARP poisoning |
| **ICMP**  | Ping/troubleshooting | Recon attacks |
| **DHCP**  | Assign IP            | Rogue DHCP    |
| **HTTP**  | Web (unencrypted)    | Sniffing      |
| **HTTPS** | Secure web           | Safer         |

### Transport Protocols

| Protocol | Type                | Use Case        | Key Feature |
| -------- | ------------------- | --------------- | ----------- |
| **TCP**  | Connection-oriented | Web, email      | Reliable    |
| **UDP**  | Connectionless      | VoIP, streaming | Fast        |

### Network Attacks

| Attack            | Description             |
| ----------------- | ----------------------- |
| **SYN Flood**     | Half-open TCP attack    |
| **Smurf**         | ICMP flood              |
| **Fraggle**       | UDP flood               |
| **ARP Poisoning** | Fake MAC mapping        |
| **MITM**          | Intercept communication |

### Network Cables

| Type      | Description       | Pros         | Cons      |
| --------- | ----------------- | ------------ | --------- |
| **UTP**   | Unshielded copper | Cheap        | EMI risk  |
| **STP**   | Shielded copper   | Less EMI     | Expensive |
| **Fiber** | Light-based       | Fast, secure | Costly    |

### Cable Issues

| Issue           | Meaning                   |
| --------------- | ------------------------- |
| **EMI**         | Signal interference       |
| **Crosstalk**   | Signal leakage            |
| **Attenuation** | Signal loss over distance |

### LAN Topologies (Very Important)

| Topology | Structure               | Advantage       | Disadvantage                  |
| -------- | ----------------------- | --------------- | ----------------------------- |
| **Bus**  | Single cable line       | Simple, cheap   | Single failure breaks network |
| **Ring** | Circular connection     | Organized flow  | Failure affects entire ring   |
| **Star** | Central device (switch) | Fault isolation | Central device failure        |
| **Mesh** | Interconnected nodes    | High redundancy | Expensive, complex            |
| **Tree** | Hierarchical            | Scalable        | Depends on root               |

### Wi-Fi Basics

| Concept           | Description                    |
| ----------------- | ------------------------------ |
| Wi-Fi             | Wireless LAN using IEEE 802.11 |
| Access Point (AP) | Connects wireless devices      |
| WLAN              | Wireless Local Area Network    |
| Frequency         | 2.4 GHz / 5 GHz                |

### Wi-Fi Attacks

| Attack    | Description         | Impact               |
| --------- | ------------------- | -------------------- |
| Rogue AP  | Unauthorized AP     | Confidentiality risk |
| Evil Twin | Fake AP (same name) | Data theft           |
| Jamming   | Signal interference | Availability loss    |

### Wireless Technologies

| Technology              | Range   | Speed     | Key Feature     |
| ----------------------- | ------- | --------- | --------------- |
| **Bluetooth**           | 10–100m | Low       | PAN connections |
| **Li-Fi**               | Short   | Very high | Uses light      |
| **Zigbee**              | 10–100m | Low       | IoT devices     |
| **Satellite**           | Global  | Medium    | High latency    |
| **Cellular (3G/4G/5G)** | Wide    | High      | Mobile networks |

### Cellular Generations

| Generation | Speed     | Latency  |
| ---------- | --------- | -------- |
| 3G         | ~2 Mbps   | High     |
| 4G         | ~200 Mbps | Medium   |
| 5G         | 5–20 Gbps | Very low |

### Types of Hackers

| Type          | Description        |
| ------------- | ------------------ |
| White Hat     | Ethical hacker     |
| Black Hat     | Malicious attacker |
| Grey Hat      | In-between         |
| Script Kiddie | Low skill attacker |

### Attack Sources

| Type       | Description                 |
| ---------- | --------------------------- |
| Insider    | Authorized user misuse      |
| Outsider   | External attacker           |
| Hacktivist | Political/social motive     |
| Government | State-sponsored attacks     |
| Botnet     | Network of infected devices |

### Malware Types

| Type   | Description            |
| ------ | ---------------------- |
| Virus  | Needs user action      |
| Worm   | Self-spreading         |
| Trojan | Hidden malware         |
| RAT    | Remote control malware |

### IDS vs IPS

| Feature  | IDS         | IPS            |
| -------- | ----------- | -------------- |
| Action   | Detect only | Detect + Block |
| Mode     | Passive     | Active         |
| Response | Alert       | Prevent attack |

### Detection Methods

| Method    | Description    | Weakness           |
| --------- | -------------- | ------------------ |
| Signature | Known patterns | Misses new attacks |
| Heuristic | Behavior-based | False positives    |
| Hybrid    | Both           | More complex       |

### Detection Results

| Type           | Meaning                   |
| -------------- | ------------------------- |
| True Positive  | Attack detected correctly |
| True Negative  | Normal traffic allowed    |
| False Positive | Normal flagged as attack  |
| False Negative | Attack missed !           |

### Security Systems

| System | Function                 |
| ------ | ------------------------ |
| SIEM   | Collects & analyzes logs |
| SOAR   | Automates response       |

### Honeypots & Honeynets

| Type     | Description                   |
| -------- | ----------------------------- |
| Honeypot | Fake system to trap attackers |
| Honeynet | Network of honeypots          |

### Firewalls (Very Important)

| Type             | Layer       | Function          |
| ---------------- | ----------- | ----------------- |
| Packet Filtering | L1–L3       | Basic filtering   |
| Stateful         | L1–L4       | Tracks sessions   |
| Application      | L7          | Deep inspection   |
| NGFW             | Multi-layer | Advanced security |

### Firewall Design

| Concept          | Description                      |
| ---------------- | -------------------------------- |
| DMZ              | Isolated external-facing network |
| Fail Closed      | Blocks traffic on failure        |
| Proxy            | Acts on behalf of client         |
| Host Firewall    | Protects single device           |
| Network Firewall | Protects network                 |

### 0-Day Attacks & Exploits

| **Term**                | **Definition**                   | **Key Point**          |
| ----------------------- | -------------------------------- | ---------------------- |
| **0-day Vulnerability** | Unknown or undisclosed weakness  | No patch available yet |
| **0-day Exploit**       | Code that uses the vulnerability | Used by attackers      |
| **0-day Attack**        | Actual attack using exploit      | Happens before fix     |

### Stuxnet Summary

| **Component** | **Function**                |
| ------------- | --------------------------- |
| Worm          | Spreads and executes attack |
| Link file     | Auto-executes the worm      |
| Rootkit       | Hides malware activity      |
| USB Infection | Initial entry point         |
| PLC Attack    | Modifies industrial systems |

### Virtualization

| **Concept**         | **Description**                  | **Example**        |
| ------------------- | -------------------------------- | ------------------ |
| Virtualization      | Multiple systems on one hardware | VMware             |
| Hypervisor Type 1   | Runs on hardware                 | Data centers       |
| Hypervisor Type 2   | Runs on OS                       | Personal PC        |
| VM Escape           | Attack between VMs               | Security risk      |
| Resource Exhaustion | Overuse of CPU/RAM               | Availability issue |

### Cloud Computing Types

| **Type**        | **Description**           | **Example Use**                |
| --------------- | ------------------------- | ------------------------------ |
| Private Cloud   | Owned by one organization | Bank systems                   |
| Public Cloud    | Shared services           | AWS, Google Cloud              |
| Hybrid Cloud    | Mix of private + public   | Sensitive + non-sensitive data |
| Community Cloud | Shared by similar orgs    | Government agencies            |

### Cloud Service Models

| **Model** | **Provider Gives** | **User Controls** |
| --------- | ------------------ | ----------------- |
| IaaS      | Hardware           | OS & apps         |
| PaaS      | Hardware + OS      | Apps              |
| SaaS      | Everything         | Just usage        |

### Distributed & Modern Computing

| **Type**           | **Description**                         |
| ------------------ | --------------------------------------- |
| Distributed System | Multiple systems act as one             |
| HPC                | High-speed computation (supercomputers) |
| Edge Computing     | Processing near user                    |
| IoT                | Smart connected devices                 |

### Power Issues

| **Term** | **Meaning**        |
| -------- | ------------------ |
| Blackout | Long power loss    |
| Brownout | Low voltage (long) |
| Sag      | Short low voltage  |
| Surge    | Long high voltage  |
| Spike    | Short high voltage |

### Backup Types (Very Important)

| **Type**     | **What it Backs Up** | **Archive Bit** | **Restore Speed** |
| ------------ | -------------------- | --------------- | ----------------- |
| Full         | Everything           | Cleared         | Fastest           |
| Incremental  | Since last backup    | Cleared         | Slow (many files) |
| Differential | Since last full      | Not cleared     | Faster            |
| Copy         | Full backup          | Not cleared     | Special use       |

### RAID Levels

| **RAID** | **Technique**     | **Min Disks** | **Feature**        |
| -------- | ----------------- | ------------- | ------------------ |
| RAID 0   | Striping          | 2             | Speed only         |
| RAID 1   | Mirroring         | 2             | Redundancy         |
| RAID 5   | Striping + Parity | 3             | Speed + redundancy |

### Fire Suppression

| **Method**    | **How it Works**   |
| ------------- | ------------------ |
| Remove Heat   | Water              |
| Remove Oxygen | Gas (FM200, Halon) |
| Remove Fuel   | Rare               |

### Secure Design Principles

| **Principle**        | **Meaning**                |
| -------------------- | -------------------------- |
| Least Privilege      | Minimum access             |
| Need to Know         | Only required info         |
| Separation of Duties | Split responsibilities     |
| Defense in Depth     | Multiple layers            |
| Zero Trust           | Never trust, always verify |
| Fail Secure          | Stay secure on failure     |

## Domain 5 Security Operations

### Cryptography & Hashing

| Topic            | Key Idea                      | Important Points                                                        |
| ---------------- | ----------------------------- | ----------------------------------------------------------------------- |
| **Cryptography** | Protect data using encryption | Ensures **Confidentiality, Integrity, Authentication, Non-repudiation** |
| **Plaintext**    | Original message              | Unencrypted                                                             |
| **Ciphertext**   | Encrypted message             | Not readable                                                            |
| **Encryption**   | Plaintext → Ciphertext        | Uses algorithm (cipher)                                                 |
| **Decryption**   | Ciphertext → Plaintext        | Uses key                                                                |
| **Symmetric**    | One shared key                | Fast, but key distribution problem                                      |
| **Asymmetric**   | Public + Private key          | Secure but slow                                                         |
| **Hybrid**       | Combines both                 | Used in real-world (TLS, HTTPS)                                         |
| **Hashing**      | One-way function              | Used for **Integrity**                                                  |
| **Collision**    | Same hash for different data  | Rare but possible                                                       |

### Cryptographic Attacks

| Attack                              | Description                      |
| ----------------------------------- | -------------------------------- |
| **Brute Force**                     | Try all possible keys            |
| **Key Theft**                       | Steal private key                |
| **MITM - Man-in-the-Middle Attack** | Intercept & modify communication |
| **Side Channel**                    | Use physical data (power, CPU)   |
| **Key Stretching**                  | Slows brute-force attacks        |

### Data Handling & Lifecycle

| Stage                | Description                                           |
| -------------------- | ----------------------------------------------------- |
| **Data Acquisition** | Create or collect data                                |
| **Data Use**         | Ensure CIA (Confidentiality, Integrity, Availability) |
| **Data Archival**    | Store for long-term/legal use                         |
| **Data Disposal**    | Secure deletion/destruction                           |

### Data States

| State              | Description        |
| ------------------ | ------------------ |
| **Data at Rest**   | Stored data        |
| **Data in Motion** | Data in transit    |
| **Data in Use**    | Actively used data |

### Data Disposal Methods

| Method                 | Type        | Notes                       |
| ---------------------- | ----------- | --------------------------- |
| **Delete/Format**      | Soft        | Recoverable                 |
| **Overwrite (Clear)**  | Soft        | Harder to recover           |
| **Sanitization**       | Strong      | Very difficult to recover   |
| **Purge**              | Very Strong | Not recoverable even in lab |
| **Degaussing**         | Physical    | Destroys magnetic media     |
| **Shredding/Crushing** | Physical    | Full destruction            |

### Configuration, Patch & Change Management

| Topic                        | Description                           |
| ---------------------------- | ------------------------------------- |
| **Configuration Management** | Secure baseline (hardening systems)   |
| **Patch Management**         | Apply updates to fix vulnerabilities  |
| **Change Management**        | Controlled process for system changes |

#### Change Management Flow

- `Identify → Propose → Assess Risk → Approve`
- `Test → Schedule → Notify → Implement → Review`

### Access Control (Quick Recap)

| Type                           | Description                                          | Example                                |
| ------------------------------ | ---------------------------------------------------- | -------------------------------------- |
| **Administrative (Directive)** | Policies, procedures, governance (management-level)  | Security policy, training, standards   |
| **Technical (Logical)**        | Technology-based controls (systems & software)       | Firewall, IAM, encryption              |
| **Physical**                   | Protect physical environment                         | Locks, guards, CCTV                    |
| **Operational**                | Day-to-day security procedures carried out by people | Incident response, backups, monitoring |

| Type             | Example             |
| ---------------- | ------------------- |
| **Preventative** | Firewall            |
| **Detective**    | IDS                 |
| **Corrective**   | Patch               |
| **Recovery**     | Backup              |
| **Deterrent**    | Guard               |
| **Compensating** | Alternative control |

### Security Policies

| Policy                           | Purpose               |
| -------------------------------- | --------------------- |
| **AUP - Acceptable Use Policy**  | Acceptable Use        |
| **BYOD - Bring Your Own Device** | Personal device rules |
| **Privacy Policy**               | Data handling rules   |
| **Password Policy**              | Password requirements |

### Security Awareness vs Training

| Type          | Goal                             |
| ------------- | -------------------------------- |
| **Training**  | Teach skills                     |
| **Awareness** | Change behavior (more important) |

### Social Engineering

| Technique          | Description       |
| ------------------ | ----------------- |
| **Phishing**       | Mass email attack |
| **Spear Phishing** | Targeted attack   |
| **Whaling**        | Target executives |
| **Vishing**        | Voice phishing    |
