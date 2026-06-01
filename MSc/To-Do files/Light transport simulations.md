# Things to score
- [x] Time between production and arrival at SiPM
- [x] Number of wall interactions before SiPM
	- [ ] This is saved to the fStepNumber variable and the actual number is (fStepNumber - 2)/2
- [ ] Total photons escaping around SiPM 
	- [ ] Maybe this can be done by putting a volume around the SiPM that stops and kills but adds a counter?
- [x] Photons incident on SiPM per source photon

# Things to vary
- [x] Sphere radius $R_s$
- [x] Flat spot radius $R_f$
- [x] SiPM side length $L_s$
- [ ] Scintillation source geometry



# Simulation set 1
- Photons produced directly opposite SiPM on scintillator surface
	- Check with Tanya if this is slightly inside the surface so we scatter on the backboard
	- Also check isotropic?
- $R_s$ varies over \[5, 10, 12.5, 15, 20, 25\] mm
- $R_f$ varies over (as a fraction of $R_s$) \[0.05, 0.1, 0.2, 0.3, 0.4, 0.5\] 
- $L_s$ varies over (as a fraction of $R_f$) \[0.25, 0.50, 0.75, 1.0, 1.25\]

# Simulation set 2
- Photons produced:
	- Directly above SiPM on scintillator surface
	- A line from the SiPM to the top of the sphere, randomly sampled an isotropically emitted
	- Sampled uniformly over the volume of the sphere (flat spot makes this annoying)
- $R_s$ varies over \[12.5, 25\] mm
- $R_f$ varies over the best 3 from the previous simulation (as fn of $R_s$)
- $L_s$ varies over the best 3 from the previous simulation (as fn of $R_f$)

