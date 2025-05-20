---
created: 2025-05-19T14:12
updated: 2025-05-20T07:35
---
Signal propagation refers to the movement of electromagnetic waves from a transmitter to a receiver through a medium, influenced by environmental interactions. These interactions cause phenomena like shadowing, reflection, refraction, scattering, and multipath propagation, which significantly impact communication quality.

## Types of Signal Propagation Ranges:

![[Types of Signal Propagation Ranges.excalidraw.svg]]

1. **Transmission Range:**
	The range within which the signal is strong enough for the receiver to decode it accurately with a low error rate.
2. **Detection Range:**
	The range beyond the transmission range where the receiver can sense the signal’s presence but cannot decode the data.
3. **Interference Range:**
	The range where the signal is too weak to be detected or decoded by a receiver but still strong enough to interfere with other ongoing transmissions.

## Key Effects in Signal Propagation
1. Shadowing
	- Occurs when large obstacles like buildings or hills block the signal.
	- Causes a significant drop in signal strength behind the obstacle (known as a shadow region).
	- Results in slow variations in signal strength over distance.
2. Reflection
	- Happens when signals bounce off large surfaces like walls, buildings, or the ground.
	- Creates multiple copies of the signal arriving at the receiver.
	- Can either strengthen or weaken the overall signal depending on phase alignment.
3. Refraction
	- Bending of the signal as it passes through materials with different densities (e.g., from air to glass or air layers with different temperatures).
	- Can cause signal distortion and path deviation.
4. Scattering
	- Caused by small objects or rough surfaces (e.g., trees, lampposts, street signs).
	- Signal is diffused in many directions.
	- Especially significant at higher frequencies like in 5G.
5. Multi-path Propagation
	- A combination of reflection, scattering, and diffraction.
	- Multiple versions of the signal reach the receiver via different paths, each with different delays.
	- Can cause constructive or destructive interference leading to:
		- Fading (signal drops)
		- Inter-symbol interference (symbols overlap)