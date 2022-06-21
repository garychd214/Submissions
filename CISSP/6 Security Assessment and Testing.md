# Security Assessment and Testing
- Pen testing Rules of Engagement
- SSAE16 SOC Reports
- Information Security Continuous Monitoring (ISCM)

## ROE for Pentest
A Rules of Engagement document details the parameters and expected testing team conduct of thet/assessment/audit
- Target Environment
- Objective
- Scenario and Approach
- Level of knowledge
- Contraints
- Notifications
- Data handling requirements
- Reporting expectations

### Scenario and Approach
<img src = "Pics/CISSP ROE Scenario and Approach.jpg">

### Organizational Knowledge
1. Overt Testing
    - Informed: Management, Information Technology Personnel, Security Personnel, Third-party Personnel
    - Relationship: Cooperative
    - Advantages: More Efficient
    - Disavantages: Report may have less impact, Tendency to want to fix during the testing
2. Covert Testing
    - Informed: Limited Management
    - Relationship: Adversarial
    - Advantages: Valid test of incident detection and incident response capabilities
    - Disadvantage: May not get past barriers that an intruder with time and resources would

### Testing Team Knowledge
1. Zero
    - Testing team has not been provided any relevant information about the target environment
2. Partial
    - Testing team has been provided some relevant information about the target environment
3. Full
    - Testing team has intimate knowledge of the target environment
4. Hybrid
    - Two teams - Red team attacks and Blue teams defends


<br>
<br>

## Audit Examination Options
An audit examination provides assurance based on evidence and testing

- Auditing standards require that sufficient, relevant, and reliable evidence is obtained to support audit conclusions and opinion.
- An audit examination report can provide three types of opinions.
    - Unqualified
    - Qualified
    - Adverse
- An audit examination report can also include a disclaimer that the auditor was not able to render an opinion due to named circumstances
- Audit Standards and Framworks
    - ISACA COBIT 4.1 IT Controls and Assurance Objectives
        - Deliver and Support Domain
        - DS5 Ensure Systems Security (DS5.1~DS5.11)
    - AICPA Statement on standards for Attestation Engagements No. 16 (SSAE16)
        - Formally known as a SAS70
        - SSAE16 Service Organization Control Reports are internal control reports on the services provided by a service organization
            - Standard designed and maintained by the American Institute of Certified Public Accountants (AICPA)
- SOC Versions (Systems and Orgranization Controls)
    1. SOC1
        - Report of controls relevant to user entities financial statements
            - Agreed upon scope
        - No standard for what controls will be included
    2. SOC2 
        - Based upon Trust Services Principles (TSP) SOC 2 reports on controls intended to mitigate risk related to the security, availability, processing integrity, confidentiality, and privacy
            - Organization chooses categories but controls
            - Criteria provided by the AICPA
    3. SOC3
        - Same as SOC2 but does not detail testing performed and is designed for public distribution
    - SOC 2 and 3 Principles
    <img src = "Pics/CISSP SOC2_3 Principles.jpg">

- SOC Types
    1. Type 1
        - Reports on controls place in operation as of a point in time
        - Evaluation of design and implementation but not the operting effectivenss because it evaluate only at a point in time not the period of time
    2. Type 2
        - Reports on the design, implementation and operting effectiveness over a period of time (Generally, 6 or 12 months)
        - Includes tests of operating effectiveness and results
        - Emphasis on evidential matter 

<br>
<br>

## ISCM (Information Security Continuous Monitoring)
NIST SP-800-137 defines ISCM as Maintaining ongoing awareness of information security, vulnerabilities, and threats to support organizational risk management solutions

### Process
<img src = "Pics/CISSP ISCM Process.jpg" width = 400>

### Security Automation Domains
<img src = "Pics/CISSP ISCM Automation Domain.jpg" width = 400> 

### SCAP (Security Content Automation Protocol)
SCAP is a suite of specifications that standardizes the format and nomenclature by which security software products communicate security flaw and security configuration information.

### NVD (National Vulnerability Database)
NVD is the US Government repository of standards-based vulnerability management data represented using the SCAP specifications
    - This data enables automation of vulnerability management, security measurement, and compliance. It includes security checklists, security-related software flaws, misconfigurations, product names, and impact metrics 

### FISMA (Federal information Seucrity Management Act)
Federal agencies need to provide information security protections commensurate with the risk and magnitude of the harm resulting from unauthorized access, use, disclosure, disruption, modification, or destruction of: information collected/maintained by or on behalf of an agency.