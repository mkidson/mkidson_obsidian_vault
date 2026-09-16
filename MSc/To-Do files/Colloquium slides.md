# Neutron production
- How neutrons are produced (brielfy)
- Gamma rays are also produced
- 40% of the dose
- Peaks at 1 and 100 MeV
- Shielding isn't feasible
- Measurements of the neutron spectrum are required, and lots of them
- Current technologies are not well-suited

# Detecting neutrons
- Both neutrons and gamma rays are neutral, so no coulomb interaction.
- Both scatter or react to produce recoiling charged particles
- Recoil products deposit their energy, which produces fluorescence, with the number of photons proportional to the energy deposited by the recoil particle
- Photons scatter and eventually hit the photodetector, which produces a voltage pulse proportional to the number of photons as a function of time.
- Two questions: 
	- How do we tell the difference between neutrons and gamma rays? 
	- How do we measure the energy of the incident neutron?

# PSD (and light output units)
- Photodetector outputs a pulse like this.
- We integrate the pulse over a set time interval, which gives us a charge that is proportional to the energy deposited by the recoil particle.
- This is defined as the "light output" and we calibrate it to energy units using known gamma ray sources. So for gamma rays, L is the energy of the recoiling particle
- Because protons are heavier than electrons, the number of photons they produce per MeV of energy deposited is lower, so L, calibrated using gamma rays, is defined as MeV electron equivalent.
- Another thing that happens because protons are heavier is that they produce a larger proportion of "delayed fluorescence", meaning the same number of total photons gets produced, but some are produced later than others, and we can see that in the signal plot.
- If we also integrate our pulse over a short time interval and take the ratio of the two integrals, we can define a pulse shape parameter S
- Plotting S against light output, we see good separation of gamma ray events and neutron events. At low energies things get a bit muddy, so we define a threshold below which we can no longer discriminate.

# Neutron light output spectra
- In the region below 20 MeV, neutron interactions are dominated by elastic scatter on hydrogren. There is also the scatter on C but for reasons I won't get into now, that doesn't show up in the light output spectrum
- The elastic scatter happens as in the diagram
- For monoenergetic neutrons, we see the L spectrum shown, with a flat continuum from about 1 MeVee up to the maximum proton recoil energy, in this case 6 MeVee. We'd expect this to be 14.1 MeV but the gamma calibration means it's only 6 MeVee
- Effectively this means that on an event-by-event basis, knowing the energy of the incident neutron is impossible, looking only at the signal in the detector

# Spectrum unfolding
- So, we measure entire spectra and make an assumption that some complex measured light output spectrum is a linear combination of light output spectra corresponding to monoenergetic neutrons.
- If we can reverse engineer this equation and get the weights of the linear sum, we can determine the proportion of each energy that was present in the field when measuring.
- The quality of these monoenergetic "response functions" greatly affects the quality of the unfolding that we can do.
- There's also an efficiency term that is hiding in this equation, since we would like to know the spectrum of the neutron field present, not just the spectrum of the neutrons that interacted with the detector

# Detector design at n-lab
- As on the slide

# International measurements
- As on the slide
- AMANDE was great for verifying any measurements made at PIAF