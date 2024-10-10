### Key Terms:
- Business Continuity Plan (BCP): Long-term plan to ensure the continuity of business operations.
- Disaster Recovery (DR): Policies, procedures and tools to recover from a natural, environmental or man-made disaster.
- Collusion: An agreement between two or more individuals to subvert the security of a system.
- Continuity of Operations Plan (COOP): A plan to maintain operations duraing a disaster.
- Disaster Recovery Plan: Short-term plan to recover from a disruptive event, part of our BCP.
- Mean Time Between Failures (MBTF): How long a new/repaired system will function on average before failing.
- Mean Time to Repair (MTTR): How long it will take to recover a failed system.
- Mirroring: Complete duplication of data to another disk, used by some levels of RAID.
- Striping: Spreading data writes across multiple disks to achieve performance gains, used by some levels of RAID.
- Real Evidence: Tangible and Physical objects a.k.a Hard Drives, USBs - NOT the data on them!
- Chain of custody: Who handled it / When / What did they do with it / Where did they handle it?
- Resume Producing Event (RPE): a f@#$kup that could cause someone to get fired??

## Administrative Personnel Controls
- Least Privilege
- Need To Know
- Separation of Duties: To prevent fraud and errors. For the exam, assume the organization is large enough to use separation of duties - in smaller companies where that is not practical, compensating controls should be in place. Separation of duties involves distributing responsibilities among multiple individuals to prevent fraudulent activity. By ensuring no single individual has control over all parts of a critical process, organizations can reduce the risk of fraud. While employee background checks, access controls, and physical security measures are all important security controls, separation of duties is considered a key method for controlling and reducing the risk of internal fraud
- Job Rotation: Helps detect errors and frauds.
- Mandatory Vacations
- Non-disclosure Agreement (NDA)
- Background Checks: For sensitive positions the background check is an ongoing process.
- Privilege Monitoring
- PAM: PIM is a subset of PAM. Always try to add MFA unto PAM.
- Logging and Monitoring activities
- Threat Intelligence
  - Threat Feeds: A stream of raw current and potential threats.
  - Threat Hunting: Actively looking for threats on our network.
- User and Entity Behavior Analytics (UEBA): Use machine/deep learning to model typical and atypical user behavior, setting a baseline.
  - Use cases: How do normal users use our network and data?
  - Data sources: normally a data lake//warehouse or SIEM, should not be deployed directly.
  - Analytics: To build the baseline and detect anomalies.

## Digital Forensics
Focuses on the recovery and investigation of material found in digital devices in relation to computer crime. Closely related to incident response, forensics is based on gathering and protecting the evidence, where IR is based on how we react in an event breach. We want to preserve the crime scene and evidence, to later prove the integrity of it in court.

#### Processing the evidence
1. Whenever we have a compromised drive, we take that drive and create a bit-level copy.
2. Once we have the copy, we make a hash of the original drive as well as the copy drive and ensure that they match. Any changes in the hash means a change of integrity from original to copy.
NEVER MAKE ANY CHANGES ON THE ORIGINAL COPY!
3. Once our **forensics investigation** is done on the copy drive, we do another hash check and ensure that all 'three' hashes match for forensics integrity!

#### General Forensics Investigation Process
1. Identify the potential evidence, azquire, analyze and make a report.
2. Be aware of how we gather our forensice evidence - attackers like to cover their tracks and delete any evidence or logs.
3. If malware is in volatile memory, rather than shutting the system down. we can safely disconnect the system from the network and take bit by bit copies of the memory, drives, running processes and network connection data.
> [!IMPORTANT]
> Always work from MOST volatile to LEAST volatile, starting with RAM and ending with the hard disks.

We want to make sure we use our incident response plan, which can include our HR and Legal departments.
Ensure that evidence is acquired in a legal manner.

> [!IMPORTANT]
> The 4th Amendment of the US Constitution states, "The right of the people to be secure in their persons, houses, papers, and effects, against unreasonable searches and seizures, shall not be violated."

Despite the 4th Amendment, if anything is subpoenaed, search warranted, turned over voluntarily and/or in exigent circumstances (immediate danger of being destroyed), law enforcement is given the rgith to bypass it.

![image](https://github.com/user-attachments/assets/bebd53ec-6741-463c-8928-1d30499d8666)


## Disk Forensics
There are 4 types of disk-based forensic data:

![image](https://github.com/user-attachments/assets/48125b46-34bd-43f4-8f7b-636dc6beb531)

- **Allocated Space**: The portions of the disk that are marked as actively containing data.
- **Unallocated Space**: When a file is deleted, the parts of the disk that held the deleted file are marked as unallocated and made available for use. (This is also why deleting a file does nothing, the data is still there until overwritten.)
- **Slack Space**: If a file does not require the use of an entire cluster, then some extra space will exist within.
- **Bad Blocks/Clusters/Sectors**: hard disks may end up with sectors that can't be read due to a physical defect - these bad sectors will be ignored by the OS.

In each of these spaces, attackers can hide their data/malware by marking them as slack, bad blocks or unallocated spaces.

## Network Forensics
Network forensics tends to be a pro-active investigation since network traffic is transmitted and then lost.
1. Monitoring a network for anomalous traffic and identifying intrusions (IDS/IPS).
2. Relates to law enforcement - analysis of captured network traffic can include tasks such as reassembling transferred files, searching for keywords and parsing human communication such as emails or chat sessions.

![image](https://github.com/user-attachments/assets/88343142-94ee-41ac-8b1e-ad19cbfab1d3)

![image](https://github.com/user-attachments/assets/f6776b41-d739-4681-ae93-5935a8e8c53d)

![image](https://github.com/user-attachments/assets/3af9869d-ffbb-4053-974c-6faf68786809)

![image](https://github.com/user-attachments/assets/bfb1cf33-6303-404f-821b-d1523655990e)

## Incident Management
Incidents and events can generally be categorized in 3 classes:
- Natural: Hurricanes, floods, earthquakes, etc.
- Human: done either intentionally or unintentionally by humans
- Environmental: the environment we work in a.k.a power grid, internet connections, hardware failures, software flaws

TERMS:
- **Event**: an observable change in state, neither negative nor positive.
- **Alert**: warnings for specific events.
- **Incident**: multiple adverse events happening in our systems/network, often caused by people.
- **Problem**: Incident with an unknown cause - we'd still follow similar steps to incident response.
- **Inconvenience**: Non-disruptive failures, hard disk failures, 1 node down in a cluster.
- **Emergency/Crisis**: Urgent, event with potential for loss of life or property.
- **Disaster**: entire facility is unusable for 24 hours or longer.
- **Catastrophe**: Facility entirely destroyed.

- IR 8-step lifecycle

![image](https://github.com/user-attachments/assets/44a59ba1-1fa6-4220-862f-5cc22c52a6ff)

  - **Preparation**: outlines all the steps we do for incidents. Policies, procedures, training, tools.
  - **Detection**: Events analyzed to determine if it's a security incident. IDS/IPS
  - **Response**: Tools and training come into play. Contain an event, create bit-level copies of a system, isolation.
  - **Mitigation**: Understand the cause of the incident. RCA to understand if we need patches and vulnerability management.
  - **Reporting**: document throughout the process from detection phase (technical/non-technical)
  - **Recovery**: carefully restore systems to operational status - reinsertion determined by the business unit responsible.
  - **Remediation**: happens during mitigation phase, and continues after mitigation.
  - **Lessons Learned**: produce a report to senior management, with findings, we can only make SUGGESTIONS. Outcomes feed to Preparation phase.

### Preventive/Detective Controls (IDS/IPS)
Two types:
1. Network-Based: placed on network segment (a switch port in promiscuous mode)
   - Can't look into encrypted traffic.
   - Deployed on one switch, port and NIC must be promiscuous and port must be a span port. 
2. Host-Based: on a client/workstation/server
   - Since we're at Layer 7, we can see the unencrypted traffic.
   - certain attacks can turn off HIDS/HIPS
   - if we choose to do traffic analysis, it can impact host by slowing it down.

Two approaches to identifying:
A. Signature/Pattern Matching
B. Heuristic/Behavourial Based Matching

**How hackers mask/evade IDS/IPS detection**
- Fragmentation: Sending fragmented packets can avoid the system from detecting the attack signature.
- Avoiding Defaults: Attackers can send malware over an unexpected port.
- Low-Bandwidth Coordinated Attacks: multiple agents are used to attack from various ports and hosts, difficult to deduce network scans.
- Address spoofing/proxying: Attackers can use proxy servers to bounce an attack, making it harder to detect origin.
- Pattern Change Evasion: Attacker changes the data used slightly.

![image](https://github.com/user-attachments/assets/2ed723e7-c1eb-4d0c-b3f4-3d3b3af46172)

### SIEM and SOAR systems
- SIEM: gathers logs from all our systems and centralizes storage to allow near real-time automated identification, analysis and recovery of security events.
- SOAR: uses AI to allow us to respond to incidents automatically. Can at times react to an event and usually manages logs to reduce load.

![image](https://github.com/user-attachments/assets/212cd971-92c5-4d46-becd-73b437d89553)

*Spelling mistake: SOAR is generally more expensive than SIEM.

### Application positive-listing
Basically whitelisting, from most secure to least:
- hash
- path
- name

Good security policies should also lock down USB ports, CD drives, and anywhere else where you can load malicious code unto systems from external devices. Use Group Policy for all this.

### Honeypots
Systems that look like our real system - sole purpose is to attract attackers. This is to learn our vulnerabilities, alert us during 'breaches' and learn to mitigate such attacks. Always talk to LEGAL before deploying honeypots since there's a thin line with ENTRAPMENT (making someone commit a crime) and ENTICEMENT (attacker already decides on committing a crime, and you made it more appealing) and gain senior management's APPROVAL. Make sure they are segmented and isolated between sensitive servers.

- **Low-interaction honeypot** simply captures connection attempts and alerts an intrusion has been attempted.
- **High-interaction honeypot**: allows attackers to compromise and gain access to the system.

**Production honeypots are placed inside the production network with other production servers by an organization to improve their overall state of security. Normally, production honeypots are low-interaction honeypots, which are easier to deploy.**

> [!TIP]
> The MOST effective way to use honeypots/honeynets among the provided options is 'As a tool to gather information on attackers'. Honeypots and honeynets are primarily used to detect, deflect, or study attempts at unauthorized use of information systems. They serve as decoys, mimicking real systems to deceive attackers, allowing security professionals to observe and analyze the attackers' behaviors, and gather intelligence about their techniques. While they do serve as decoys, their primary value is in the information they provide rather than actively blocking or mitigating attacks.

### Configuration Management

When receiving or building new systems, they often come in a default insecure state, thus we have to harden them before introducing them into our environment. We develop a long list of ports to close, services to disable, accounts to delete and any missing patches.

### Patch Management

For multiple systems, tools like SCCM or WSUS help not only push patches but also any software we want to distribute to our orgnaization. Best to do these pushes AFTER HOURS to not impact availability. We tend to avoid midnights since a lot of backups and EOD jobs run then, therefore a decent timeframe is approx. 2:00am-4:00am.

## Change Management
The formalized process on how we handle changes to our environments. Done right, we should:
- have full documentation and understanding of all systems in place
- communicate changes to all appropriate parties
- Change Review board should be comprised of both IT and other operational units
- when a change is proposed to the change board, thorough research needs to be done to understand the full impact
- person/group submitting the change should clearly explain the reasons for the change (pros/cons)
- any final change requires senior leadership approval

For example:

![image](https://github.com/user-attachments/assets/d28f9d60-2e0a-4730-8783-bc09b2629205)

Change Management Process:
- PLAN: request, analyze, approve
- DO: plan implementation, communicate, implement and test
- CHECK: success->communicate or failure(rollback)->communicate
- ACT: acceptance, lessons learned

![image](https://github.com/user-attachments/assets/efa84023-89b5-455c-b31e-7739cdb764c9)

### Zero-Days
Differences with Zero-Day vulnerability, exploit and attack.

**Stuxnet Case**

![image](https://github.com/user-attachments/assets/cbc05969-fb04-4921-ab26-aa9ee670e0ce)

## Backups
To ensure internal SLAs, we need to provide as high availability as possible. For backups, we use:

- **Full**: backup everything. (e.g. data kept for 1 year)
  - Clears all archive bits
  - requires 1 tape
- **Incremental**: backup what was changed since the last backup. (e.g. data kept for 30 days)
  - Clears all archive bits
  - requires 4 tapes (restore a full backup alongside incremental backups)
  - faster to backup, but longer to restore
- **Differential**: backup everything that was changed since the last FULL backup.
  - Does not clear archive bits
  - requires 2 tapes (the full backup and differential backup)
  - faster to restore, but longer to backup
- **Copy**: same as FULL, but we do not clear the archive bit or the flag.
  - often used before system updates or patches, in order to revert in case something goes wrong

In our backup solutions, our backup policies should state what to backup, what to exclude, how long to keep the data of various backup types. Based on our policies, requirements or regulations (whichever is longer).

## RAID
RAID provides us redundancy NOT backup!

- **Disk Mirroring**: writing the same data across multiple disks. (slower since RAID has to write data twice)
- **Disk Striping**: writing the data simultaneously across multiple disks. (faster but does not provide redundancy)

- **RAID 0**: STRIPING, no fault tolerance, faster write speed, requires at least 2 disks
- **RAID 1**: MIRRORING, 2 disks identical data, write on both disks
- **RAID 5**: STRIPING with PARITY, parity is spread across disks, requires at least 3 disks (only 1 disk can fail at a time)
- **RAID 10**: First RAID 0, then split into 2 disks of RAID 1, requires at least 4 disks, 50% capacity usage due to PARITY.

## Redundancy
Stuff about clustering that you already know. (active/passive, nodes, etc.)

- **Database Shadowing**: exact real-time copy of the database to another location (best practice: another geographical location)
- **Electronic Vaulting**: remote backup service sent off-site electronically at certain intervals or during file changes.
- **Remote Journaling**: Sends transaction logs to remote locations - not the files themselves. Transactions can be rebuilt from the logs if we lose the original files.

## BCP and DRP

- **Business Continuity Plan**
  - long-term strategic business plans, policies and procedures for continued operations after a disruptive event.
  - lists a range of disaster scenarios and the steps an organization must take in each scenario
  - Contains:
    - COOP (Continuity of Operations Plan)
    - Crisis Communications Plan
    - Critical Infrastructure Protection Plan
    - Cyber Incident Response Plan
    - DRP (Disaster Recovery Plan)
    - ISCP (Information System Contingency Plan)
    - Occupant Emergency Plan

![image](https://github.com/user-attachments/assets/4178c7c7-ac42-4ac2-814d-f7de754ab688)

- **Disaster Recovery Plan**
  - short-term version of BCP (subset of BCP)
  - focuses on critical IT and business functions and how we back them up
  - much more system specific, where BCP is more non-system specific

Three categories of disasters:
- **Natural**
- **Human**: errors and omissions (accidental)
- **Environmental**: power outages, hardware failures, provider issues, etc.

## Personnel

![image](https://github.com/user-attachments/assets/31e7792a-e351-4164-9887-ce9bc445bef7)

## DRP basics
1. What is the **objective/purpose**?
2. **Who** (people/teams) will be responsible during disruptions?
3. What will these (people/teams) **do** during disruptions?

![image](https://github.com/user-attachments/assets/ecd80cff-cd06-4981-bcba-227c541ac8e2)

## Developing our BCP and DRP

![image](https://github.com/user-attachments/assets/6f46a8cb-dfc2-4f10-80c9-73bc20aa5371)

Senior management needs to be involved and committed during the BCP/DRP process.
- Need to ba part of at least the initiation and final approval of the plans
- They must show due-care and due-diligence since they are ultimately liable
- Top-Down IT security approach (exam assumes that already)
- Senior management or Legal talks to the press

![image](https://github.com/user-attachments/assets/bb25577e-c082-494f-b907-9213b23f5c3f)

## Business Impact Analysis
Identifies critical and non-critical organization systems, functions and activities.

- A function may be considered critical based on unaccapetable disruption factors or dictated by law.
- For each criticalsystem in scope, 2 values are assigned:
  1. RPO (Recovery Point Objective): the acceptable amount of data that is lost.
  2. RTO (Recovery Time Objective): the amount of time it takes to restore a system.
     - WRT (Work Recovery Time): amount of time required to configure a recovered system.
     - MTD (Maximum Tolerable Downtime): amount of time a system can be inoperable before our organization is severaly impacted.
    
In other words, we want MTD to always be greater than or equal to RTO + WRT.

![image](https://github.com/user-attachments/assets/59ae88b2-d059-4281-85fe-3853d950ea7b)

![image](https://github.com/user-attachments/assets/6dc0096e-f929-4d5d-9a95-02541bf001e4)

![image](https://github.com/user-attachments/assets/e2a24be6-b809-49e6-b578-653b3d34205b)

![image](https://github.com/user-attachments/assets/76ca5dc5-1739-4b2f-a04a-a86fdd2ec99b)

## Supply and infrastructure redundancy
## Disaster Recovery sites
## Other BCP subplans
## Employee redundancy
## Testing the Plans
## After a disruption
