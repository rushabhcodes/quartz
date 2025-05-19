---
created: 2025-05-19T23:06
updated: 2025-05-19T23:12
---
In IEEE 802.11 (Wireless LAN), MAC Management is responsible for controlling and managing how devices communicate and stay connected within the network.

The key responsibilities of MAC Management include: synchronization, power management, association/reassociation, and maintaining the MAC Management Information Base (MAC MIB).

### 1. Synchronization

- In a wireless LAN, all stations (devices) must stay synchronized to ensure proper communication.
- Access Points (APs) send out beacon frames at regular intervals.
- These beacons contain timing information that helps stations adjust their clocks and maintain timing alignment.
- This is crucial for timing operations like sleep/wake cycles in power-saving modes.

### 2. Power Management

- Allows devices to conserve battery by entering low-power (sleep) mode when not transmitting or receiving.
- Stations can inform the AP when they enter power-saving mode.
- During this time, the AP buffers any incoming data for the sleeping device.
- Devices periodically wake up to check for buffered data (via beacon frames).

### 3. Association / Reassociation

- Association: The process where a station connects to an AP to gain access to the network.
    - Involves exchanging association request/response frames.
    - The AP assigns an Association ID (AID) to the station.
- Reassociation: Happens when a mobile station moves from one AP's range to another.
    - Ensures seamless handoff and continuous connectivity (important for roaming).

### 4. MAC Management Information Base (MAC MIB)

- It is a database of parameters and status information maintained by each station or AP.
- Contains:
    - Configuration settings (SSID, supported rates, etc.)
    - Current state (associated, authenticated, etc.)
    - Performance data (packet counts, error rates, etc.)
- Used by network management systems to monitor and control wireless communication effectively.