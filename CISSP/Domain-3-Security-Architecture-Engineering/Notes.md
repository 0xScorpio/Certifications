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
- [Malware](#malware)
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

![image](https://github.com/user-attachments/assets/92170b43-5c04-44d2-8ce5-eda5b379c96d)

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
- Planning: Define scope, objectives and security requirements.
- Development: Build or buy systems that meet security requirements.
- Implementation: Install, configure, and test systems in the operational environment.
- Operations: Daily operations, ensuring effectiveness and security.
- Retirement: decommission, secure data migration, destruction and environmentally compliant hardware disposal.

# Secure Access Service Edge
SASE combines network security functions and WAN capabilities for dynamic, secure access. It addresses the limitations of traditional security models, promoting flexibility and scalability.

Key components include:
- SD-WAN
- Integrated services (NGFW, CASBs, ZT)

SASE enables consistent security policy enforcement, regardless of user or application location.
- Requires careful planning and consideration to align with organizational needs.
- Adoption involves a cultural shift towards integrated, cloud-centric IT model.

# Hardware Architecture
Newer models have the bus split up into two components.
- Northbridge (Host bridge): faster than the Southbridge, since it's closer to the CPU. CPU/RAM/Graphics.
- Southbridge: Peripheral, I/O.

- CPU: brains.
  - ALU (Arithmetic Logic Unit): performs arithmetic/logic operations. Does the math.
  - CU (Control Unit): handles fetching (from memory) and execution of instructions by directing the coordinated operations of the ALU, registers and other components. Also sends instructions to the ALU.

CPU instructions:
- Fetch: Gets the instructions from memory into the processor.
- Decode: Internally decodes what it is instructed to do.
- Execute: Takes the add/subtract values from the registers.
- Store: Stores the result back into another register (retiring the instruction)
> [!TIP]
> Pipelining: Combining multiple steps into one process; can Fetch, Decode, Execute, Store in the same clock cycle.

- Interrupt: a signal to the processor emitted by hardware or software indicating an event that needs immediate attention.
- Process: an executable program and its associated data loaded and running in memory. (Heavy Weight Process / tasks)
  - Processes may exist in multiple states:
    - New: process beign created
    - Ready: process waiting to be executed by the CPU
    - Running: process being executed by the CPU
    - Blocked: waiting for I/O
    - Terminate: completed process
- Threads: A parent process may spawn additional child processes called threads. (Light Weight Process)
  - Threads can share memory, resulting in lower overhead compared to HWP.
 
- Multithreading: the ability of a CPU to execute multiple processes/threads concurrently.
- Multiprocessing: A computer using more than one CPU at a time for a task.
- Multitasking: Tasks sharing a common resource (1 CPU).
- Multiprogramming: A computer running more than one program at a time (eg. Word and Chrome)
  
- Memory protection: prevents one process from affecting the CIA of another process.
- Process isolation: logical control that tries to prevent a process from interfering with another process.
- Hardware segmentation: mapping processes to specific memory locations.
- Virtual Memory: virtual address mapping between applications and hardware memory. Used for multitasking/processing/swapping, etc.
- Swapping: moves entire processes from RRAM to Disk (primary memory to secondary memory)
- Paging: copies a block from RAM to Disk.

- BIOS (Basic Input Output System) (Low-level OS)
  - runs a basic POST (Power On Self Test) including verifying the integrity of the BIOS testing, memory, system devices.
  - stored in Read-Only memory (EEPROM) (EPROM on legacy systems)
  - once the POST process is complete, it locates the boot sector for the OS. Kernel loads and executes, and OS boots.

- WORM media (Write Once Read Many)
  - early versions of ROM is WORM media (data written once and can't be changed)
  - CD/DVDs can be WORM media (R) if they are not R/W.

- TPM (Trusted Platform Module)
  - international standard for a secure cryptoprocessor.
  - used for RNG, encryption, hashing and secure storage of cryptographic keys and message digests.
  - most commonly used to ensure boot integrity.

- DEP (Data Execution Prevention)
  - security feature that can prevent damage to your computer from viruses/threats.
  - eg. prevents harmful programs from executing code from system memorylocations reserved for Windows and authorized programs.

- ASLR (Address Space Layout Randomization): a memory-protection process for OS; it guards against buffer-overflow attacks by randomizing the location where system executables are loaded into memory.

- Microservices
  - Really good at a single-task
  - Not connected or related to other components in the MSA architecture
  - Resilient and fault-tolerant
  - If we have distributed deployment, testing can be tedious and complicated.

- Containerization: portability, scalability, deployment speed, enhanced security, cost-effective.
- Serverless (FaaS): does not hold resources in volatile memory. Cost is based on actual use.
  - Elasticity: resources expand/contract based on need.
  - Scalability: we scale resources to meet expected needs.

![image](https://github.com/user-attachments/assets/5afbc5a2-de9f-47f9-8faf-acf77970591d)

# Secure OS and software architectures

### Kernel
At the core of the OS is the Kernel. At ring 0 (or 3), it interfaces between the OS/applications and hardware.
- A **monolithic kernal** is one static executable and the kernel runs in supervisor mode.
- **Microkernels** are mopdular kernels. A microkernel is smaller and has less native functionality than a monolithic kernel. They can add functionality via loadable kernel modules.
- **Reference monitor** is a core function of the kernel; it handles all access between subjects and objects. It is always on and can't be bypassed.

### Users and File permissions
- Linux/Unix: rwx permissions which can be set at an Owner, Group or World level.
- Windows NTFS (New Technology File System):
  - Read, Write, Read/Execute, Modify, Full Control
  - It is a type of DAC (Discretionary Access Control): who can access and how they can access it, is at the owner's discretion.

# Virtualization, Cloud and Distributed Computing
### Virtualization
- Possibility for multiple clients on the same hardware platform - running under the OS (Ring -1).
- Traffic between the clients on the host doesn't have to traverse our network.

- **Type 1 Hypervisor**: (BARE METAL) is a part of a virtualization OS that runs on top of host hardware (data center)
- **Type 2 Hypervisor**: runs of top of regular OS like Windows10 (personal PC)

![image](https://github.com/user-attachments/assets/594e73b3-9153-4c52-8916-ac3ae1812b4c)

> [!TIP]
> - Clients on the same host should be on the SAME network segment; a host should never house multiple zones.
> - **VM Escape**: is when an attacker can jump from the host or a client, to another client.
> - **Hypervisor Security**: If an attacker can get access to the hypervisor, they may gain access to the clients.
> - **Resource Exhaustion**: Admins may oversubscribe CPU/Memory and may not realize more is needed.

### Cloud Computing
There are 4 types of cloud computing:
1. Private
2. Public
3. Hybrid
4. Community

For public cloud computing, the following infrastructures exist:

![image](https://github.com/user-attachments/assets/f06118fa-8e90-443c-846e-53ba8a633c6f)

- IaaS: everything before the OS.
- PaaS: everything before the application.
- SaaS: everything except the interaction of the software.

- **Grid Computing**: can make use of resources not currently in use from thousands of computers to perform very complex tasks.
  - Each node has a smaller subtask
  - BOINC (Berkeley Open Infrastructure for Network Computing) has over 4 million machines enrolled, used for various research.
  
- **P2P / Peer-to-Peer**: any system can be a client and/or server.
  - Used on torrent networks for sharing of music/movies/etc.
  - Older versions have centralized index servers, making it easier to disrupt a sharing network; current version is decentralized.
  - Each client is often also a server and has the index stored. Taking down 10,000 out of 100,000 will have no discernable impact.

- **Thin Clients**: (Boot sequence -> BIOS > POST > TCP/IP > BOOTP/DHCP)
  - **Diskless Workstation**: a diskless node has all the normal hardware/firmware except the disk and low-level OS that performs the POST. It then downloads the kernel and higher-level OS.
  - **Thin Client Applications**: we use a web browser to connect to the application on a server. The full application is housed and executed on the server instead of your PC.

### Distributed Computing
Also known as **Distributed Computing Environment** and **concurrent/parallel computing**.
DCEs are a collection of individual systems that work together to support a resource or provide an overall service.
Most end-users see the DCE as a single entity and not as multiple systems.
+ They provide us with horizontal scaling (size, geography, admin), fault tolerance, cost-effectiveness and low latency.

- **High-Performing Computing system (HPC)**
  - HPCs have 3 components: Compute, Network, Storage
  - All 3 components must have enough resources to avoid bottleneck issues.
  - e.g.: supercomputers
![image](https://github.com/user-attachments/assets/4fe15edb-05e1-4836-8c4a-394af79fce2c)

- **Edge Computing System**:
  - Think SASE; the procesing data is done as close as possible to where it is needed. This is done by moving the data and computer resources.
  - Optimizes bandwidth use and lower latency.
  - e.g.: content delivery networks (CDNs)
  
# Internet of Things
> [!TIP]
> If you use IoT within an organization/home, segment that part of the network off from everything else!!!

IoT devices are often criticized for their lack of robust security measures, which makes the other options—lack of strong authentication protocols, inability to patch and update software, and inadequate data encryption and privacy protection—common vulnerabilities. These devices often prioritize convenience and functionality over security, leading to potential gaps that attackers can exploit. 

# Emanations and Covert Channels
Often electromagnetic emanations!
- Information that can be disseminated from the electrical changes from a system or a wire.
- It is possible to log a user's keystrokes on a smart phone using a motion sensor.
- It is unintentional information-bearing signals, which if intercepted and analyzed, can lead to compromise.
- Electromagnetic emanations can be blocked by heavy metals.

- **Covert Channels**: capability to transfer information using channels not intended to do so.
  - **Covert Timing Channels**: operations that affect the real-time response observer by the receiver.
    - e.g.: a wrong username may take 100s to confirm, while a wrong password takes 500ms. Effectively, you get the error, but an attacker is able to tell when they use a correct username due to the delay difference.
  - **Covert Storage Channels**: Hidden information through the modification of a stored object.
    - Certain file sizes can have certain meanings.
    - Attackers can add data in payload if outbound ICMP packets are enabled.

- **Steganography**: Hiding a message within another media (images, videos, etc.)
- **Digital Watermarks**: encode data into a file (could be hidden using steganography / often used to fingerprint files)

![image](https://github.com/user-attachments/assets/1d297fff-1ce3-440d-b065-ffce04faaed7)

![image](https://github.com/user-attachments/assets/e513064b-13f6-4f80-b6ac-77f9a14a5387)

![image](https://github.com/user-attachments/assets/ad0ee14a-c7e2-410c-8ea1-f050bf998b57)

# Malware
- **Viruses**: require human interaction, often transmitted via portable devices. When executed, replicates itself by inserting its own code into other programs.
  - Macro: written in macro languages (word, outlook).
  - Boot Sector: infects Master Boot Record, ensuring it runs every time the PC boots.
  - Stealth: tries to hide from OS and AV software.
  - Polymorphic: changes their **signature** to avoid AV definitions.
  - Multipart/Multipartite: Spreads across multiple vectors (files, OS, boot sector, etc.)
 
- **Worms**: spreads through **self-propagation**, makes it much easier to spot.
- **Trojans**: malicious code **embedded** in a 'normal' program.
- **Rootkits**: replaces parts of the OS/Kernel with malicious payload. User rootkits on Ring 3 and Kernel rootkits on Ring 0.
- **Logic Bombs**: malicious code that is triggered at a certain **time** or event.
- **Packers**: programs that compress .exe files, to hide malware from its binary executable format.
- AV types:
  - Signature: known signatures using a server-side database, hence needs to be constantly updated.
  - Heuristic: behavioural based, outliers and abnormal behaviour - can result in a lot of false positives.

# Web architecture and attacks
- **Applets**: small applications embedded into other software (web browsers).
  - Executable, downloaded from a server and installed locally on the client.
  - Often written in **Java** or **ActiveX**(control):
    - Java: run in sandbox environment - segmenting java from OS -> OS agnostic.
    - ActiveX: runs with certificates - since it's an MS product, interacts with Windows OS.

![image](https://github.com/user-attachments/assets/9ff3b320-dcc7-4ac4-900b-3547621b5357)

- SOA: software design where services are provided to other components by application components, through a communication protocol over a network.

# Database security
- Polyinstantiation: two or more instances of the same file depending on who accesses it.
  - The real information may be available to subjects with Top Secret clearance, but different information will be available to staff with Secret or lower clearance.

Securing databases is often through **defense in depth**.

# Mobile security

![image](https://github.com/user-attachments/assets/54044b2c-1d0b-4ab0-858f-ee8d587a0f67)

![image](https://github.com/user-attachments/assets/041d7229-8c30-41ae-bc1e-9ad2b5cc734b)

![image](https://github.com/user-attachments/assets/7b27de60-5697-4dec-af14-e3e72cabf62b)

# Industrial Control Systems
- SCADA (Supervisory Control And Data Acquisition): control system architecture that uses computers, network data communications and GUIs for high-level process supervisory management.
- DCS (Distributed Control Systems): control system for a process or plant in which autonomous controllers are distributed throughout the system - with a central operator supervisory control.
- PLC (Programmable Logic Controller): industrial digital computer adapted for the control of manufacturing processes such as assembly lines, robotic devices, or any acitivity that requires high reliability control, ease of programming, and process fault diagnosis.

SCADA uses the DNP3 protocol (Dsitributed Network Protocol):
- Primarily for communications between master station (control centers), RTUs (remote terminal units) or IEDs (intelligent electronic devices).

![image](https://github.com/user-attachments/assets/ae4a07fc-123d-46b5-96f5-8765aeedbb2f)

![image](https://github.com/user-attachments/assets/c9d756e8-bc9a-4798-bfa9-cde02166c5ee)

![image](https://github.com/user-attachments/assets/866579dd-53e4-448a-a0ff-08038fbcd5f3)

# Cryptography
Cryptography supports **Confidentiality**, **Integrity** and **Authentication** via non-repudiation.

Quick terms:
- Cryptology: science of securing communications.
- Cryptanalysis: science of breaking encrypted communication.
- Cipher: cryptographic algorithm.
- Plaintext: cleartext, unencrypted.
- Ciphertext: encrypted message.
- Book Cipher: often uses a book as the key (244.2.13 = page 244, sentence 2, word 13)
- Running-Key Cipher: uses a well-known test as a key, but uses a previously agreed upon phrase.

- Monoalphabetic Ciphers: substitutes one letter for another.
- Polyalphabetic Ciphers: substitutes letters starting at different base points per round. (T -> W on 1st round -> D on 2nd, etc.)
- Frequency Analysis: analyzing the frequency of a certain character based on the language. English (e) is used 12.7% of the time on average. With enough encrypted text, you can possibly break it.

- Confusion: relationship between plaintext and ciphertext - should be as random as possible.
- Diffusion: how the order of the plaintext should be diffused/dispersed in the ciphertext.
- Substitution: character replacements.
- Permutation: transposition -> rearranging characters of the plaintext.
  
![image](https://github.com/user-attachments/assets/bf45bb43-a3cd-4cd1-8030-a64a0d3fe3e9)

Vigenere Cipher
![image](https://github.com/user-attachments/assets/e1dea602-d683-4df8-aaf4-d81a48c5df2a)

- Cipher Disk: 2 concentric disks with alphabets on them with pre-agreed monoalphabetic and disk is turned in pre-agreed direction.
- Enigma: Rotary based. 3 rotors early on, broken. 4 rotors made it harder.
- Purple: Japanese rotary, similar to Enigma. Broken with 3 rotors by US, UK, Russia.

- One-time Pads: cryptographic algorithm where plaintext is combined with random key. Unbreakable but impractical, since it can only be used ONCE!
  - Vernam Cipher: first known one-time pad using bits and XOR.

Jefferson Disk
![image](https://github.com/user-attachments/assets/643a5809-ea2d-448d-a45e-f471860681e2)

SIGABA
![image](https://github.com/user-attachments/assets/7c6f9381-96cb-469a-ad89-7e5720dbdb5b)

- COCOM (Coordinating Committee of Multilateral Export Controls) 1947-1994
  - used to prevent the export of 'critical technologies' from 'Western' countries to 'Iron Curtain' countries during the cold war.
  - Encryption is considered as 'critical technologies'.
 
## Encryption
![image](https://github.com/user-attachments/assets/20b56da6-2d7d-484b-84c2-5ff8659ef986)

### Symmetric Encryption
- **DES (Data Encryption Standard) [BROKEN]**
  - DEA or DES in exam
  - **64-bit block cipher, 56 bit key, 16 rounds of encryption, uses Fistel.**
  - 5 different modes it can encrypt data with - Block, Stream, Initialization Vector and if encryption errors propagate to the next block:
    - **ECB** (Electronic Code Book):
      - simple, weakest. no IV or chaining. (2 separate encryptions with same plaintext produces identical ciphertext)
    - **CBC** (Cipher Block Chaining):
      - **block cipher**
      - uses IV and every subsequent block uses XOR from first block.
      - the weakness is an encryption error which will propagate through all blocks after the error since they build on each other, breaking integrity.
    - **CFB** (Cipher Feedback):
      - **stream cipher**
      - It uses feedback, IV and it has the same error propagation.
    - **OFB** (Output Feedback):
      - Instead of the previous ciphertext for XOR, it uses the subkey before it is XOR'd to the plaintex - ensures that error propagations do NOT occur.
    - **CTR** (Counter):
      - First block XOR'd with 1, second block with 2, third block with 3; since the Feedback is predictable it can be done in parallel.
      
- **3 DES (Triple DES)**
  - Developed to extend DES system life to prepare for AES.
  - 3 rounds of DES
    - K1 (keymode1): 3 different keys with 112-bit key strength
    - K2 (keymode2): 2 different keys with 80-bits and 1/3 same key
    - K3 (keymode3): Same key 3 times, just as insecure as DES
  - considered secure until 2030 and still commonly used (K1).

- IDEA (International Data Encryption Algorithm):
  - designed to replace DES.
  - **128-bit key, 64-bit block size**
  - considered safe, but not widely used since it's **patented** and **slower than AES**.

- AES (Advanced Encryption Standard):
There a better and faster symmetric encryptions than AES, however, AES is open-source compared to other patented, paid options.
  - Rijndael
  - 128 bits
  - considered secure
  - uses both transposition and substitution
  - AES operates on a 4x4 column-major order of matrix of bytes:

During the **initial round**, there is an AddRoundKey function, where each byte is combined with a block of the round key using bitwise XOR:

![image](https://github.com/user-attachments/assets/eb903471-c812-425d-b523-a011e48c29e8)

The next **rounds**, there are 3 different functions that occur:
- **SubBytes**: a non-linear substitution step where each byte is replaced with another according to a lookup table.
- **ShiftRows**: a transposition step where the last three rows of the state are shifted a certain number of steps.
- **MixColumns**: a mixing operation which operates on the columns, combining the 4 bytes in each column.

![image](https://github.com/user-attachments/assets/d3a27c43-13ce-48a8-80bb-19c988f0b2b1)
![image](https://github.com/user-attachments/assets/558e6e0f-9753-437a-b352-23f0250d8b72)

In the **final round**, the follow functions are left:
- SubBytes
- ShiftRows
- AddRoundKey

The key size specifies the number of repetitions of transformation rounds that occur to convert the plaintext to ciphertext.
- 10 cycles for 128-bit keys
- 12 cycles for 192-bit keys
- 14 cycles for 256-bit keys

> [!IMPORTANT]
> For the exam, know it's symmetric, open-source, secure, and how the initial, next and final rounds work, what each round does and how many rounds/cycles go through per key size.

- **Blowfish**
  - uses Feistel
  - Block cipher, 64-bit blocks, 32 to 448-bit key lengths
  - NOT secure
 
- **Twofish**
  - uses Feistel
  - Block cipher, 128-bit blocks, 128/192/256-bit key lengths
  - secure
 
- **Feistel cipher (network)**
  - Cipher splits a plaintext block into 2 halfs (L and R).
  - Process goes through several rounds, the R half does not change.
  - The Right half (Rn) is XOR with a subkey (Kn) for each round (F).
  - The XOR value (F) is XOR with the Left half (Ln).
  - The recipient reverse the subkey order and XORs to get the plaintext.

![image](https://github.com/user-attachments/assets/3c64bd79-5550-4503-b4f3-0fb2e35b8e56)

**Feistel (modified) Algorithms**
Blowfish, Camellia, CAST-128, DES, FEAL, ICE, KASUMI, LOKI97, Lucifer, MARS, MAGENTA, MISTY1, RC5, TEA, Triple DES, Twofish, XTEA ...
**Generalized Feistel Algorithms**
CAST-256, MacGuffin, RC2, RC6, Skipjack

- **RC4**:
  - Used by WEP/WPA/SSL/TLS
  - Pseudorandom keystream
  - NOT secure
  - Stream cipher with 40 to 2048-bit key length

- **RC5**:
  - Block cipher, 32/64/128-bit blocks with key lengths 0-2040 bits.
  - Secure IF high enough blocks/key

- **RC6**:
  - AES3 finalist
  - Based on RC5, but edited to meet AES requirements and use Feistel.
  - Block cipher, 128-bit block with 128/192/256-bit key length.
  - Secure

### Asymmetric Encryption
In the 1970s, multiple asymmetric keys were developed incliding Diffie-Hellman (1976) and RSA (1977).
- 2 keys, public and private key pair
- use of one way functions:

**Prime Number Factorization**:
  - Easy to multiply 2 high numbers, hard to discern the 2 numbers used for the result.
  
**Discrete Logarithms**:
  - Easy to log 4584932532 to the power of 4537829458, hard to discern X to the power of Y with just the result.

- **RSA (Rivest-Shamir-Adleman)**
  - Used to exchange symmetric keys, slow and patent-protected (1977-1997, 20 years)
  - 1024-4096-bit key
  - considered SECURE
  - RSA-704 broken due to a side-channel attack

- **Diffie-Hellman (DH)**

- **Elliptic Curve Cryptography (ECC)**
  - Uses discrete logarithms applied to elliptical curves - much stronger
  - Often found in low-power devices, since they can use shorter key lengths and be as secure
  - Patented, therefore costs money to use.
  - 256-bit ECC key is as strong as 3072-bit RSA key.

- **ElGamal**
  - based on Diffie-Hellman key exchange
  - used in free GNU Privacy Guard software, recent versions of PGP and other cryptosystems.

- **DSA (Digital Signature Algorithm)**
  - uses a different algorithm for signing and encryption than RSA, yet provides the same security.
  - DSA is a variant of ElGamal signature scheme.

- **Knapsack (Merkle-Hellman knapsack cryptosystem)**
  - The public key is used only for ENCRYPTION and the private key for DECRYPTION.
  - NOT secure

### Hashing
Only used for INTEGRITY.

- **MD5**
  - 128-bit fixed length hash
  - widely used despite flaw found regarding collisions

- **MD6**
  - Was supposed to replace MD5 but SHA2/3 were better
  - Withdrew due to flaws
 
- **SHA1**
  - 160-bit hash value
  - Weak collision avoidance but still commonly used

- **SHA2**
  - considered collision resistant
  - somewhat used, relatively new

- **SHA3**
  - Finalized in August 2015

- **HAVAL (Hash of Variable Length)**
  - Not widely used
  - MD length is varied between 128/160/192/224/256 bits

- **RIPEMD**
  - Developed outside of defense to ensure no government backdoors
  - 128/256/320 bit hashes
  - NOT secure

- **RIPEMD160**
  - fixed flaws of RIPEMD
  - 160-bit hashes
  - not widely used
  - Considered SECURE

PRIMARY function of **salting** is to defend against dictionary attacks or a pre-compiled rainbow table attack.

**Nonce**: arbitrary number that may only be used once.

### Quantum Cryptography and Key Distribution

- **Quantum entanglement**:
  - forms the foundation of quantum cryptography, ensuring communication channels are immune to hacking.

Quantum Key Distribution (QKD) relies on the Heisenberg uncertainty principle and the no-cloning theorem to prevent eavesdropping. Real-time detection of tampering/eavesdropping is possible with QKD. Challenges include distance limitations and the fragility of quantum states.

**Heisenberg uncertainty principle:** certain pairs of physical properties such as position and momentum, can't be simultaneously measured with perfect accuracy.

In other words, a hacker couldn't measure the quantum state of a proton without disturbing the proton itself. Therefore, by observing the proton, we can tell if it has been tampered with.

**No Cloning Theorem**: it is impossible to create an identical copy of an unknown quantum state.

This defends from the hacker creating a duplicate of the proton in order to measure its quantum state.

Researchers are currently using **Quantum Repeaters** and satellite0based QKD to overcome distance limitations in quantum communication.

# Cryptographic attacks

- **Steal the Key**: literally
- **Brute Force**: literally
- **Key stretching**: pause 1-2 seconds during every password verification
- **Digraph attack** similar to frequency analysis, but looks at common pairs (TH, HE, IN, ER)
- **MiTM**
- **Session Hijacking**: takes over web user's session ID
- **Social Engineering**
- **Adaptive Chosen Plaintext**: attacker adapts the following rounds based on previous rounds.
- **Meet-In-The-Middle**: known plaintext - attacker has to know some parts of the plaintext and ciphertexts to break multiple ciphers, which have 2 or more secret keys for multiple encryptions using the same algorithm. (Think 3DES)
- **Known Key**: attacker knows something about the key (password is 8 chars / first char is uppercase, etc.)
- **Differential Cryptanalysis**: find the difference between related plaintexts.
- **Linear Cryptanalysis**: known plaintext attack - attacker has a lot of plain/cipher text pairs.
- **Differential Linear Cryptanalysis**
- **Side-Channel Attacks**: use of physical data to break a crypto system. (CPU cycles, power consumption, sound, etc.)
- **Implementation Attacks**: a vulnerability is left from the implementation of the application/service.
- **Key Clustering**: when 2 different symmetric keys used on the same plaintext produce the same ciphertext, both can decrypt ciphertext from the other key.
- **Pass The Hash**: attackers passes on the hashed password to a system
- **Kerberos Exploitation**:
  - **Overpass the Hash / Pass the Key**: used when NTLM is disabled on a network, since systems will generate an NTLM hash and store it in memory.
  - **Pass The Ticket**: attacker attempts to collect tickets held in lsass.exe process. Attacker then injects the ticket to impersonate the user.
  - **Silver Ticket**: attacker uses NTLM hash of a service account to make a TGS ticket.
  - **Golden Ticket**: attacker gains access to hash of the Kerberos service account and can create any tickets they want in AD.
  - **Kerberos Brute-Force**: kerbrute.py or Rubeus.exe to report if username is valid or not.
  - **ASREPRoast**: if Kerberos pre-authentication is disabled (default is enabled)
  - **Kerberoasting**: attacker collects encrypted TGS tickets (service accounts). When enough collected, can be decrypted offline. Again, tries to find service accounts with Kerberos pre-authentication disabled.
- **Fault Injection**: attacker tries to compromise the integrity of cryptographic devices by external faults (active side-channel, stress tests, temperature, light, etc.)

# Digital Signatures
Mainly for integrity and non-repudation.

- **Key Escrow**: Keys are kept by a 3rd party organization.
- **Certificate Authority**
- **Organizational Registration Authority**: within an org, authenticates the certificate holder prior to certificate issuance.
- OCSP (Online Certification Status Protocol): client/server hybrid, better balance, faster, keeps list of revoked certificates.
- **Clipper chip**: NSA developed an encryption device that secured voice and data messages with a built-in backdoor.

# MAC, HMAC, SSL and TLS

![image](https://github.com/user-attachments/assets/afd8be5f-bd83-4a7c-b49a-904fda51446a)

![image](https://github.com/user-attachments/assets/6c4fc586-ab1c-4116-8edf-9bfbe321edcf)

# IPSec and PGP

![image](https://github.com/user-attachments/assets/2fbebcfe-b833-45d9-b8b3-0208251eaf2b)

![image](https://github.com/user-attachments/assets/b5d12f54-d69c-483d-923b-92bb79518bb2)

![image](https://github.com/user-attachments/assets/d2e5d9d5-0420-4780-b23a-709fe020f104)

![image](https://github.com/user-attachments/assets/70209130-9481-404a-b727-250fe450293f)

![image](https://github.com/user-attachments/assets/8f226636-455d-4337-b980-eb261d02db93)

# Physical Security

- Preventative Control: prevents action (assume attacker has chosen to act)
- Detective Control: detect during, before and after (CCTV, alarms, etc.)
- Deterrent Control: deters action (assume attacker chosen not to act due to deterrent)
- Compensating Control: for controls that are too costly to implement)
- Administrative Control: (policies, compliance, procedures)

# Site selection

- Greenfield: not built on yet
- Topography: prone to flooding, fires, snow, etc.
- Utilities: think power reliability, internet area?
- Crime: crime rates, closest police stations, etc.

**Site Marking**

![image](https://github.com/user-attachments/assets/d214210a-d0f0-49ab-a38f-e3104478fbec)

![image](https://github.com/user-attachments/assets/b0493213-82db-41a9-ab44-69530cb9248e)

![image](https://github.com/user-attachments/assets/0c104a02-8efb-444d-8f12-c8610aa3a397)

# Media Storage

The media storage facility should be climate controlled at an offsite facility.
  - Tape will deteriorate at a certain temperature, just as disks will corrode at a certain humidity.
  - Data at Rest should always be encrypted.

# Asset tracking and hardware hardening

We need to keep an accurate inventory of all our assets. We should have it as part of our technology refresh cycle to record the Asset Serial Number, Model Number, and often an internal Asset ID.

- Hardware hardening
- Disabling USB ports
- Remove bloatware

![image](https://github.com/user-attachments/assets/6f1e264e-6584-4e21-9907-4cb2bf063222)

# Electricity

![image](https://github.com/user-attachments/assets/fbfd918d-a52c-4774-ba14-7c2570602434)

UPS - uninterruptible power supply, ensure power during outages
PDU - ensures correct levels of power is applied properly

![image](https://github.com/user-attachments/assets/fc226e27-31d9-4a89-acb9-8c704762c3a6)

- **Electromagnetic Interference (EMI)**:
Disturbance generated by an external source that affects an electrical circuit by electromagnetic induction, electrostatic coupling or conduction.
  - This is often an issue with network cables that are not shielded properly or run too closely to power cables. Crosstalk can occur (magnetism from one cable crosses over to a neighbor cable).
  - Integrity (data corruption) / Confidentiality (data sniffed) / Availability
  - Crosstalk is avoided by using STP cables (Shielded Twisted Pairs)
  - Power cables should never run close to copper cables.
  - Fiber Optic cables should be used if it makes sense (not susceptible to EMI since it's glass based)

> [!IMPORTANT]
> For the exam: Cheapest secure cables - FIBER beats COPPER. Assume in exam environment, that we have the money, we want full security, senior management is on top of things, etc.

# Fire suppression
**HVAC**

![image](https://github.com/user-attachments/assets/0285e19b-9c45-4377-925b-b5ed63acc8c2)

![image](https://github.com/user-attachments/assets/5aedb54a-e698-41eb-9476-2048a492d8cc)

### Detectors
- Heat Detectors
- Smoke Detectors
  - Ionization detectors have a small radioactive source which creates a small electric charge.
  - Photoelectric uses LED and a photoelectric sensor that produces a small charge while receiving light.
- Flame Detectors
  - detect infrared or ultraviolet light emitted by fire
  - they require line of sight of the fire though

![image](https://github.com/user-attachments/assets/cf1a3db5-6b80-4a12-ab66-f7090bf95645)

Removing oxygen from the room is the safest and cheapest option (Halon, FM200, Argon) to suppress a fire.

![image](https://github.com/user-attachments/assets/44206780-67f6-4d98-afcb-b5695392967d)

Water can also remove the 'heat' sector of the fire supression triangle, however:
- Water + Hardware = dead hardware
- Electricity should be cut before water is used.

### Sprinkler Systems

![image](https://github.com/user-attachments/assets/cf39aca0-e987-47c8-8f00-1a95bb28047e)
![image](https://github.com/user-attachments/assets/6643022c-511d-4c84-be33-b2cda9e6f596)

![image](https://github.com/user-attachments/assets/886b075d-2289-409a-9652-3322f1b4bfcb)

![image](https://github.com/user-attachments/assets/3fbe6e51-4a2c-48bd-8a5e-f25d3df1ca25)

![image](https://github.com/user-attachments/assets/b6a82598-007d-4561-8927-b1320e77a709)

![image](https://github.com/user-attachments/assets/d1603956-9891-4a2c-9a04-b4fdbd55e4a4)

![image](https://github.com/user-attachments/assets/405c9a04-6b86-410b-8276-e0d07e6382bb)

> [!TIP]
> Type A: (ASH) ordinary, solid combustibles such as in office
> Type B: (BARREL) flammable liquids and gas
> Type C: (CURRENT) electrical current like in data centers
> Type D: (DYNAMITE) combustible metals
> TYPE K: (KITCHEN) oils and fats that burn

![image](https://github.com/user-attachments/assets/a173e60e-2292-478d-b06a-b88462b3e7dc)

![image](https://github.com/user-attachments/assets/a7450eb2-44db-46bd-83ba-763e2376c70a)

# Personnel Safety

![image](https://github.com/user-attachments/assets/c533aee3-d619-4619-bd36-578deb0076fe)

![image](https://github.com/user-attachments/assets/d7e8ed64-8a4c-4282-8b2c-3812281856e6)

![image](https://github.com/user-attachments/assets/16a2a6b0-701b-4300-88ff-25c8569247e2)


