### Content

- [Security models and concepts](#security-models-and-concepts)
- [Security evaluation models](#security-evaluation-models)
- [Secure design principles](#secure-design-principles)
- [Secure system design concepts](#secure-system-design-concepts)
- [Managing the information system lifecycle](#managing-the-information-lifecycle)
- [Secure Access Service Edge](#secure-access-service-edge)
- [Hardware Architecture](#hardware-architecture)
- [Secure OS and software architectures](#secure-os-and-software-architectures)
- [Virtualization, Cloud and Distributed Computing](#virtualization-cloud-and-distributed-computing)
- [Internet of Things](#internet-of-things)
- [Emanations and Covert Channels](#emanations-and-covert-channels)
- [Web architecture and attacks](#web-architecture-and-attacks)
- [Database security](#database-security)
- [Mobile security](#mobile-security)
- [Industrial Control Systems](#industrial-control-systems)
- [Cryptography](#cryptography)
- [Cryptographic attacks](#cryptographic-attacks)
- [Digital Signatures](#digital-signatures)
- [MAC, HMAC, SSL and TLS](#mac-hmac-ssl-and-tls)
- [IPSec and PGP](#ipsec-and-pgp)
- [Physical Security](#physical-security)
- [Site selection](#site-selection)
- [Media Storage](#media-storage)
- [Asset tracking and hardware hardening](#asset-tracking-and-hardware-hardening)
- [Electricity](#electricity)
- [Fire suppression](#fire-suppression)
- [Personnel Safety](#personnel-safety)

# Security models and concepts
- Discretionary Access Control (DAC): gives subjects full control of objects they have created or been given access to.
- Mandatory Access Control (MAC): system-enforced control based on subject's clearance and object's labels.
- Role Based Access Control (RBAC): access to objects based on the role of the subject.
- Attribute Based Access Control (ABAC): access to objects based on attributes/conditions of the subject/object.
- Rule Based Access Control (RUBAC): access granted based on IF/THEN logical statements.

### Bell-LaPadula (CONFIDENTIALITY) (MAC)
- Simple Security Property: NO READ UP
- Star Security Property: NO WRITE DOWN
- Strong Star Property: NO READ/WRITE UP AND DOWN

### BIBA (INTEGRITY) (MAC)
- Simple Integrity Axiom: NO READ DOWN
- Star Integrity Axiom: NO WRITE UP
- Invocation Property: NO READ/WRITE UP

### Lattice Based Access Control LBAC (MAC)
- A subject can have multiple access rights, based on relevant lattice.
  
![image](https://github.com/user-attachments/assets/c65a9bcc-9660-403c-8ef7-117e47ca63b9)

### Graham-Denning Model
Uses Objects, Subjects and Rules.
1. Transfer Access
2. Grant Access
3. Delete Access
4. Read Object
5. Create Object
6. Destroy Object
7. Create Subject
8. Destroy Subject

### HRU model (Harrison, Ruzzo, Ullman) (INTEGRITY of Access Rights)
An operating system level computer security model that deals with the integrity of access rights in the system.
It is an extension of the Graham-Denning model, based around the idea of a finite set of procedures being available to edit the access rights of a subject on an object. There are 6 primitive operations:
- Create Object
- Create Subject
- Destroy Object
- Destroy Subject
- Enter right into access matrix
- Delete right from access matrix

### Clark-Wilson Rule (INTEGRITY)
Separates tend users from the back-end data through 'Well-formed transactions' and 'Separation of Duties'.
![image](https://github.com/user-attachments/assets/7247f1ac-69ad-4d20-8ec6-8a7c3cd815f7)

### Brewer-Nash Model
Designed to provide controls that mitigate **CONFLICT OF INTEREST** in commercial organizations and is built upon an **information flow** model. In other words, no information can flow between the subjects and objects in a way that would create a conflict of interest.

### Non-Interference Model
- Ensures that any actions that take place at a higher security level do not affect, or interfere with the actions that take place at a lower level.
- The model is not concerned with the data flow, rather **what the SUBJECT knows about the state of the system**.

### Take-Grant Protection Model
 ![image](https://github.com/user-attachments/assets/bff40e99-a3b1-4fda-8801-e910401c6709)

### Access Control Matrix
Model describing the rights of EVERY subject for EVERY object in the system. For example:
![image](https://github.com/user-attachments/assets/3a4ea7d5-364c-4e25-b602-d631d64f8ba9)

### Zachman Framework (Enterprise Architecture)
![image](https://github.com/user-attachments/assets/0d096628-2359-4ad8-af18-9bb20fb0c6e6)

### Security Modes (MAC or DAC)
The systems contain information at various levels of security classification. The mode is determined by:
- The type of users who will be accessing the systems.
- The type of data that are processed on the systems (classification levels, compartments, categories).
- The type of levels of users, their need to know, and formal access approvals that the users will have.

#### Dedicated Security Mode
![image](https://github.com/user-attachments/assets/c0cd4f24-6090-4e4b-8684-9a5e3ff2b217)

#### System High Security Mode
![image](https://github.com/user-attachments/assets/f38cbf21-e6e2-4dee-ae46-051a39d8458b)

#### Compartmented Security Mode
![image](https://github.com/user-attachments/assets/14d17d15-bc11-4bba-b8b7-4b35884ffd26)

#### Multilevel Security Mode
![image](https://github.com/user-attachments/assets/33ee1928-0e08-4325-b580-145f2108e83c)

# Security evaluation models
To choose the security systems and products we will implement in our organization, we can use evaluation models.
- The Orange Book: TCSEC / Trusted **Computer System** Evaluation Criteria (1980, DoD, part of Rainbow Books)
- The Red Book: TNI / Trusted Network Interpretation (addresses Network Systems)

- ITSEC (The European Information Technology Security Evaluation Criteria): First successful international model. Contains a lot of references from the Orange Book, but are both retired now.
- International Common Criteria (ISO/IEC 15408):
  - Common Criteria evaluations are performed on BOTH computer security products and systems. It must verify the target's security features through:
    - Target of Evaluation (TOE): The product/system that is the subject of the evaluation.
    - Protection Profile (PP): A document which identifies security requirements for a class fo security devices. Products canc omply with more than one PP. Customers looking for particular types of products can focus on those products certified against the PP that meet their requirements.
    - Security Target (ST): A document that identifies the security principles of the target of evaluation. The ST may have one or more PPs.
  - Evaluation Assurance Level (EAL): How did the system/product score on testing?
    - EAL1: Functionally TESTED.
    - EAL2: Structurally TESTED.
    - EAL3: Methodically TESTED and CHECKED.
    - EAL4: Methodically designed, TESTED and REVIEWED.
    - EAL5: Semi-formally DESIGNED and TESTED.
    - EAL6: Semi-formally VERIFIED DESIGN and TESTED.
    - EAL7: Formally VERIFIED DESIGN and TESTED.
> [!TIP]
> Fun Stress Method Medical-Doctors Seem Somewhat Verifiably Foolish
> 
> Functionally, Structurally, Methodically, Methodically Designed, Semi-formally, Semi-formally Designed Verified, Formally

# Secure design principles
- Least Privilege: minimum necessary access.
- Need to Know: Even if you have access, if you don't need to know, then you shouldn't access the data.
- Separation of Duties: More than 1 individual on one single task - intended to prevent fraud and error.
- Defense in Depth
- Secure defaults: think security baselines. Determined by risk analysis and usability tests.
- Fail securely: If the system fails, it stays at least as secure as it was before the failure
- Keep it simple

### Threat Modeling
- PASTA / Process for Attack Simulation and Threat Analysis (Attacked-focused)
  - 7 step process that aligns business objectives and technical requirements.
  - Dynamic threat identification, helps develop an asset-centric mitigation strategy.
    1. Definition of Objectives
    2. Definition of Technical Scope
    3. Application Decomposition and Analysis
    4. Threat Analysis
    5. Weakness/Vulnerability Analysis
    6. Attack Modeling & Simulation
    7. Risk Analysis/Management

- STRIDE / (Developer-focused)
  - Spoofing: Authenticity
  - Tampering: Integrity
  - Repudiation: Non-repudiability
  - Information disclosure: Confidentiality
  - DoS: Availability
  - Elevation of Privilege: Authorization

- TRIKE (Acceptable Risk Focused)
  - uses a requirements model
  - stakeholders, at least the data owner, defines the acceptable use of risk -> gives us a threat model
  - threats are enumerated and assigned risk values
  - risk assessment

- DREAD (Abandoned by Microsoft in 2008)
  - Disaster/Damage
  - Reproducibility
  - Exploitability
  - Affected Users
  - Discoverability
 Each category is given a rating from 1 to 10.

- **Trust but verify**: Implicit trust, but we verify you.
- **Zero-Trust**: Never trust, always verify (NIST SP 800-207 zero trust architecture).
- Privacy by design: Proactive, not reactive. Privacy as security default.
- Shared responsibility: mainly regarding cloud computing environments.

# Secure system design concepts

- **Layering**: Separate hardware and software functionality into layers.
  - Layers can influence layers adjacent, but not past that.
  - eg. The change of a hard disk to another of the same/different type has no influence on the applications.
  - eg. Changing an OS may change some applications, but will not affect the hardware.
> [!TIP]
> APPLICATIONS <-> OPERATING SYSTEM <-> KERNEL AND DEVICE DRIVERS <-> HARDWARE

- **Abstraction**: Hiding unecessary details from the user - providing seamless experience to user.

- **Security Domains**
A list of OBJECTS a SUBJECT is allowed to access, groups of OBJECTS/SUBJECTS with similar security requirements.
  - Kernel mode: (Supervisor Mode): Allowing low-level unrestricted access to memory, CPU, disk, etc.
  - User mode (Problem mode): No direct access to hardware, it is directed through an API.
  - Open systems: use open standards and can use standard components from multiple vendors.
    - Hard disks are built and evaluated to a certain standard.
    - What most organizations use and is considered more secure.
  - Closed systems: use proprietary hardware/software. (Security through obscurity)
    - We may not get hit with the latest vulnerability, but our systems and software have not been as rigorously tested and audited for flaws as open systems and may be easy to gain access to.
  - Ring Model: 4 ring model that separates Users (Untrusted) from the kernel (Trusted).
    - The model is slow and rarely used. Most operating systems use only rings 0 and 3.
    - There is a new addition to the model: Hypervisor mode (-1), sits below the Client kernel in Ring 0.
      - Ring -1: Hypervisor mode (MOST privileged)
      - Ring 0: Kernel
      - Ring 1: Other OS components that do not fit into Ring 0.
      - Ring 2: Device drivers
      - Ring 3: User applications (LEAST Privileged)
        
# Managing the information system lifecycle
# Secure Access Service Edge
# Hardware Architecture
# Secure OS and software architectures
# Virtualization, Cloud and Distributed Computing
# Internet of Things
# Emanations and Covert Channels
# Web architecture and attacks
# Database security
# Mobile security
# Industrial Control Systems
# Cryptography
# Cryptographic attacks
# Digital Signatures
# MAC, HMAC, SSL and TLS
# IPSec and PGP
# Physical Security
# Site selection
# Media Storage
# Asset tracking and hardware hardening
# Electricity
# Fire suppression
# Personnel Safety
