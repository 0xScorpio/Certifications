> [!IMPORTANT]
**OBJECTIVE**:
>
> How we identify our assets, the platforms we use for them, how we provide authorized access and prevent unauthorized access to the assets and the asset/identity lifecycle.

> [!NOTE]
> **CONTENT**:
> 
> [Access Control](#access-control)  
> [Authorization](#authorization)
> [Accountability](#accountability)
> [Access Control Systems](#access-control-systems)
> [Service Account Management](#service-account-management)
> [Identity and Access provisioning](#identity-and-access-provisioning)
> [Authentication Protocols](#authentication-protocols)

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


# Service Account Management
# Identity and Access provisioning
# Authentication Protocols

