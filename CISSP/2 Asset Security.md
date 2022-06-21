# Asset Security
- Privacy Concepts
- Information Lifecycle

## Privacy
- Privacy is the right of an individual to control the use of his/her personal information

### Privacy Principles
- Internationally, the organization for Economic Cooperation and Development (OECD) Privacy Principles are the most commonly used framework.
- Principles include collection limitation, data quality, purpose specification, use limitation, security safeguard, openness, individual participation, and accountability. (http://oecdprivacy.org/, https://www.oecd.org/sti/ieconomy/oecd_privacy_framework.pdf)

1. Collection Limitation Principle
<br>There should be limits to the collection of personal data and any such data should be obtained by lawful and fair means and, where appropriate, with the knowledge or consent of the data subject.

2. Data Quality Principle
<br>Personal data should be relevant to the purposes for which they are to be used, and, to the extent necessary for those purposes, should be accurate, complete and kept up-to-date.

3. Purpose Specification Principle
<br>The purposes for which personal data are collected should be specified not later than at the time of data collection and the subsequent use limited to the fulfilment of those purposes or such others as are not incompatible with those purposes and as are specified on each occasion of change of purpose.

4. Use Limitation Principle
Personal data should not be disclosed, made available or otherwise used for purposes other than those specified in accordance with Paragraph 9 except:
<br>a) with the consent of the data subject; or
<br>b) by the authority of law.

5. Security Safeguards Principle
<br>Personal data should be protected by reasonable security safeguards against such risks as loss or unauthorised access, destruction, use, modification or disclosure of data.

6. Openness Principle
<br>There should be a general policy of openness about developments, practices and policies with respect to personal data. Means should be readily available of establishing the existence and nature of personal data, and the main purposes of their use, as well as the identity and usual residence of the data controller.

7. Individual Participation Principle
<br>An individual should have the right:
<br><br>a) to obtain from a data controller, or otherwise, confirmation of whether or not the data controller has data relating to him;
<br><br>b) to have communicated to him, data relating to him
<br><br>i) within a reasonable time;
<br>ii) at a charge, if any, that is not excessive;
<br>iii) in a reasonable manner; and
<br>iv) in a form that is readily intelligible to him;
<br><br>c) to be given reasons if a request made under subparagraphs (a) and (b) is denied, and to be able to challenge such denial; and
<br><br>d) to challenge data relating to him and, if the challenge is successful to have the data erased, rectified, completed or amended.

8. Accountability Principle
<br>A data controller should be accountable for complying with measures which give effect to the principles stated above.

<br>

### Privacy Laws
<img src = "Pics/CISSP Privacy Laws.jpg" width = "800">

## Information Life Cycle
1. Collection
2. Uses
3. Retention Archiving
4. Deletion/Destruction
- Retention
<br> Retention is a protocol within an organization that dictates types of unaltered data that must be kept and for how long
- Archiving
<br> Archiving is the process of securely storing unaltered data for the retention period.
<br> *** Backup and Replication is the process of making copies of the data for recoverability. THEY'RE NOT THE ARCHIVING.
- Legal Hold
<br> A Legal hold is the requirement for an organization to preserve all forms of relevant information when litigation, audit, or government investigation is reasonably anticipated. The objective is to avoid evidence spoliation.
<br> ex) Even though you don't have Email retention policy but you will be asked to maintain email stream for the legal action
- eDiscovery (AKA electronic discovery)
<br> it refers to any process in wich electronic data is sought, located, secured, and searched with the intent of using it as evidence in a civil or criminal legal case.

### Deletion
Simply by hitting "Delete" button is not acutally delete the data. It could be recovered with digital forensic tool (data remanence).<br>
Make sure to consider how to securely delete the data

- Secure deletion ensures that the deleted file or file fragments cannot be retrieved and/or reconstructed.
1. Disk Wiping
<br> It overwrites all addressable storage and indexing locations "multiple" times
<br> - US DoD 5220.22-M method requires overwriting all addressable storage and indexing locations on the drive three times: with zeros(0x00), complement (0xFF) and Random characters
<br> - Exception: SSD may require a manufacturer specific utility.

2. Degaussing
<br>It involves using a machine or wand that produce a strong electromagnetic field to destroy all magnetically recorded data.

3. Shredding
<br> It means to shred the drive physically 
<br> - For SSD: A shred width of 1/2" or smaller is needed to break through the small memory chips and securely obliterate the data.