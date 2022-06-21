# Security Architecture and Engineering

## Defining Star [*] and Simple Properties
- Star [*] implies "Write"
- Simple implies "Read" 
- Apply the properties to security models
1. Bell-LaPadula : is for Confidentiality
    - Simple (read) Confidentiality rule: A subject cannot read data at a higher security level. (No read up) 
        - If you don't have higher previlege, you can't read higher 
    - Star [*] (write) confidentiality rule: A subject cannot write information to a lower security level (No write down) 
        - If you write something to lower security level, user without previlege might see something for higher previlege.
2. Biba : is for Integrity
    - Simple (read) Integrity rule: A subject cannot read data at a lower security level (No read down)
        - Someone at lower security level might not know all the fact then what you know. It might contaminate what you have at your security level or might take invalid information
    - Star [*] (write) integrity rule: A subject cannot write information to a higher security (No write up)
        - You might not have complete picture without higher information.
3. Clark Wilson is for Integrity
4. Brewer Nahs is to reduce conflict of interest

<img src = "Pics/CISSP Simple and Star Rules.jpg" width = "800">

<br>
<br>

## Cipher
    Cipher is a technique or set of rules that transforms cleartext into an unreadable form (ciphertext or cryptogram) and back to cleartext

### Key (Cryptovariable)
- It is a value used with an algorithm
- The key dictates what parts of the algorithm will be used in what order and with what values.
- It is secret
- Keyspace is the number of possible key combinations (8bit -> 256 potential keys, etc)
#### Types
1. Stream: Linear, work on one bit at a time
    - ex) RC4
2. Block: Multiple bits at a time
    - Substitution: Substitute bits to the others (a to c, d to f, etc)
        - ex) caesar cipher
    - Transposition: Move bits around.
    - The Goal is confusion (Changing Values) and Diffusion (Changing Order).
    - ECB (Electronic Codebook Mode) each block is independent
    - CBC (Cipher Black Chaining Mode) includes an initialization vertoc and a component of the previous ciphertext to leverage randomization. 

<img src = "Pics/CISSP Block Cipher.jpg" width = "800">

<br>
<br>

## Encryption
### Symmetric Encryption
- It uses the same key for encrypt and decrypt
- It refers to Single key, Shared key, or Session key.

### Assymmetric Encryption
- It uses two different keys but related.
- Known as a key pair
- One key is used to encrypt (Public Key), the other to decrypt (Private Key)
- Diffie-Hellman, RSA, El Gamel, ECC (Current US govt standard)

<img src = "Pics/CISSP Encryption.jpg" width = "800">

### Hybrid Encryption (Both Symmetric and Assymetric)
- Use Symmetric Encryption to encrypt messages and Use Assymetric Encryption to encrypt Session Key (Symmetric Key) to deliver to the receiver.

<img src = "Pics/CISSP Hybrid Encryption.jpg" width = "800">


<br>
<br>

## Hashing
- A Hash is a one-way representation (fingerprint) of a string of text
    - A hash function takes input of any length and creates a fixed length output.
- Hash values are used to prove integrity.

### Collision
- This is when an algorithm produces the same value for two different inputs.
- An attacker can attempt to force a collision with Birthday Attack. (Birthday Attack is the probability that two or more people in a group of 23 share the same birthday is >50%)

<img src = "Pics/CISSP Hash.jpg" width = "800">

### Effective Hash Characteristics
1. Computationally hard to reverse
2. Repeatable (Output should be the same everytime user put the same input)
3. Collision Resistance  

### Hashed MAC
- A hashed message authentication Code (HMAC) is hashed value that includes a symmetric Key.
    - An HMAC cannot be reproduced without knowing the key.
    - An HMAC provides integrity and data origin authentication.
    - An HMAC is used by cryptographic protocols such as the TLS and IPsec to verify the integrity of transmitted data during secure comms.

### Salting
- Salting enforces the Hashing process by adding more values on plaintext


<br>
<br>

## Digital Signature
- It is a vash value encrypted with the sender's private key.
    - A digital signature provides integraity and non-repudiation. (Because in order to decrypt, it requires sender's private key and when validating the message uses sender's public key)

- Requirement
    - Hashing Algorithm (e.g. SHA)
    - Digital signature function (such as RSA or DSA)

### Process
<img src = "Pics/CISSP Digital Signature Process.jpg" width = "500">


<br>
<br>

## Digital Certificate
    It is an electronic "Passport" that identifies a person, device, domain, organization, or publisher (of the Code).
        - The Certificate is issued by a "Trusted" CA (Certification Authority), a web of trust, or self-signed

<img src = "Pics/CISSP x509.jpg" width = "800">

### Certificate Authorities (CA)
    Certificate Authority: Issue and revoke the certificates.
    Registration Authority: Administrative (Apply, Background Check, Paperwork, etc.)

### Obtaining a Digital Certification
<img src = "Pics/CISSP Digital Certification Process.jpg" width = "500">

### Digital Certificate Revocation Process
- Certificate Revocation List (CRL)
    - CA maintains list of certificates that have been revoked
- Online Certificate Status Protocol (OCSP)
    - Client receives certificate
    - Client sends OCSP Request to a OCSP Responder
    - OCSP Responder replies with a certificate status
- Both are only enforced for "Extended Validation (EV)" Certificates


<br>
<br>

## Cryptographic Communications Protocols
- Cryptographic Communications Protocols are designed to secure information flow.
- Information flow is vulnerable to
    - Eavesdropping and packet capture (a violation of confidentiality)
    - Tempering (a violation of integrity)
    - Spoofing and misrepresentation (a violation of authentication, integrity and availability)

## Cryptographic Protocols
- Link and end-to-end Encryption
- Common cryptographic Protocols
- IPsec Suite of services

### Transmission
- Modes
    - Link encryption (Tunnel Mode)
        - All control information (Header, trailers, and routing infromation) is encrypted along with the payload
        - Not encourage if there is/are intermediary device(s) without encryption related functions. (becuase it would requires intermediary device decrypt everytime to see the control information)
    - End-to-end Encryption (Transport Mode)
        - Only the Payload is encrypted
        - Intermediary devices do not have encryption related functions

<img src = "Pics/CISSP Cryptographic Protocols.jpg" width = "800">


<br>
<br>

## IPSec
    IPSec is a suite of protocols that uses cryptographic security services to protect communications over Internet Protocol networks
        1. Native to IPv6
        2. Supports authentication, message integrity, encryption, and nonrepudiation
        3. Operates in transport mode (end-to-end) or Tunnel Mode (Link)

<img src = "Pics/CISSP IPsec Components.jpg" width = "500">

## Cryptanalysis
    Cryptanalysis is the science of 
        1. Cracking Codes
        2. Decoding Secrets
        3. Finding Weaknesses in algorithms or protocols
        4. Exploiting computing power

- Workfactor = time + effort
### Categories
- Cipher-text only
    - Only thing to work with is sample cipher text
- Known Plaintext
    - With both Sample of Plaintext and corresponding cipher text
- Chosen Plaintext
    - Choose sample plaintext and then get to see corresponding cipher text
- Chosen Ciphertext
    - With ciphertext, try to find plaintext (Cracking code)

### Key Attacks
<img src = "Pics/CISSP Key Attacks.jpg" width = "700">

### Hash Attacks
<img src = "Pics/CISSP Hash Attacks.jpg" width = "800">


<br>
<br>

## Database Security Objectives
    CIA + Privacy
    - Confidentiality
    - Integrity
    - Availability
    - Privacy 

### Confidentiality (Access Controls)
<img src = "Pics/CISSP Confidentiality.jpg" width = "800">

### Integrity - Concurrency
    Concurrency issues arise when a database is simultaneously accessed by subjects and other objects.

- Semantic Integrity: Structual and semantic rules are enforced including deadlocking
- Commit Operation: Protects the transaction

#### ACID Characteristics
    Online trasaction processing(OLTP) is generally used when databases are clustered to provide fault tolerance and real-time performance.
    A - Atomicity: Transactions must be impletmented in their entirety, or they must be completely rooled back.
    C - Consistency: Transactions must be correct across all instances
    I - Isolation: Transactions must not interact with other transactions until completed.
    D - Durability: Transactions cannot be rolled back, once committed

### Availability (Transaction Recovery)
- Rollback: Operation that ends a corrupt or an invalid transaction, cancels the changes to the database and logs the error
- Checkpoint: Known good point from which the database can recover using the transaction log
- Savepoints: Temporary backup files

### Privacy
<img src = "Pics/CISSP Privacy.jpg" width = "800">

<br>
<br>

## Injection Attack
    Injection is the failure to properly validate input from the client or environment
- Inject flaws are prevalent, particularly in legacy code (e.g. SQL injection)
- A successful attack can result in data loss, corruption, compromise, DOS, or even a complete hostile takeover.
- Injection flaws occur when an application sends untrusted data to an interpreter
- Resolution is validate input and output
