### **1. Security Goals**

Security goals define **what** needs to be protected in an information system. These are high-level objectives that guide the design and implementation of security.

The **main security goals** are:

|Goal|Description|
|---|---|
|**Confidentiality**|Ensuring that information is not accessed by unauthorized users.|
|**Integrity**|Protecting data from being altered by unauthorized parties.|
|**Availability**|Ensuring reliable and timely access to resources by authorized users.|
|**Authentication**|Verifying the identity of users and systems.|
|**Non-repudiation**|Preventing denial of actions performed (e.g., sending a message or transaction).|

---

### **2. Security Services**

Security services are the **functions or services provided to meet security goals**. These are defined by standards like the OSI model.

|Security Service|Purpose|
|---|---|
|**Authentication**|Verifies the identity of communicating entities.|
|**Access Control**|Limits access to system resources to authorized users only.|
|**Data Confidentiality**|Prevents unauthorized disclosure of data.|
|**Data Integrity**|Ensures that data has not been tampered with.|
|**Non-repudiation**|Ensures actions cannot be denied later.|
|**Availability**|Ensures systems are up and running when needed.|

---

### **3. Security Mechanisms**

Security mechanisms are the **tools and techniques** used to implement security services.

|Mechanism|Description|
|---|---|
|**Encryption**|Protects confidentiality by making data unreadable without a key.|
|**Digital Signatures**|Ensures integrity, authentication, and non-repudiation.|
|**Hash Functions**|Detect changes in data (used in integrity).|
|**Firewalls**|Controls incoming/outgoing network traffic (access control).|
|**Authentication Protocols**|Verifies user/system identity.|
|**Intrusion Detection Systems (IDS)**|Monitors and detects suspicious activities.|

---

### Relationship between Security Services and Mechanisms

- **Security Services** are like **goals** or **functions** we want to achieve.

- **Security Mechanisms** are the **means or tools** to achieve those services.


**Example**:

- **Service**: Data Confidentiality  
**Mechanism**: Encryption (e.g., AES, RSA)

- **Service**: Authentication  
**Mechanism**: Passwords, Biometrics, Digital Certificates

|**Security Goal**|**Security Service**|**Security Mechanism (Examples)**|
|---|---|---|
|**Confidentiality**|Data Confidentiality|Encryption (AES, RSA), Access Control Lists (ACLs)|
|**Integrity**|Data Integrity|Hash Functions (SHA-256), Checksums, Digital Signatures|
|**Availability**|Availability Service|Redundancy, Load Balancers, Firewalls, DoS Protection|
|**Authentication**|Authentication Service|Passwords, Biometrics, Digital Certificates (PKI), OTP|
|**Non-repudiation**|Non-repudiation Service|Digital Signatures, Logging, Timestamps|
|**Access Control**|Access Control Service|Authorization Policies, Role-Based Access Control (RBAC)|
