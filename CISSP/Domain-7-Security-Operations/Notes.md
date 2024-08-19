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

