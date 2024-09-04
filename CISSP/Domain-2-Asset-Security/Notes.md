### Overview
- [The Information Lifecycle](#the-information-lifecycle)
- [States of Data](#states-of-data)
- [Data Classification and Clearance](#data-classification-and-clearance)
- [Data Handling, Storage and Retention](#data-handling-storage-and-retention)
- [System Owners and Data Custodians](#system-owners-and-data-custodians)
- [Memory and Data Remanence](#memory-and-data-remanence)
- [Data Remanence and Destruction](#data-remanence-and-destruction)
- [Data Security Frameworks](#data-security-frameworks)
- [Data Protection](#data-protection)

# The Information Lifecycle
- Data Acquisition: information is either created or copied from another location.
- Data Use: How do we ensure the data is kept confidential, integrity is intact and available at need.
- Data Archival: Retention required by law or data will be used later.
- Data Disposal: How do we dispose properly of the data once it is no longer useful and required.

# States of Data
- Data at REST: stored data. (Full disk encryption)
- Data in MOTION: data transferred on a network. (Encrypt network traffic, both internal and external)
- Data in USE: actively using data. (No shoulder surfing, clean desk policy, print policy, locking screens)

# Data Classification and Clearance
![image](https://github.com/user-attachments/assets/f308741c-5cee-4e9e-8083-d91b07fdb453)

> [!IMPORTANT]
> Just because it is unclassified, it doesn't mean it is publicly available!

![image](https://github.com/user-attachments/assets/d222a140-7819-4fa9-b4aa-453d3e4a56f0)

- **Formal Access Approval**: Document from the data owner approving access to the data for the subject - subject must understand all requirements for accessing the data and the liability involved if compromised, lost or destroyed.
Just because you have access, does not mean you are allowed the data.

# Data Handling, Storage and Retention
- Data Handling: Trusted individuals should handle our data. Logs should be in place to show these metrics.
- Data Storage: Where do we keep sensitive data? Kept in secure, climate-controlled facility preferably geographically distant.
- Data Retention: Should not be kept beyond the period of usefulness or beyond legal requirements.
![image](https://github.com/user-attachments/assets/a38c49de-c5d7-4390-8835-cc73d80f6016)

# System Owners and Data Custodians
- Business owners: senior executives
- Data/Information owners: Management level - they assign sensitivity labels and backup frequency
- Data custodians: Technical hands-on employees who DO the backups, patches and configurations
- System Owner: Management level - like a data center manager or infrastructure manager
- Data controllers/processors: HR/Payroll

# Memory and Data Remanence
Data remanence: data left over after normal removal and deltion of data.

![image](https://github.com/user-attachments/assets/fe4bbc87-a942-46cf-a2f3-b7e59ae24a8e)

![image](https://github.com/user-attachments/assets/6e315aee-bc75-46b4-aecf-312a1b1c8f28)

![image](https://github.com/user-attachments/assets/df4ff727-0e2e-4e45-99c4-8bee4e456648)

# Data Remanence and Destruction

![image](https://github.com/user-attachments/assets/ee4b5824-78da-4c41-884f-5d327c155925)

![image](https://github.com/user-attachments/assets/76e3dffb-6a86-4e54-9bc2-3d6983bb2a07)

# Data Security Frameworks
- Scoping: determine which portion of a standard should be deployed in the organization.
- Tailoring: customizing a standard to our organization.
- Certification: A system and the security measures on it, meet the security requirements set by regulation/laws.
- Accreditation: The data owner accepts the certification and residual risk. This is required before the system can be put into production.

# Data Protection
- Digital Rights Management (DRM): using technology and systems to protect copyrighted digital media.
  - Encryption
  - Limited Permissions management
  - Persistent authentication and audit trails
  - Tracking: watermarks or meta data embedded in files
- Cloud Access Security Broker (CASB): on-premise or cloud software between users and cloud apps.
- Data Loss Prevention (DLP)
  - Loss vs Leak: With leak, both internal and hackers know about the information.
  - Network DLP for data in motion and Endpoint DLP for data in use and rest.
