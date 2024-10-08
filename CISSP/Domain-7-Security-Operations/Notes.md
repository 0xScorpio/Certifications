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


### Disk Forensics
There are 4 types of disk-based forensic data:

![image](https://github.com/user-attachments/assets/48125b46-34bd-43f4-8f7b-636dc6beb531)

- **Allocated Space**: The portions of the disk that are marked as actively containing data.
- **Unallocated Space**: When a file is deleted, the parts of the disk that held the deleted file are marked as unallocated and made available for use. (This is also why deleting a file does nothing, the data is still there until overwritten.)
- **Slack Space**: If a file does not require the use of an entire cluster, then some extra space will exist within.
- **Bad Blocks/Clusters/Sectors**: hard disks may end up with sectors that can't be read due to a physical defect - these bad sectors will be ignored by the OS.

In each of these spaces, attackers can hide their data/malware by marking them as slack, bad blocks or unallocated spaces.

### Network Forensics
Network forensics tends to be a pro-active investigation since network traffic is transmitted and then lost.
1. Monitoring a network for anomalous traffic and identifying intrusions (IDS/IPS).
2. Relates to law enforcement - analysis of captured network traffic can include tasks such as reassembling transferred files, searching for keywords and parsing human communication such as emails or chat sessions.

![image](https://github.com/user-attachments/assets/88343142-94ee-41ac-8b1e-ad19cbfab1d3)

![image](https://github.com/user-attachments/assets/f6776b41-d739-4681-ae93-5935a8e8c53d)

![image](https://github.com/user-attachments/assets/3af9869d-ffbb-4053-974c-6faf68786809)

![image](https://github.com/user-attachments/assets/bfb1cf33-6303-404f-821b-d1523655990e)

### Incident Management
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
### Honeypots
### Configuration Management
### Patch Management
### Change Management
### Zero-Days
### Backups
### RAID
### Redundancy
### BCP and DRP
### Warfare, terrorism, sabotage and ransomware
### Personnel
### DRP basics
### Developing our BCP and DRP
### Business Impact Analysis
### Supply and infrastructure redundancy
### Disaster Recovery sites
### Other BCP subplans
### Employee redundancy
### Testing the Plans
### After a disruption
