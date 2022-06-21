# Security Operations

- Evaluating Vulnerability, Change, and Configuration Management
- Assessing Resiliency and Fault Tolerance
- Deciphering Digital Forensics and Evidence Handling
- Protecting People and Places

## Configuration Management
Configuration Management is a set of practices designed to ensure that systems are deployed in a consistent state and stay that way through their lifetime
- A baseline Configuration (BC) is a set of specifications for a configuration item (CI), that has been reviewed and agreed on and which can be changed only through change control procedures
- Process
    1. Research | Plan
    2. Approve Baseline Configuration
    3. Implement
    4. Control Changes
    5. Monitor
    6. Report
    7. Repeat
- Change Management practices are designed to ensure that all changes are evaluated, documented, tracked and controlled
    - Process
        1. Submit Request
        2. Evaluate Request
        3. Test
        4. Identify Rollback Options
        5. Approve Request
        6. Document Changes
        7. Determine Change Window
        8. Implement
        9. Verify
        10. Close - If applicable, apply it to Configuration Management Process

## Vulnerability Management
- Vulnerability Management is the process of identifying, mitigating, and responding to known or anticipated vulnerabilities
- Threat Intelligence (TI) is evidence-based information about threats, vulnerabilities, and exploits
- The value of threat intelligence is in its application
    - Changing the security model from reactive to proactive
        - if you understand your adversaries, you can develop tactics to combat current attacks and plan better for future threats
    - Driving better, more informed responses to security incidents
- VM Process
    - Inventory
    - TI intake
    - Assess
    - Prioritize
    - Invoke or Bypass Change Control
    - Deploy
    - Verify
    - Monitor
- Configuration, change, and vulnerability practices work together to ensure that systems are configured correctly and securely when deployed and remain that way throughout their lifetime 

## Resiliency and Fault Tolerance
- Resiliency is the capability to continue operating even when there has been an attack, disruption, or abnormal operating conditions
- Fault tolerance is the capability of a system to continue to operate in the event of failure of one or more system components

### Fault Tolerance
<img src = "Pics/CISSP Fault Tolerance.jpg" width = 800>

- Example for fail-secure is Firewall. When Firewall is failed, all the ports should shut (Trustworthy state)
- RAID (Redundant Array of Independent Disks) <br>
    <img src = "Pics/CISSP RAID.png" width = 600> 
- Backup and Replication
    - Traditional data backup and recovery systems copy data to removable media (Generally so it can be manually transported to another location)
        - Automated solutions are often built-in to an application and are faster, more reliable, and facilitate more frequent copies than traditional backup technology
    - Replication is an automated process that streams copies of data to one or more locations in real time or near-time

#### Backup Strategies
- Types
    - Full-backup
        - Backs up all files
    - Differential
        - Backs up all files created or modified since last full backup. 
        - Does not reset archive bit
        - Iot restore, Full backup + most recent differential backup
    - Incremental
        - Backs up all "changed" files
        - Does reset archive bit
        - Iot restore, Full backup + all incremental backups
- Automated Backup Strategies
    - Disk Shadowing
        - Data is written to (and read from) two or more "independent" disks
        - Process is transparent to the user
    - Electronic Vaulting
        - Copies files as thedy are changed and periodically transmitte d to an backup location
    - Remote Journaling
        - Copies "transaction logs" and periodically transmitted to a backup location

#### Replication Strategies
- Types
    - Point-in-Time
        - Preiodic snapshots replicated
        - If replicated, snapshots are pointer based, then just changes transmitted
    - Asynchronous Replication
        - Write is considered complete as soon as local storage commits
        - Remote storage updated with a slight time lag.
    - Synchronous Replication
        - Data written in two location (Local and Remote)
        - Both write operations must successfully complete before the system can proceed
        - Guaranteed zero data loss
<img src = "Pics/CISSP Cost Complexity Availability.jpg" width = 700>

<br>
<br>

## Evidence Handling
- Incident handlers should treat every investigation as if it will lead to a court case
- Incident handlers must establish and maintain an evidentiary chain (Chain of custody) for all physical and electronic evidence collected during the investigation
- Be aware that this information may become public record, and company confidential information should not be included unless absolutely necessary

### Types of Investigation
<img src = "Pics/CISSP Types of Investigations.jpg" width = 800>

### Digital Forensics Process
1. Evidence Collection
2. Acquisition (Making Cover to avoid using Original)
3. Recovery and examination
4. Analysis
---------
<br>
After Digital Forensics Process

5. Reporting
6. Testifying
7. Archiving

#### Acquisition Technique
- Memory Imaging
    - Acquisition of volatile data
- Write Blocker
    - Tool that intercepts inadvertnet drive writes
- Fingerprint
    - Fixed length one-way representation of the source (Hash)
- Bit Stream Image
    - Bit-by-bit copy of the source material that preserves all latent data in addition to files and directory structure
    - Accessing an image does not modify its data
- Clone
    - Exact copy of the entire physical hard drive including all active and residual data and unallocated or slack space
    - A cloned hard drive can be installed into the computer, and the computer will be reboot and function as if the original drive were still installed


<br>
<br>

## File Recovery
- Cluster
    - Fixed length blocks of disk space
    - Documented in a File Allocation Table or equivalent
- Slack Space
    - Space between the end of a file and the end of teh cluster
    - Slack space can contain data from RAM or segments of deleted files
- Unallocated (free) space
    - Clusters that are not allocated to a file
    - Clusters can contain deleted file fragments
    - Carving is the process by which deleted files or fragments are recovered

<br>
<br>

## Metadata
<img src = "Pics/CISSP Metadata.jpg" width = 800>

<br>
<br>

## Steganography
- Watermarking is a hidden message that is used to prove or claim ownership
- Hidden Binary files are most often found embedded in image and audio files
- Steganalysis is the detection of steganography by a third party

<br>
<br>

## Protecting People and Places
- <i>Securing the human</i> is a catch phrase that reminds us that we need to protect personnel and provide safe and secure workplaces 
- Proper design and effective use of the physical controls can mitigate risk to people and places
    - Obstacles to frustrate trivial attackers and delay serious ones
    - Detective controls make it likely that attacks will be noticed 
    - Response mechanisms to repel, catch, or frustrate attackers

## CPTED (Crime Prevention through Environmental Design)

The Basic premise of CPTED is that the proper design and effective use of the physical environment can lead to a reduction in the incidence and fear of crime.

- CPTED is a psychological and sociological method of looking at security based upon three constructs
    1. People protect territory they feel is their own, and people have a certain respect for the territory of others
    2. Intruders do not wan to be seen
    3. Limiting access discourages intruders and/or marks them as intruders

## Fail Safe and Fail Secure

- In event of an emergency, the organization's security structure must comply with safety, fire, and building codes
    - Fail-safe implies that in a emergency situation, ingress/egress controls will default to open
    - Fail-secure implies that in an emergency situation, ingress/egress controls will default to locked

## Identifying Locks and Sensors
<img src = "Pics/CISSP Locks and Sensors.jpg" width = 800>

## Social Engineering
- Social Engineering
    - Exploiting human vulnerabilities
- Pretexting
    - Impersonation or babricated scenario
- Baiting
    - Temptation or promise of a good or service
- Duress
    - Threat of harm
- Phishing
    - Social engineering using email
- Vishing
    - Social engineering using voice (Phone)
- SMSiShing
    - Social engineering using text msg
- Shoulder Surfing
    - Covert observation
- Piggybacking / tailgating
