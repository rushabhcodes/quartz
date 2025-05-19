---
created: 2025-05-19T19:48
updated: 2025-05-19T19:48
---
# Selective Retransmission in TCP

Selective retransmission (also known as Selective Acknowledgment or SACK) is an enhancement to standard TCP that improves efficiency when handling packet loss, particularly in wireless and mobile environments.

## The Problem with Standard TCP

In standard TCP, when a packet is lost, the sender must retransmit that packet and all subsequent packets, even if those subsequent packets were successfully received. This is because traditional TCP uses cumulative acknowledgments that only confirm receipt of all bytes up to a certain sequence number.

For example, if packets 1, 2, 4, and 5 arrive but packet 3 is lost:

- The receiver can only acknowledge up to packet 2
- After timeout or triple duplicate ACKs, the sender must retransmit packet 3 and all subsequent packets (4 and 5)
- This wastes bandwidth and reduces throughput, especially on wireless networks

## Selective Retransmission Mechanism

Selective retransmission solves this inefficiency by:

1. **Allowing the receiver to inform the sender about all segments that have arrived successfully**, including those that arrived after a missing segment
    
2. **Enabling the sender to retransmit only those segments that have actually been lost** rather than retransmitting all segments from the point of loss
    

## How It Works

1. **SACK Option Negotiation**:
    
    - During TCP connection establishment, both ends indicate SACK capability
    - This is done through TCP options in the SYN packets
2. **Acknowledging Received Segments**:
    
    - When a gap in sequence numbers is detected, the receiver continues to send ACKs for the last in-order segment received
    - These ACKs include SACK blocks that specify which out-of-order segments have been successfully received
3. **Selective Retransmission**:
    
    - The sender maintains information about which segments have been selectively acknowledged
    - Only unacknowledged segments are retransmitted
    - This avoids unnecessary retransmission of data that has already been received

## Benefits

1. **Efficiency**: Retransmits only lost data, saving bandwidth
2. **Improved Throughput**: Particularly beneficial in networks with high packet loss rates (like wireless networks)
3. **Reduced Latency**: Faster recovery from packet loss
4. **Better Utilization**: Makes better use of available network capacity

## Implementation Considerations

- Requires slightly more complexity in TCP implementation
- Needs additional buffer space at both sender and receiver
- Both sender and receiver must support the SACK option
- The overhead of SACK information in ACK packets is minimal compared to the bandwidth saved

Selective retransmission represents one of the most important TCP enhancements for mobile networking, as it specifically addresses the inefficiencies of traditional TCP when dealing with the higher packet loss rates commonly encountered in wireless environments.