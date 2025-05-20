---
created: 2025-05-19T13:53
updated: 2025-05-20T07:24
---
## DSSS (Direct Sequence Spread Spectrum)

- DSSS spreads data by multiplying it with a high-rate pseudo-noise (PN) code (chip sequence).
- Each bit becomes multiple chips, increasing bandwidth and interference resistance.
- PN code must match at both ends for successful de-spreading.
- Offers good security, anti-jamming, and signal reliability.

## DSSS Transmitter:

![[DSSS Transmitter.excalidraw.svg]]

1. Modulation: User data is modulated using BPSK.
2. Spreading: Modulated signal is multiplied by a high-rate PN sequence to widen the bandwidth.
3. Transmission: The spread signal is sent over a carrier; each bit becomes multiple chips, improving resistance to interference.
## DSSS Receiver:

![[DSSS Receiver.excalidraw.svg]]
1. De-spreading: The received wideband signal is multiplied again by the same PN sequence used at the transmitter to recover the original narrowband signal.
2. Demodulation: The de-spread signal is demodulated using BPSK to extract the binary data.
3. Output: The original user data is reconstructed after filtering and decoding.