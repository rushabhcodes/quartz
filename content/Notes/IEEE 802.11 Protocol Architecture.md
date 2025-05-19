---
created: 2025-05-19T20:23
updated: 2025-05-19T20:25
---
The IEEE 802.11 standard defines the protocol architecture for Wireless Local Area Networks (WLANs). It describes how data is transmitted and managed over wireless networks.
![[Pasted image 20250519202448.png]]

This architecture facilitates the connection of wireless devices to a wired network using WiFi (IEEE 802.11) through an Access Point (AP). The AP acts as a bridge between two networks:

- Wireless (IEEE 802.11)
- Wired Ethernet (IEEE 802.3)

Although these networks use different MAC and PHY layers, they share a common LLC layer, which enables communication. The AP translates between the two protocols, allowing devices on both networks to utilize the same TCP/IP applications for services like web Browse or email. This setup facilitates smooth communication in infrastructure-based wireless networks.

![[Pasted image 20250519202516.png]]

The IEEE 802.11 protocol architecture is typically described in terms of the following layers:

1. **Physical Layer (PHY):**
    
    - Responsible for wireless signal transmission and reception.
    - Defines modulation techniques (e.g., OFDM, DSSS) and data rates.
    - Divided into three sublayers:
        - PMD (Physical Medium Dependent): Responsible for the actual modulation and transmission of signals.
        - PLCP (Physical Layer Convergence Protocol): Prepares data for transmission and adds headers.
        - PHY Management: Coordinates the functions of the physical layer.
2. **MAC Layer (Medium Access Control):**
    
    - Manages channel access using mechanisms like CSMA/CA for collision avoidance and controls frame transmission.
    - MAC Management handles processes such as scanning, authentication, and association.
3. **LLC Layer (Logical Link Control):**
    
    - Provides flow and error control for data transmission.
    - Interfaces with higher network layers (e.g., TCP/IP).