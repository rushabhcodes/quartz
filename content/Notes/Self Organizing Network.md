---
created: 2025-05-19T19:58
updated: 2025-05-19T20:00
---
A **Self-Organizing Network (SON)** is an advanced automation framework used in modern mobile networks (such as LTE and 5G) to reduce manual intervention by enabling the network to **automatically configure, optimize, and heal itself**.

---

### Key Functions of SON

1. **Self-Configuration**: Automatically configures newly deployed network nodes (like base stations) for plug-and-play operation.
    
2. **Self-Optimization**: Continuously improves performance by adjusting network parameters (e.g., handover thresholds, power levels).
    
3. **Self-Healing (Self-Recovery)**: Detects and corrects faults (e.g., base station failure) by reconfiguring surrounding nodes.
    

---

### 🏗 Architecture of SON

SON can be implemented using **three types of architectures**:

#### 1. **Centralized SON**

![[Pasted image 20250519195948.png]]

- **Location**: All SON functionalities are located in a central **OAM (Operations, Administration, and Maintenance)** system.
    
- **Function**: Global optimization (e.g., network-wide load balancing, interference coordination).
    
- **Advantage**: Complete network view allows for coordinated, intelligent decisions.
    
- **Limitation**: Slower response and potential scalability issues.
    

#### 2. **Distributed SON**

![[Pasted image 20250519200007.png]]

- **Location**: SON functions are embedded directly into each base station (e.g., eNB in LTE).
    
- **Function**: Each base station performs local optimizations like handover tuning and power adjustment.
    
- **Advantage**: Fast response time and scalability.
    
- **Limitation**: Lack of global network awareness may lead to suboptimal decisions.
    

#### 3. **Hybrid SON**

![[Pasted image 20250519200024.png]]

- **Location**: Combines both centralized and distributed components.
    
- **Function**:
    
    - Central SON handles global, complex tasks.
        
    - Distributed SON handles fast, local optimizations.
        
- **Advantage**: Balances efficiency, speed, and performance.
    

---

**In Summary**:  
SON is essential for handling the increasing complexity and scale of mobile networks. It enhances network performance, improves user experience, reduces operational costs, and supports rapid deployment of new network nodes.