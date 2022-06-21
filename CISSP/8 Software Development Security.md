# Software Development Security
- Evaluating Source Code Flaws
- Software DEvelopment processes
- Surveying Software Testing
- Deconstructing the Product Development Lifecycle

## Source Code Flaws
Design flaws, inadequate code review, and poor configuration management contribute to source code security issues

### OWASP
https://owasp.org/Top10/

1. Broken Access Control
    - the contributed data indicates that on average, 3.81% of applications tested had one or more Common Weakness Enumerations (CWEs) with more than 318k occurrences of CWEs in this risk category. The 34 CWEs mapped to Broken Access Control had more occurrences in applications than any other category.
2. Cryptographic Failures, previously known as A3:2017-Sensitive Data Exposure
    - which was broad symptom rather than a root cause. The renewed name focuses on failures related to cryptography as it has been implicitly before. This category often leads to sensitive data exposure or system compromise.
3. Injection slides 
    - 94% of the applications were tested for some form of injection with a max incidence rate of 19%, an average incidence rate of 3.37%, and the 33 CWEs mapped into this category have the second most occurrences in applications with 274k occurrences. Cross-site Scripting is now part of this category in this edition.
4. Insecure Design with a focus on risks related to design flaws. 
    - If we genuinely want to "move left" as an industry, we need more threat modeling, secure design patterns and principles, and reference architectures. An insecure design cannot be fixed by a perfect implementation as by definition, needed security controls were never created to defend against specific attacks.
5. Security Misconfiguration 
    - 90% of applications were tested for some form of misconfiguration, with an average incidence rate of 4.5%, and over 208k occurrences of CWEs mapped to this risk category. With more shifts into highly configurable software, it's not surprising to see this category move up. The former category for A4:2017-XML External Entities (XXE) is now part of this risk category.
6. Vulnerable and Outdated Components was previously titled Using Components with Known Vulnerabilities
    - This category moves up from #9 in 2017 and is a known issue that we struggle to test and assess risk. It is the only category not to have any Common Vulnerability and Exposures (CVEs) mapped to the included CWEs, so a default exploit and impact weights of 5.0 are factored into their scores.
7. Identification and Authentication Failures was previously Broken Authentication and now includes CWEs that are more related to identification failures. 
    -This category is still an integral part of the Top 10, but the increased availability of standardized frameworks seems to be helping.
8. Software and Data Integrity Failures
    - focusing on making assumptions related to software updates, critical data, and CI/CD pipelines without verifying integrity. One of the highest weighted impacts from Common Vulnerability and Exposures/Common Vulnerability Scoring System (CVE/CVSS) data mapped to the 10 CWEs in this category. A8:2017-Insecure Deserialization is now a part of this larger category.
9. Security Logging and Monitoring Failures was previously A10:2017-Insufficient Logging & Monitoring 
    - This category is expanded to include more types of failures, is challenging to test for, and isn't well represented in the CVE/CVSS data. However, failures in this category can directly impact visibility, incident alerting, and forensics.
10. Server-Side Request Forgery 
    - The data shows a relatively low incidence rate with above average testing coverage, along with above-average ratings for Exploit and Impact potential. This category represents the scenario where the security community members are telling us this is important, even though it's not illustrated in the data at this time.

### Other attacks to memorize
<img src = "Pics/CISSP Other Attacks.jpg" width = 800>

<br>
<br>

## Software Development Models
### Project Development Models
<img src = "Pics/CISSP Project Development Models.jpg" width = 700>

### Integrated Processes
<img src = "Pics/CISSP Integrated Process.jpg" width = 700>

### Testing Modes
- Unit testing
    - Testing of small discrete chunks of codes
- Integration testing
    - Testing multiple units of code to ensure that the proper information flows between them
- Validation testing
    - Testing to verify that the product meets the design specifications
- Vulnerability testing
    - Testing for security vulnerabilities
- Acceptance testing
    - Testing the enduser performs to verify the functionality of the softrware and acceptance of the product
- Regression testing
    - Testing of all major functions after an update or a patch is applied to verify that the changes didn't disrupt functionality

## Software Testing Strategies
1. Positive testing
    - it determines if the application works as expected
2. Negative testing
    - it ensures that the application can gracefully handle invalid input or unexpected behavior

### Structural Coverage
- Statement
    - Requires sufficient test cases for each program statement to be executed at least once
    - Outcome is insufficient to provide confidence in a products behavior
- Decision (Branch)
    - Requires sufficient tests cases for each program decision, so that each possible outcome occurs at least once
    - Considered to be a minimum level of coverage for most software products, but decision coverage alone is insufficient for high integrity application
- Condition
    - Requires sufficient test case for each condition in a program decision to take on all possibvle outcomes at least once.
    - Differs from branch coverage only when multiple conditions must be evaluated to reach a decision
- Multi-condition
    - Requires sufficient test cases to exercise all possible combinations of conditions in a program decision
- Loop
    - Requires sufficient test cases for all program loops to be executed for 0, 1, 2, and many iterations covering initialization, typical running, termination conditions
- Path
    - Requires sufficient test cases for each feasible path, basis path, etc., from start to exit of a defined program segment, to be executed at least once
- Data Flow
    - Requires sufficient test cases for each feasible data flow to be executed at least once. 

## Product Lifecycle
- Traditional Development Lifecycle
<img src = "Pics/CISSP Traditional LC.jpg" width = 500>

- Microsoft Security Development Lifecycle
<img src = "Pics/CISSP Microsoft SDL.jpg" width = 700>

### Vulnerability Disclosure
1. Bug Bounty
    - Reward for reporting vulnerabilities and not going public for a specified amount of time
2. Zero day
    - Time between when a vulnerability is identified and exploit code developed and when remediation is available
3. Vulnerability Disclosure Policy
    - Researcher policy good faith effort to communicate with product vendor and timeline of public disclosure