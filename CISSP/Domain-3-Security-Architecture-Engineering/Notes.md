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
# Secure design principles
# Secure system design concepts
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
