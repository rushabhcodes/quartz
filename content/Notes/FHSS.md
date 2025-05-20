---
created: 2025-05-19T13:40
updated: 2025-05-20T07:22
---
## Frequency Hopping Spread Spectrum (FHSS):

- FHSS uses TDM and FDM, splitting available bandwidth into smaller channels.
- Transmitter and receiver hop between channels after a set time.
- The hopping sequence defines the pattern of frequency changes.
- Dwell time is the duration spent on a frequency before hopping.
- Two types: **Slow hopping** (few hops per bit) and **Fast hopping** (multiple hops per bit).
### FHSS Transmitter:
![[FHSS Transmitter.excalidraw.svg]]
1. Modulation: User data is modulated using FSK or BPSK (e.g., f₀ for binary 0, f₁ for binary 1).
2. Hopping Sequence: Used to generate the carrier frequency fᵢ via a frequency synthesizer.
3. Final Modulation: The spread signal is created with frequencies fᵢ + f₀ (for 0) and fᵢ + f₁ (for 1).

### FHSS Receiver:
The receiver reverses the FHSS transmission process to recover user data.
![[FHSS Receiver.excalidraw.svg]]
1. Demodulation: Uses the hopping sequence to extract the narrowband signal.
2. Analog-to-Digital Conversion: Converts the signal back to original binary data.