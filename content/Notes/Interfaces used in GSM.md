---
created: 2025-05-20T00:01
updated: 2025-05-20T00:01
---
## GSM Interfaces and Their Uses

| **Interface** | **Between**                                     | **Purpose**                                                                                  |
| ------------- | ----------------------------------------------- | -------------------------------------------------------------------------------------------- |
| **Um**        | Mobile Station ↔ Base Transceiver Station (BTS) | Wireless **air interface** used for communication between the mobile device and the network. |
| **Abis**      | BTS ↔ Base Station Controller (BSC)             | Carries **voice, data, and control signals**; allows the BSC to manage BTS operations.       |
| **A**         | BSC ↔ Mobile Switching Centre (MSC)             | Handles **call control, handovers**, and **mobility management**.                            |
| **B**         | MSC ↔ Visitor Location Register (VLR)           | Transfers **temporary subscriber information** for session and call handling.                |
| **C**         | MSC ↔ Home Location Register (HLR)              | Retrieves **permanent subscriber data** used for authentication and service provisioning.    |
| **D**         | HLR ↔ VLR                                       | Transfers subscriber information when a user **roams** into a new location.                  |
| **E**         | MSC ↔ Other MSCs                                | Supports **inter-MSC handovers** and routing of calls.                                       |
| **F**         | MSC ↔ Equipment Identity Register (EIR)         | Verifies the **IMEI** to prevent the use of stolen or unauthorized devices.                  |
| **G**         | VLR ↔ Other VLRs                                | Transfers user data during **inter-VLR** handovers.                                          |