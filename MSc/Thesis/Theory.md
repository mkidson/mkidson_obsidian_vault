# Overview
- [ ] Scintillation
	- [ ] How it works
	- [ ] Organic scintillators and PSD
	- [ ] Plastic scintillators, EJ200, 299, 276
	- [ ] Maybe neutron interactions in plastic
- [ ] Photomultipliers
	- [ ] PMTs
	- [ ] SiPMs
- [ ] Unfolding
	- [ ] Methods
	- [ ] Requirements
	- [ ] Motivation for making the measurements and simulations
- [ ] Time of flight maybe?


# Theory
## Scintillation
The detection of charged particles is a problem that has been solved a number of times in a number of different ways. Scintillation detectors work by taking advantage of the ability of charged particles to continuously deposit kinetic energy in a material as they pass through it, as well as the ability of some materials to emit light at optical wavelengths when excited by those charged particles. This optical-wavelength light is much easier to capture and measure reliably compared to gamma or x-rays. The energy of the ionising particle is even able to measured, as the amount of scintillation photons produced is related to the energy deposited by the charged particle, as well as its charge-to-mass ratio.

### Organic Scintillators
There are a few types of scintillating materials that can be used for these detectors. When it comes to detecting neutrons, organic scintillators are the preferred choice. This is due to both the high hydrogen content, meaning neutrons can deposit (up to) all their energy in (n,p) elastic scatter interactions, and the ability to make materials that react slightly differently to the recoiling protons, compared to the electrons produced in gamma ray events. The carbon in the organic materials is also often involved in neutron interactions, producing 1 or 3 $\alpha$ particles.

Organic scintillators work on the principle of fluorescence: charged particles deposit their energy continuously as they travel through the medium, exciting electrons into $n$ spin 0 "singlet" states $S_{n0}$. When these electrons de-excite to the ground state, photons of wavelengths on the order of 400 nm ***check*** are emitted. This happens many times for each charged particle as it slows down in the medium, and despite the free electrons being excited to a range of singlet states, photon emission has only been observed for the transition between the first excited state $S_{10}$ and the ground state $S_{00}$. Any higher energy excited state rapidly undergoes radiation-less internal conversion to the first excited state. While this means that a single photon can be produced by a range of energy depositions, the majority of the excitations tend to be to $S_{10}$. ***check this shit. why would it tend to be only the first state? this isn't backed up but it seems to be implied???*** 

Because of this, the number of photons produced in a given event is assumed to be directly related to the energy of the charged particle, as particles with more energy will simply undergo more interactions with the material, thus exciting more electrons. 

Radiation-less internal conversion, along with other de-excitation modes that don't involve the emission of light (e.g. heat), are all grouped under the term "quenching". Effectively this covers all processes that result in a more complicated conversion from light output to energy deposited.


### Plastic Organic Scintillators



### Neutron Interactions in Plastic/Organics