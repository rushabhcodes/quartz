---
created: 2025-05-19T19:50
updated: 2025-05-19T19:55
---
Micro-mobility manages the seamless movement of mobile devices within a local or regional network, ensuring low-latency handovers within a single administrative domain. It is crucial for real-time applications like VoIP, online gaming, and video streaming.

### Need for Micro-Mobility

1. **Reduces Handover Latency**
   - Ensures faster handover between access points.

2. **Scalable Signalling**
   - Limits signalling to the local network, reducing global routing updates.

3. **Efficient Resource Usage**
   - Avoids overload on global mobility protocols like Mobile IP.

### Three major protocols are Cellular IP, HAWAII, and HMIPv6.

#### Cellular IP

Cellular IP is a micro-mobility protocol designed for the seamless movement of mobile nodes within an IP-based network. Unlike global mobility protocols, it optimizes local handovers using a routing cache, ensuring uninterrupted connectivity with minimal overhead.

**Advantages of Cellular IP:**

1. **Seamless Local Handover:** Maintains uninterrupted connectivity by using a routing cache during node movement.
2. **Low Overhead:** Optimizes local handovers without relying on global mobility protocols.

#### HAWAII (Handoff-Aware Wireless Access Internet Infrastructure)

HAWAII implements a hierarchical mobility management approach to enhance efficiency. By localizing handover processes, it minimizes global signalling overhead, making it ideal for scalable and efficient micro-mobility management.

**Advantages of HAWAII:**

1. **Reduced Global Signalling:** Localizes handover processes to minimize signalling overhead.
2. **Scalability:** Well-suited for large networks due to its hierarchical structure.

#### Hierarchical Mobile IPv6 (HMIPv6)

HMIPv6 is an advanced extension of Mobile IPv6 that introduces a dual-level mobility management system. By segmenting handovers into local and global domains, HMIPv6 significantly reduces signalling traffic, improves handover speed, and enhances network performance for mobile users.

**Advantages of HMIPv6:**

1. **Improved Handover Speed:** Segregates local and global domains for faster handovers.
2. **Lower Signalling Traffic:** Reduces global network load by handling updates locally.