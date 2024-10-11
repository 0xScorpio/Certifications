## Content
- [Designing security in our software](#designing-security-in-our-software)
- [Programming concepts](#programming-concepts)
- [Software development methodologies](#software-development-methodologies)
- [DevOps and DevSecOps](#devops-and-devsecops)
- [Scaled Agile Frameworks](#scaled-agile-frameworks)
- [Databases](#databases)
- [OWASP](#owasp)
- [Software Vulnerabilities, Attacks and Mitigations](#software-vulnerabilities-attacks-and-mitigations)
- [Maturity Models](#maturity-models)
- [Buying software from other companies](#buying-software-from-other-companies)
- [Software Composition Analysis](#software-composition-analysis)
- [Artificial Intelligence](#artificial-intelligence)

 # Designing security in our software

- **SDS (Software-Defined Security**
  - security functions are removed from the hardware and become virtual network functions (VNFs) instead.
  - SDS is software-managed, thus policy-driven and governed security where most controls are automated and monitored by software.

- **Auditing/Logging of Changes**
  - need to be clear with change/configuration management

- **Risk Analysis & Mitigation**
  - Identify, Analyze, Mitigate
 
 # Programming concepts
- Machine Code
- Source Code
- Assembler Languages
- Compiler Languages
- Interpreted Languages: similar to compiler but interprets code each time it is run into machine code.
- Bytecode: interpreted code, in intermediary form, converted from source, but still needs to convert to machine code before it can run on the CPU.
- Procedural Languages: uses subroutines, procedures and functions.
- Object-Oriented Programming

![image](https://github.com/user-attachments/assets/151f705e-3ace-4f8b-a5cd-5f3fd66734ab)

- CASE (Computer-Aided Software Engineering)
  - similar, inspired by CAD tools for hardware
  - used to develop high-quality defect-free and maintainable software
  - CASE software is classified into 3 categories:
    - **Tools** support specific tasks in the software lifecycle.
    - **Workbenches** combine 2 or more tools focused on a specific part of the software lifecycle.
    - **Environments** combine 2 or more tools or workbenches and support the complete software lifecycle.

 - **Top-Down Programming**
   - Starts with the big picture, then breaks it down into smaller segments.
   - Each subsystem in the overview, is then refined in greater detail, sometimes with additional subsystems.
   - Procedural programming leans towards Top-Down, you start with one function and add to it.
     
 - **Bottom-Up Programming**
   - Piecing together of systems to build more complex systems. The individual base systems are specified in great detail, then linnked together to form a larger subsystem, until a complete top-level system is formed.
   - OOP tends to lean toward Bottom-Up; start by developing your objects and then build up.

- **Open-Source**: public and free release of source code and software.
- **Closed Source**: software released to public, private source code, security through obscurity.
- **Proprietary Software**: software protected by IP/patents. Can be both Open or Closed source. Any software not released to public is protected by copyright.

**SOFTWARE RELEASE**

- 3 types of free software:
  - **Freeware**: free software, free of charge to use.
  - **Shareware**: fully functional proprietary software initially free to use. Trials to test, after 30 days, pay to continue use.
  - **Crippleware**: Partially functioning proprietary software, key features disabled. Payment required to unlock full functionality.
 
 - **EULA (End-User License Agreements)**: Electronic form where the user agrees to software terms/conditions while installing software.

**SOFTWARE LICENSES**

Open source software can be protected by a variety of licensing agreements:
- **GNU (General Public License or GPL)**
  - guarantees end users the freedom to run, share and modify the software.
  - copyleft license: which means the derivative work can only be distributed under the same license terms.
 
- **BSD (Berkeley Software Distribution)**
  - family of permissive free software licenses, imposing minimal restrictions on the use and redistribution of covered software.
  - different that copyleft, which have reciprocity share-alike requirements.
 
- **Apache**
  - software must be free and free to distribute modifications of software.
  - requires preservation of the copyright notice and disclaimer.

![image](https://github.com/user-attachments/assets/e624b9be-4cfe-4a1f-9bb8-224fa89aebcd)

 # Software development methodologies

In the past, the Waterfall methodology was widely used, however it was a very linear process and does not work well with the iterative nature of software development. To remedy this issue, other methodologies were developed such as Spiral, Sashimi, Agile and Scrum,

- **Waterfall**
  - Very linear, each phase leads directly into the next.
  - Unmodified waterfall model does not allow us to go back top a previous phase. Modified waterfall allows us to go ONE step back.
  - System/Software requirements -> Design -> Implementation -> Testing -> Maintenance

- **Sashimi**
  - Similar to waterfall, but we always have 2 overlapping phases.
  - This is a modified waterfall that allows us to go back to the previous phase, but NOT further!
 
## Agile

A set of values/principles for software development under which requirements and solutions evolve through the collaborative effort of self-organizing cross-functional teams.

![image](https://github.com/user-attachments/assets/afa64b92-145a-4f1e-9870-6f59d6b2c255)

- **Scrum**
  - Designed for small teams; 10 people
  - Relies on two-week development cycles called 'sprints'
  - short daily stand-up meetings
  - **3 Core Roles**:
    - **Product Owner**: represents the stakeholders, voice of customer, accountable for ensuring team delivers value.
    - **Development Team**: responsible for delivering product at each sprint. Cross-functional team of 3-9 individuals.
    - **Scrum Master**: acts as a buffer between the team and distracting influences. Follows the Scrum framework.

- **XP (Extreme Programming)**
  - intended to improve software quality and responsiveness to changing customer requirements.
  - advocates frequent releases in short dev cycles to improve productivity, and checkpoints for new, changing customer requirements if needed.
  - pair programming, extensive code review.
  - unit tests on all code.
  - avoid features until they are needed.
  - flat management structure.
  - simple/clear code.
  - frequent communication with the customer.
 
- **Spiral Model**
  - Risk-driven process model generator for software projects.
  - It has 4 phases:
    - Planning
    - Risk Analysis
    - Engineering
    - Evaluation
  - A software project repeatedly passes through these phases in iterations (spirals)
  - Each subsequent spiral builds on the baseline spiral.

- **RAD (Rapid Application Development)**
  - emphasis on adaptability and adjusting requirements in response to knowledge gained as the project progresses.
  - Prototypes are often used in place of design specifications.
  - suited for developing software that is driven by UI requirements.
 
- **Prototyping**
  - high level of customer involvement
  - creation of multiple prototypes with limited functionality

 ![image](https://github.com/user-attachments/assets/1d374587-b5b3-467c-b56c-d161d0d65a3b)

 # DevOps and DevSecOps
 # Scaled Agile Frameworks
 # Databases
 # OWASP
 # Software Vulnerabilities, Attacks and Mitigations
 # Maturity Models
 # Buying software from other companies
 # Software Composition Analysis
 # Artificial Intelligence
