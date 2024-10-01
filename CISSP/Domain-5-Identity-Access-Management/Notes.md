> [!IMPORTANT]
**OBJECTIVE**:
>
> How we identify our assets, the platforms we use for them, how we provide authorized access and prevent unauthorized access to the assets and the asset/identity lifecycle.


**CONTENT**:
- [Access Control](#access-control)  
- [Authorization](#authorization)
- [Accountability](#accountability)
- [Access Control Systems](#access-control-systems)
- [Service Account Management](#service-account-management)
- [Identity and Access provisioning](#identity-and-access-provisioning)
- [Authentication Protocols](#authentication-protocols)

# Access Control
This is determined by our policies, procedures and standards.
NEVER USE group logins/accounts as they have no accountability.
#### IAAA
- Identification: name, username, ID, SSN, etc.
- Authentication: (MFA)
  - Type 1: Something you know (knowledge factors)
  - Type 2: Something you have (possession factors)
  - Type 3: Something you are (biometrics)
  

#### Mitigations:
**Key Stretching**: Adding 1-2 seconds to password verification - effectively making a bruteforce attack unfeasible!
- **Bruteforce**: limit number of wrong logins
- **Dictionary attacks**: limit number of wrong logins and blacklist dictionary words
- **Rainbow tables**: limit number of wrong logins and salt the password before hashing
- **Nonce**: number once - random pseudo-number issued during authentication protocols to ensure old communications/sessions cannot be used in replay attacks!
- **Clipping levels**: to prevent administrative overhead - allows authorized users to get extra tries during password failures. Clipping levels are thresholds of acceptable user errors and suspicious activities. If this threshold is exceeded, it must be logged and the administrator must decide if any malicious activity is taking place or if the user needs some training.

![image](https://github.com/user-attachments/assets/8c3825e2-4ed5-4079-96d5-d8b0407c2a19)

![image](https://github.com/user-attachments/assets/376251b0-17c1-4500-84d2-fee0d4a2b61a)

# Authorization
For authorization, access control models will determine what a subject is allowed to access.

- **Confidentiality**: Mandatory Access Control (centrally managed model, objects assigned labels / subjects assigned clearance)
- **Integrity**: RBAC or ABAC (least privilege)
- **Availability**: Discretionary Access Control (decentralized management using ACLs)

> [!NOTE]
> ABAC is much more secure than RBAC due to how much more granular the security is!
> Also known as PBAC (policy-based) or CBAC (claims-based)

- **Context-Based Access Control**: location, time, providing user/pass with CAPTCHA, filtering based on MAC address, etc.
- **Content-Based Access Control**: hiding/showing menus in an app, views in database - access to confidential information are all content-dependent.
  
# Accountability
Also referred to auditing and non-repudiation.
Centralized logs backed up.

# Access Control Systems
In a perfect world, access control systems should be physically and logically segmented from the rest of our IP networks.

### Centralized Access Control Systems
- All systems/locations have the same security posture.
- Easier to manage,
- Only a few people have access and the privilege to make changes.
- Provides separation of duties.
- SSO can be used for user access to multiple systems.

### De-Centralized Access Control Systems
- Traffic overhead and response time, takes longer to authenticate.
- Connectivity to the head office must be stable enough.

### Hybrid
- centrally-controlled; ACLs for that location are pushed to a local server on a daily basis / local admins have no access to that.
- local site still needs to follow organization's secuirty policies throughout.

### Just-In-Time
- allows us to use 3rd party websites without checking if all our employees have accounts on those sites
- users log in 3rd party site, JIT confirms employee withour systems and creates user account on their systems, using SAML.

### OpenID Connect (OIDC) / Open Authorization
- Adds an identity layer to OAuth2.0, allowing 3rd party apps/sites to verify identity of user.
- e.g. You can use Google/Facebook accounts to log into other sites.

### Risk-Based Access Control
- Access decisions are made based on risk assessment.
- Done using machine learning, which analyzes behavioral and contextual data analytics to calculate risk for each access.

# Service Account Management

### Policy Decision Points (PDP)
Determines access permissions based on security policies

### Policy Enforcement Points (PEP)
Executes access decisions, enforcing security policies

# Identity and Access provisioning
We can have multiple identities per entity and each identity can have multiple attributes.

![image](https://github.com/user-attachments/assets/8436e494-ff45-4552-a4bd-5805b8c81ae0)

![image](https://github.com/user-attachments/assets/ad235d12-5f9b-4049-9f07-ea48e1a9a673)

![image](https://github.com/user-attachments/assets/12fbeb17-d131-4e15-8c2e-4baaa501f692)

# Authentication Protocols
- Kerberos (port 88)
- 
![image](https://github.com/user-attachments/assets/2a1d8051-9534-438c-bfb7-1af9d3e7e275)

- SESAME (Secure European System for Applications in a Multi-vendor Environment)
Addresses some of the issues of Kerberos - uses asymmetric PKI to fix Kerberos plaintext storage of symmetric keys.
Uses a PAS (Privilege Attribute Server) which issues PACs (Privilage Attribute Certificates) instead of Kerberos tickets. Not widely used, since Kerberos is natively in most OS's.

- RADIUS (Remote Authentication Dial-In User Service)
  - networking protocol that provides centralized AAA management for users connecting to a network service.
  - UDP port 1812 fopr authentication
  - UDP port 1813 for accounting
  - can use TCP with TLS for security
![image](https://github.com/user-attachments/assets/cdec2ee0-a6e8-4f64-8fb0-6f2d6d9531f6)

- Diameter
  - intended as a replacement to RADIUS
  - used in 3G/4G/5G space
  - uses 32bit for the AVP field
  - SCTP(Stream Control Transmission Protocol) for TCP as default

- TACACS (Terminal Access Controller Access Control System)
  - centralized access control system requiring users to send an ID and reusable password for authentication
  - TCP/UDP port 49
  - Generally replaced by TACACS+ and RADIUS

- TACACS+
  - Provides better password protection using 2FA
  - Not backwards compatible with TACACS
  - TCP port 49 for authentication
  - Similar to RADIUS, but RADIUS only encrypt the password / TACACS+ encrypts the entire data package

- PAP (Password Authentication Protocol)
  - no longer secure (credentials are sent over the network in plaintext)
  - authentication is initialized by client sending packet with creds ate the beginning of the connection

- CHAP (Challenge-Handshake Authentication Protocol)
  - Provides protection against replay attacks through incrementally changing identifiers and of a variable challenge value.
  - Requires the client/server to know the plaintext of a shared secret - never sent over the network.
  - Ongoing authentication requests from the server to the client continue on a regular basis after the initial handshake, which means the identifiers must change with every new authentication.
  - CHAP server stores plaintext passwords of each client [VULNERABILITY]

  ![image](https://github.com/user-attachments/assets/027e2b87-f8cd-47dc-b2a7-38a66bcdf8b3)

