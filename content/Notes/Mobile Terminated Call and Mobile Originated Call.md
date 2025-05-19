---
created: 2025-05-19T23:54
updated: 2025-05-19T23:59
---
## **Mobile Terminated Call (MTC)**

An **MTC** refers to a call **received by the mobile user**. When a caller dials a mobile number, the **GMSC** (Gateway MSC) queries the **HLR** to locate the mobile subscriber. After locating the serving **MSC** and **BSS**, the network pages the **MS**, performs authentication, and sets up the call.

![[Pasted image 20250519235911.png]]
**Steps:**  
1–2): Calling user dials MS number → Call reaches GMSC via PSTN.

3): GMSC queries HLR for MS location.  

4–5): HLR contacts VLR to get routing info.  

6): HLR sends routing info to GMSC.  

7): GMSC forwards call to the serving MSC.  

8–9): MSC checks MS status in VLR.  

10): MSC pages BSSs in the area.  

11): BSS pages the MS.  

12): MS responds to BSS.  

13–14): Authentication and setup via MSC & VLR.  

15–17): Traffic channel allocated; call established.

---

## **Mobile Originated Call (MOC)**

An **MOC** is a call **initiated by the mobile user**. The **MS** sends a request to the **BSS**, which forwards it to the **MSC**. The **MSC** then authenticates the user with the **VLR** and routes the call through the **GMSC** to reach the **PSTN** or other network.

![[Pasted image 20250519235931.png]]
**Steps:**  
1): MS sends a request to BSS to make a call.  

2): BSS forwards the request to MSC.  

3–4): MSC authenticates MS with VLR.  

5): Call setup proceeds from MSC to GMSC.  

6–7): GMSC routes the call to PSTN (or other networks).  

8–9): MSC allocates a channel for the call.  

10): BSS connects the call to MS.