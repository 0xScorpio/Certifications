### Overview
- [CIA Triad](#cia-triad)
- [DAD Triad](#opposing-dad-triad)
- [IAAA](#iaaa)
- [Governance vs Management](#governance-vs-management)
- [Governance: Standards and Control Frameworks](#governance-standards-and-control-frameworks)
- [Laws and Regulations](#laws-and-regulations)
- [International Agreements and Guidelines](#international-agreements-and-guidelines)
- [Third-Party, Acquisitions and Divesture Security](#third-party-acquisitions-and-divesture-security)

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

> [!NOTE]
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

> [!NOTE]
Due Diligence: Research, Plan

> [!NOTE]
Due Care: Action, Do

> [!NOTE]
Negligence: opposite of Due Care.
If a system under your control is compromised and you can prove you did your Due Care, you are most likely not liable.

# Evidence
Types of evidence:
- Real Evidence: tangible and physical (hard disks, NOT the data in them)
- Direct Evidence: testimony from a first-hand witness / experiences with all 5 senses
- Circumstantial Evidence: evidence that supports circumstance or other evidence
- Corroborative Evidence: evidence that supports facts or elements of the case

Definitions
- Hearsay: Not first-hand knowledge - normally inadmissible in a case.
- Best Evidence Rule: accurate, complete, relevant, authentic and convincing.
- Secondary Evidence: suchs as logs and documents from systems.
- Evidence Integrity: Hashes, any forensics is done on copies and NEVER on original.
- Chain of Custody: proves the integrity of the data
  - WHO handled it?
  - WHEN did they handle it?
  - WHAT did they do with it?
  - WHERE did they handle it?

Reasonable Searches:
- The 4th Amendment on the US Constitution protects citizens from unreasonable search and seizure by the government.
- The court will determine if evidence was obtained legally.
- Exceptions apply if there is an immediate threat to human life or of evidence destruction.

Entrapment: (illegal and unethical) when someone is persuaded to commit a crime they had no intention of committing and is then charged for it.

Enticement: (legal and ethical) makiing committing a crime more enticing, but the person has already broken the law or at least decided to do so. e.g. Honeypots.

# Intellectual Property
- Copyright:
  - Automatically granted and lasts 70 years after creator's death or 95 years after creation by/for corporations.
- Trademarks:
  - Brand names, logos, slogans - valid for 10 years at a time, can be renewed indefinitely. 
- Patents:
  - Protects inventions for 20 years (normally)
    - Cryptography algorithms can be patented. Inventions must be:
      - Novel: new
      - Useful: possible to use and useful
      - Nonobvious: inventive work involved
- Trade Secrets

## Attacks on Intellectual Property
Copyright:
- Piracy
- Copyright infringement

Trademarks:
- Counterfeiting

Patents:
- Patent infringement

Trade Secrets:
While an organization can do nothing if their Trade Secret is discovered, HOW it is done can be illegal.
- Cyber Squatting: Buying a URL you know someone else will need (gray area legal)
- Typo Squatting: Buying a URL that is very close to real website name (can be illegal)

# US Rules, Regulations and Laws
- **HIPAA: Health Insurance Portability and Accountability Act.**
  - Strict privacy and security rules on handling PHI (Protected Health Information)
> [!NOTE]
> PRIVACY, SECURITY and BREACH NOTIFICATION rule.
- Security Breach Notification Laws
  - NOT Federal, all 50 states have individual laws.
- **ECPA: Electronic Communications Privacy Act**
  - Protection of electronic communications against warrantless wiretapping.
  - This act was weakened by the Patriot Act.
- **PATRIOT Act of 2001**:
  - Expands law enforcement electronic monitoring capabilities.
  - Allows search and seizure without immediate disclosure.
  - Allows ISPs to voluntarily share information of their users to law enforcement.
  - Eases the restrictions of foreign intelligence gathering within the US.
- **CFAA: Computer Fraud and Abuse Act, Title 18 Section 1030**
  - Used to prosecute computer crimes.
- **GLBA: Gramm-Leach-Bliley Act**
  - Applies to financial institutions: driven by the Federal Financial Institutions.
- **SOX: Sarbanes-Oxley Act of 2002**
  - Directly related to the accounting scandals in the late 90s.
- **PCI-DSS: Payment Card Industry Data Security Standard**
  - The standard applies to carholder data for both credit and debit cards.
 
# GDPR (General Data Protection Regulation)
- Data protection and privacy for all individuals within the EU and EEA.
- It does NOT matter where we are based / if we have clients in EU, we have to adhere to GDPR.
- Violators of the GDPR may be fined up to 20 million euros or up to 4% of the annual worldwide turnover of the preceding financial year in case of an enterprise, WHICHEVER IS GREATER!

**Restrictions**: Lawful interception, national security, military, police or the justice system.
  
**Right to access**: Data controllers must be able to provide a free copy of an individual's data if requested.

**Right to erasure**: All users have a 'right to be forgotten'.

**Data portability**: All users will be able to request access to their data 'in an electronic format'.

**Data breach notification**: Users/Data controllers must be notified of data breaches within 72 hours.

**Privacy by design**: Ensure data processes are secure and that are 'absolutely necessary for the completion of duties'.

**Data Protection Officers**: Companies whose activities involve data processing and monitoring MUST APPOINT a Data Protection Officer.

> [!WARNING]
> REMINDER TO DO SOME EXTRA RESEARCH FOR CONTEXT AND UNDERSTANDING!
> 
# Legacy laws between EU and US
- **EU Data Protection Directive**
- **EU-US Safe Harbor**
- **Privacy Shield**

# International Agreements and Guidelines
## Organization for Economic Cooperation and Development (OECD) Privacy Guidelines
- 30 member nations around the world, including the US.
- Guidelines on the protection of privacy and transborder flows of personal data - issued in 1980.

Eight Driving Principles (aligns with GDPR):
1. Collection limitation principle
2. Data quality principle
3. Purpose specification principle - purpose of collecting data
4. Use limitation principle - only with conset of subject can data be disclosed
5. Security safeguards principle - safeguards in place to protect data from general loss or unauthorized access
6. Openness principle - any practices to personal data needs to be communicated properly
7. Individual participation principle - which organizations have the subject's data
8. Accountability principle - organizations are held accountable to comply in the other 7 principles

## Wassenaar Arrangement
Export/Import controls for Conventional Arms and **Dual-Use** Goods and Technologies
- 41 countries are a part of the arrangement
- Cryptography is considered **Dual-Use**:
  - Iran, Iraq, China, Russia and others have import restrictions on strong cryptography.
  - If it is too strong, it can't be broken; governments want to be able to spy on their citizens.
  - Companies have to make "country-specific" products with different encryption standards.

![image](https://github.com/user-attachments/assets/5f6455f6-00d0-47c7-8f11-5511e5da6c41)

![image](https://github.com/user-attachments/assets/24d1c1b7-34da-40a8-8a23-5a40c025294e)

# Third-Party, Acquisitions and Divesture Security
test
  
  

  
