---
created: 2025-05-19T23:21
updated: 2025-05-19T23:27
---
![[Pasted image 20250519232509.png]]
### GSM Architecture Overview

The GSM architecture is divided into three main subsystems:

1. **Mobile Station (MS)**
    
2. **Basic Station Subsystem (BSS)**
    
3. **Network Switching Subsystem (NSS)**
    

Additionally, there is the **Operating Support Subsystem (OSS)** to manage and maintain the network.

---

### 1. Mobile Station (MS)

The Mobile Station is the user's device, made up of two parts:

- **A. Mobile Equipment (ME):**
    
    - Portable or vehicle-mounted handheld device (e.g., a mobile phone).
        
    - Uniquely identified by an **IMEI** (International Mobile Equipment Identity) number.
        
    - Used for voice and data transmission.
        
    - Monitors power and signal quality of surrounding cells to assist in smooth handover between cells.
        
    - Can send 160-character long SMS messages.
        
- **B. Subscriber Identity Module (SIM):**
    
    - A smart card containing the **IMSI** (International Mobile Subscriber Identity) number.
        
    - Enables users to send and receive calls and use other subscriber services.
        
    - Protected by a password or PIN.
        
    - Contains encoded network identification details.
        
    - Portable: can be moved from one mobile device to another.
        

---

### 2. Basic Station Subsystem (BSS)

The BSS is responsible for communication between the Mobile Station and the Network Switching Subsystem.

- **Base Transceiver Station (BTS):**
    
    - Facilitates wireless communication between the mobile device (UE) and the network.
        
    - Handles radio signals to and from the mobile station.
        
- **Base Station Controller (BSC):**
    
    - Controls one or more BTSs.
        
    - Manages radio resources including setting up radio channels, frequency hopping, and handovers.
        
    - Acts as a link between the BTS and the Mobile Switching Center (MSC).
        

---

### 3. Network Switching Subsystem (NSS)

The NSS handles the core network functions such as call routing and subscriber management.

- **Mobile Switching Center (MSC):**
    
    - Primary node for routing voice calls, SMS, and other services (conference calls, fax, circuit-switched data).
        
    - Interfaces with other networks such as PSTN, ISDN, and data networks.
        
- **Home Location Register (HLR):**
    
    - Central database that contains subscriber information, such as user profiles and service permissions.
        
- **Visitor Location Register (VLR):**
    
    - Temporary database storing information about subscribers currently in the MSC's service area.
        
- **Authentication Center (AuC):**
    
    - Validates SIM cards attempting to connect to the network to ensure security.
        
- **Equipment Identity Register (EIR):**
    
    - Maintains a list of valid IMEI numbers.
        
    - Helps identify stolen or unauthorized mobile equipment.
        

---

### 4. Operating Support Subsystem (OSS)

- **Operations and Maintenance Center (OMC):**
    
    - Connected to all switching and base station equipment.
        
    - Responsible for monitoring and maintaining the network to ensure smooth operation.
        

---

### Interfaces in GSM Architecture

- **Um Interface:** Air interface between Mobile Station (MS) and BTS. It is called Um because it corresponds to the mobile analog of the ISDN U interface.
    
- **Abis Interface:** Connects the BTS to the BSC within the Basic Station Subsystem (BSS).
    
- **A Interface:** Provides communication between the BSS and the MSC in the Network Switching Subsystem (NSS).
    

---

### Public Networks Connectivity

The MSC connects the GSM network to external public networks such as:

- **PSTN** (Public Switched Telephone Network)
    
- **ISDN** (Integrated Services Digital Network)
    
- **Data Networks**
    