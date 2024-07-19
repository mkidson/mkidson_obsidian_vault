# Overview
- Scintillation
	- How it works
	- Organic scintillators and PSD
	- Plastic scintillators, EJ200, 299, 276
	- Maybe neutron interactions in plastic
- Photomultipliers
	- PMTs
	- SiPMs
- Unfolding
	- Methods
	- Requirements
	- Motivation for making the measurements and simulations
- Time of flight maybe?


# Theory
## Scintillation
The detection of charged particles is a problem that has been solved a number of times in a number of different ways. Scintillation detectors work by taking advantage of the ability of charged particles to continuously deposit kinetic energy in a material as they pass through it, as well as the ability of some materials to emit light at optical wavelengths when excited by those charged particles. This optical-wavelength light is much easier to capture and measure reliably compared to gamma or x-rays. The energy of the ionising particle is even able to measured, as the amount of scintillation photons produced is related to the energy deposited by the charged particle, as well as its charge-to-mass ratio.

### Organic Scintillators
There are a few types of scintillating materials that can be used for these detectors. When it comes to detecting neutrons, organic scintillators are the preferred choice due to the ability of some materials to react slightly differently to the recoiling protons that neutrons produce, compared to the electrons produced in gamma ray events.

Organic scintillators work on the principle of fluorescence: charged particles deposit their energy continuously as they travel through the medium, exciting electrons into spin 0 "singlet" states. When these electrons de-excite to the ground state, photons of wavelengths on the order of 400 nm ***check*** are emitted. This happens many times for each charged particle, but importantly each deposition of energy to a bound electron is roughly the same in magnitude, regardless of the kinetic energy of the charged particle ***check***. Because of this, the number of photons produced in a given event is directly related to the energy of the charged particle, as particles with more energy will simply undergo more interactions with the material, thus exciting more electrons.

Not all the energy deposited in the medium is converted into light. There are many different de-excitation modes that do not involve the emission of light but rather simply heat. These processes are all grouped into the term "quenching". 
