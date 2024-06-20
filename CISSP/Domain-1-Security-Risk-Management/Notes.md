### Overview
- [CIA Triad](#cia-triad)
- [DAD Triad](#opposing-dad-triad)
- [IAAA](#iaaa)
- [Governance vs Management](#governance-vs-management)
- [Governance: Standards and Control Frameworks](#governance-standards-and-control-frameworks)
- [Laws and Regulations](#laws-and-regulations)

# CIA Triad
- **Confidentiality**: Ensuring no unauthorized user can access the data.
- **Integrity**: Ensuring the data in rest/motion/used has not been altered or modified.
- **Availability**: Ensuring that authorized people can access the data that they need, when they need.
# Opposing DAD Triad
- **Disclosure**: Someone unauthorized gaining access to information they shouldn't.
- **Alteration**: Data in rest/motion/used being changed.
- **Destruction**: Data or systems have been destroyed or rendered inaccessible.

Finding the right mix of CIA is a balancing act since:
- Excessive Confidentiality may cause Availability to suffer.
- Excessive Integrity may cause Availability to suffer.
- Excessive Availability may cause both Confidentiality and Integrity to suffer.

# IAAA
- **Identification**
- **Authentication**: KNOW, HAVE, ARE
- **Authorization**: What access are you authorized to have?
- **Accountability**: tracing an action to a subject's identity - also known as non-repudiation.

**Least-Privilege**: Minimum necessary access // Need-To-Know

# Governance vs Management
![image](https://github.com/0xScorpio/Certifications/assets/140411254/7742d50d-698e-4cdb-ac5a-e79e4f9157b9)

Bottom-up vs Top-Down (exam) -> C-Level Executives are **ULTIMATELY LIABLE**.

# Governance: Standards and Control Frameworks
- PCI-DSS: Payment Card Industry Data Security Standard - debit, credit cards
- OCTAVE: Operationally Critical Threat, Asset and Vulnerability Evaluation - self directed risk management
- COBIT: Control Objectives for Information and related Technology - Goals for IT, stakeholder needs mapped to IT-related goals
- COSO: Committee Of Sponsoring Organizations - Goals for entire organization
- ITIL: Information Technology Infrastructure Library - IT Service Management
- FRAP: Facilitated Risk Analysis Process - analyze a specific application/system with internal employees and prioritize.
- ISO 27000 series:
  - ISO 27001: Establish, implement, control and improvement of ISMS. (PLAN, DO, CHECK, ACT)
  - ISO 27002: Practical advice on how to implement security controls. Uses 10 domains for ISMS.
  - ISO 27004: Provides metrics for measuring the success of your ISMS.
  - ISO 27005: Standards-based approach to risk management.
  - ISO 27799: Directives on how to protect PHI (Protected Health Information).

# Laws and Regulations
- Criminal Law
  - SOCIETY is the victim and proof is BEYOND A REASONABLE DOUBT.
  - Incarceration, death and financial fines to PUNISH/DETER.
- Civil/Tort Law
  - INDIVIDUALS/ORGANIZATIONS are the victim and proof is the MAJORITY OF PROOF.
  - Financial fines to compensate the victim(s).
- Administrative Law
  - Laws enacted by government agencies (FDA, HIPAA, FAA, etc.)
- Private Regulations
  - Compliance is required by contract (PCI-DSS, etc.)
- Customary Law
- Religious Law

Due Diligence: research, plan
Due Care: action, do

Negligence: opposite of Due Care.
If a system under your control is compromised and you can prove you did your Due Care, you are most likely not liable.
