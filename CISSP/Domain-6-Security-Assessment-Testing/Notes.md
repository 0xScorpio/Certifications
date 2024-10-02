## Overview
- [Security Assessments](#security-assessments)
- [Security Audits](#security-audits)
- [Security Audit Logs](#security-audit-logs)
- [Audit Strategies for Cloud or Hybrid environments](#audit-strategies-for-cloud-or-hybrid-environments)

# Security Assessments
A full picture approach to assessing how effective our access controls are. Security assessments often span multiple areas and can use some or all of these components:
- Policies, procedures and other administrative controls.
- Change management
- Architectural review
- Penetration Tests
- Vulnerability assessments
- Security Audits

# Security Audits
A test against a published standard, for example: SOC 2 Type 1 or 2, PCI-DSS, HIPAA...
- Unstructured (Internal) Audits: internal company auditors
- External Audits: external company audit
- Structured Audits (3rd party): external company audit backed by some regulatory body and added credibility.

![image](https://github.com/0xScorpio/Certifications/assets/140411254/aa53b6a7-ffc8-4b47-b1f5-c28a4b25b342)

## SOC1
Focuses on service organization controls relevant to **internal control over financial reporting**.
- Type 1: Opinion on **design effectiveness** of controls - covers a **single point in time**.
- Type 2: Opinion on **design and reporting effectiveness** of controls - covers a **minimum 6-month time period**.

## SOC2
Assess internal controls for **compliance and operations**.
- Must meet **trust service criteria** defined by AICPA: **Security, Availability, Processing Integrity, Confidentiality and Privacy**.
- SOC2 reports are available to management and others under a strict NDA.
- Type 1: Report on management's description of a service organization's system and the **suitability** of the design of controls - covers a **single point in time**.
- Type 2: Report on maangement's description of a service orgnization's system and the **suitability** of the design and operating **effectiveness** of controls - covers a **minimum 6-month time perdiod**.
  - The purpose of type 2 reports is to validate/verify that an organization meets the requirements as stated in the published standard.
  - Proves that the organization controls listed are operational and enforced.
  - Better and more expensive than Type 1 reports.

## SOC3
Similar to SOC2 reports but much more generalized, shorter and a less sensitive document.
- Public facing document
- Includes ONLY the **auditor's** opinion and limited description of controls.
- Covers both design and operating effectiveness of the controls relevant to applicable trust service principles (security availability, processing integrity, confidentiality and privacy)

# Security Audit Logs
Reviewing security audit logs in an IT system is one of the easiest ways to verify that access control mechanisms are working as intended - primarily a **detective control**.
> [!NOTE]
> **NIST Special Publication 800-92** suggests the following log types should be collected and audited:
> - **Network Security Software/Hardware**:
>   - AV logs, IDS/IPS logs, remote access software (VPNs), web proxy, vulnerability management, authentication servers, routers and firewalls.
> - **Operating System**:
>   - System events, audit records, applications, client requests and server responses, usage information, significant operational actions.

We want to retain logs based on the standard we're following or based on usefulness - whichever is GREATER.

> [!IMPORTANT]
> Never touch the ACTUAL logs. Instead, hash them.
> Take a bit-level copy and check that the bit-level copy is the exact match as the original hash.
> Then work on the copy, and once done with digital forensics, re-check the hashes to ensure no changes have been made.

## Audit Trail
Audit record management typically faces 5 distinct problems:
1. Logs are not reviewed on a regular and timely basis.
2. Audit logs and audit trails are not stored for a long enough time period.
3. Logs are not standardized or viewable by correlation toolsets - they are only viewable from the system being audited.
4. Log entries and alerts are not prioritized.
5. Audit records are only review once an incident occurs.

# Audit Strategies for Cloud or Hybrid environments
- Data sovereignty: where our data can be stored and processed based on laws we have to follow.
- Shared Responsibility Model: The cloud service provider and customer would be responsibly for different aspects.
  - IaaS: customer responsible for OS, applications and data.
  - PaaS: CSP responsible for OS, middleware, hardware.
  - SaaS: CSP is responsible for everything except data and sometimes access control.

## Hybrid environments
Best practices:
- Have clear objectives and scope.
- Manual testing is important.
- Review policies, procedures and documentation.
- Engage the right stakeholders.
- Track and remediate audit findings and reassess progress.

# Penetration Testing stuff
- War Dialing: Uses a modem to dial a series of phone numbers, looking for an answering modem carrier tone, the pentester then attempts to access the answering system.
- War Driving (AP mapping)
- Network attacks
- Wireless tests
- Exception Handling
- Ethical Disclosure

# Software Testing
- SAST: passively testing code when it is not running.
- DAST: actively testing code when it is running.

![image](https://github.com/user-attachments/assets/9f5a187b-923f-471f-8c53-f85b42c9b62a)

### Software Testing Levels
- **Unit Testing**:
  - tests that verify the functionality of a specific section of the code.
  - in an object-oriented environment, this is usually at a class level / minimal unit tests include constructors and destructors.
- **Integration Testing**:
  - tests that verify the interfaces between components against a software design.
- **Component Interface Testing**:
  - tests a completely integrated system to verify that the system meets its requirements
- **Operational Acceptance**:
  - used to conduct operational readiness of a product (pre-release)
- **Installation Testing**:
  - assures the system is installed correctly and working at actual customer's hardware.
- **Regression Testing**:
  - Finding defects after a major code change has occurred.
  - Looks for software regressions, as degraded or lost features, including old bugs that may have come back.
- **Fuzz Testing**:
  - testing with different inpputs to cause unauthorized access or unpredictable states of an application.
  - if the program crashes/hangs, fuzz test has failed.
  - mutating fuzzing; tester analyzes real info and modifies it iteratively.
- **All-Pairs Testing (Pairwise Testing)**:
  - black-box technique in which test cases are designed to execute all possible discrete combinations of each pair of input parameters.

![image](https://github.com/user-attachments/assets/96e2cff4-913d-4751-b2d1-6c7bca8c1c80)

- **Misuse Case Testing**:
  - executing malicious attacks against a system that normal users wouldn't do
- **Test Coverage Analysis**:
  - identifies how much of the code was tested in relation to the entire application.
  - in massive environments, we spot check only the critical areas.
 
  

