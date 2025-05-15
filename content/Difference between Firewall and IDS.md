| Feature                | Firewall                                | Intrusion Detection System ([[IDS]])    |
| ---------------------- | --------------------------------------- | --------------------------------------- |
| **Purpose**            | Blocks/filters unauthorized traffic     | Detects suspicious/malicious activity   |
| **Action**             | **Prevents** intrusion                  | **Detects and alerts** about intrusion  |
| **Traffic Control**    | Yes                                     | No                                      |
| **Placement**          | Usually at the **network boundary**     | Can be placed **inside the network**    |
| **Types**              | Packet-filtering, stateful, proxy, NGFW | Signature-based, anomaly-based, hybrid  |
| **Real-time Response** | Can **block** traffic                   | Generally **passive** (alerts only)     |
| **Focus**              | Known threats and access rules          | Unknown or suspicious behavior patterns |
### Summary

- Firewalls act as **gatekeepers**, blocking or allowing traffic.
    
- IDS acts as a **watchdog**, monitoring for unusual or malicious activity.
    
- Both are essential for a layered security architecture.