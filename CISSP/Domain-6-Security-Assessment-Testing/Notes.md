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

