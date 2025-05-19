---
created: 2025-05-19T16:41
updated: 2025-05-19T16:46
---
## **Overview**
Mobility management enables mobile devices (Mobile Nodes - MNs) to maintain uninterrupted internet connectivity while moving across different networks without changing their IP addresses. This is achieved through **IP mobility protocols** that handle seamless handovers between networks.

---

## **Mobile IP (IP Mobility)**
Mobile IP allows a device to have:
- **Home Address (HoA)**: Permanent IP address in its home network.
- **Care-of Address (CoA)**: Temporary IP address in a foreign network.

### **How Mobile IP Works**
1. The MN registers its **CoA** with the **Home Agent (HA)**.
2. The HA intercepts packets destined for the MN’s **HoA** and tunnels them to the **CoA**.
3. The MN sends replies either directly or via reverse tunneling.

### **Challenges in Mobile IP**
- **Triangular Routing (MIPv4)**: Packets must go through the HA, increasing latency.
- **Handover Delay**: Registration and binding updates cause interruptions.

---

## **Macro Mobility (Inter-Domain Mobility)**
Manages movement **across different administrative domains** (e.g., between ISPs).

### **1. Mobile IPv6 (MIPv6)**
- Enhances IPv6 with built-in mobility support.
- **Eliminates triangular routing** by allowing **direct communication** between the MN and Correspondent Node (CN).
- Uses **Binding Updates (BU)** to inform CNs of the MN’s current location.

### **2. Fast Mobile IPv6 (FMIPv6)**
- Reduces handover latency by:
  - **Predicting movement** (using Layer 2 triggers).
  - **Pre-configuring a new CoA** before disconnection.
  - **Buffering packets** to prevent loss during handover.

---

## **Micro Mobility (Intra-Domain Mobility)**
Manages movement **within the same network domain** (e.g., campus, enterprise network).

### **1. Cellular IP (CIP)**
- Uses **gateway-based routing** and **paging caches**.
- **Soft-state routing**: Caches paths for active/idle MNs.
- **Semi-soft handover**: Temporarily uses both old and new base stations to minimize packet loss.

### **2. HAWAII (Handoff-Aware Wireless Access Internet Infrastructure)**
- **Hierarchical routing**: Updates paths only along the MN’s route.
- Reduces signaling overhead by avoiding global HA updates.

### **3. Hierarchical MIPv6 (HMIPv6)**
- Introduces a **Mobility Anchor Point (MAP)** to manage local movements.
- The MN has two addresses:
  - **Regional CoA (RCoA)** – For global routing.
  - **On-Link CoA (LCoA)** – For local routing.
- Reduces binding updates to the HA.

---

## **Conclusion**
- **Mobile IP** enables global mobility by maintaining a permanent HoA while using temporary CoAs.
- **Macro Mobility (MIPv6/FMIPv6)** handles large-scale movements across networks.
- **Micro Mobility (CIP/HAWAII/HMIPv6)** optimizes local handovers for faster, seamless connectivity.

These protocols ensure that wireless devices stay connected while moving, supporting applications like VoIP, video streaming, and IoT in 5G and Wi-Fi networks.