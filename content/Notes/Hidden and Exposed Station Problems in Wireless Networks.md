---
created: 2025-05-19T19:25
updated: 2025-05-19T19:32
---
# Hidden and Exposed Station Problems in Wireless Networks

## 1. Hidden Station Problem

**Definition**: Occurs when two stations (e.g., A and C) are out of range of each other but both can communicate with a common station (e.g., B).

**Problem**:
- Station A senses the channel as idle and sends data to B.
- At the same time, station C (which cannot sense A) also sends data to B.
- Collision occurs at B, even though A and C could not detect each other.

![[Pasted image 20250519193133.png]]

As shown in the figure, stations A and C cannot detect each other's transmissions because they are outside each other's range (indicated by the dashed and dash-dot lines). However, both are within range of station B (solid line).

**Result**:
- Increased collisions and reduced network performance.
- Higher packet loss rate.
- Reduced overall throughput.
- Increased latency due to retransmissions.

**Solution**:
- Use RTS/CTS (Request to Send / Clear to Send) mechanism from IEEE 802.11 MAC protocol.
- Station A sends an RTS to B; B replies with CTS.
- CTS is heard by all nearby nodes (including C), so C stays silent, preventing collision.
- The duration of the intended communication is included in both RTS and CTS frames.

## 2. Exposed Station Problem

**Definition**: Occurs when a station (e.g., C) refrains from transmitting due to sensing a nearby transmission (e.g., B → A), even though its transmission (C → D) would not interfere.

**Problem**:
- B senses the channel and finds it free. B starts transmitting data to A.
- C also wants to transmit data to D.
- C detects B's transmission, because B is within C's transmission range.
- C assumes the channel to D is busy and delays its transmission, even though:
  - D is out of range of B's signal.
  - There would be no interference between B→A and C→D communication.

![[Pasted image 20250519193225.png]]

**Result**:
- Underutilization of the channel — reduced throughput.
- Unnecessary delays in data transmission.
- Inefficient use of network capacity.
- Reduced overall network performance.

**Solution**:
Use RTS/CTS Mechanism:
- C sends RTS to D.
- If D replies with CTS, it means the channel is clear for communication.
- Since D is not in range of B, it will respond, allowing C to send.
- This prevents C from unnecessarily delaying its transmission.

## Additional Mitigation Techniques:

1. **MACA (Multiple Access with Collision Avoidance)**:
   - Original protocol that introduced RTS/CTS exchange
   - Provides the foundation for collision avoidance in wireless networks

2. **Power Control**:
   - Adjusts transmission power to minimize interference
   - Reduces the size of contention domains

3. **Directional Antennas**:
   - Focus signal strength in specific directions
   - Reduce unwanted interference between stations

4. **Multiple Channels**:
   - Distributes communications across different frequency bands
   - Decreases contention in densely populated networks