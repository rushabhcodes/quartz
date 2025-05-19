---
created: 2025-05-19T23:54
updated: 2025-05-19T23:55
---
Here’s a clear, well-organized explanation of **Mobile Terminated Call (MTC)** and **Mobile Originated Call (MOC)** with their steps:

---

## Mobile Terminated Call (MTC)

An **MTC** is a call **received by the mobile user**. When someone dials a mobile number, the network locates the mobile subscriber and sets up the call by paging and authenticating the mobile device.

### Steps for MTC:

1–2. Calling user dials the mobile number → Call reaches **GMSC** via PSTN. 

3. **GMSC** queries the **HLR** for the mobile subscriber’s location.  
4–5. **HLR** contacts the **VLR** to get routing information.  
4. **HLR** sends routing info back to **GMSC**.  
5. **GMSC** forwards the call to the serving **MSC**.  
8–9. **MSC** checks the mobile subscriber’s status in the **VLR**.  
6. **MSC** pages the **BSSs** in the subscriber’s area.  
7. **BSS** pages the **MS** (mobile station).  
8. **MS** responds to the **BSS**.  
13–14. Authentication and call setup occur via **MSC** and **VLR**.  
15–17. Traffic channel is allocated, and the call is established.

---

## Mobile Originated Call (MOC)

An **MOC** is a call **initiated by the mobile user**. The mobile device requests the network to set up a call, which is then routed to the destination via the network.

### Steps for MOC:

1. **MS** sends a call request to the **BSS**.
    
2. **BSS** forwards the request to the **MSC**.  
    3–4. **MSC** authenticates the **MS** with the **VLR**.
    
3. Call setup proceeds from the **MSC** to the **GMSC**.  
    6–7. **GMSC** routes the call to the **PSTN** or other networks.  
    8–9. **MSC** allocates a traffic channel for the call.
    
4. **BSS** connects the call to the **MS**.
    

---

If you want, I can help diagram this or add more technical details!