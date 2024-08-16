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
- [ ] Time of flight


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






## Unfolding
The primary interaction channel for neutrons in organic scintillators is (n,p) elastic scattering, where the energy of the recoiling proton depends on both the incident neutron energy and the scattering angle. Because of this, the energy of the neutron cannot be inferred from the amount of scintillation light produced in a neutron event. This restricts the methods available to be able to do neutron spectrometry with organic scintillator-based devices to practically one option: spectral unfolding.

Spectral unfolding is an analysis technique that produces the energy spectrum associated with a given light output spectrum. It is not interested in the individual events and their light output, only the shape of the spectrum as a whole. This of course means that any input light output spectrum needs to have enough events for the method to have good enough statistics to work with. 

The method works by assuming that the light output spectrum associated with an incident neutron field consisting of a number of different energies is simply the linear combination of light output spectra associated with monoenergetic neutron fields:

$$
z_{i} = \sum\limits_{j=1}^{m}R_{ij}\phi_{j}.
$$
Here the $z_i$ are the bin heights of the complicated light output spectrum, the $\phi_j$ are the numbers of incident neutrons of a given energy indexed by $j$, and the $R_{ij}$ are the bin heights (indexed by $i$) of the light output spectrum associated with the neutrons with energy indexed by $j$. In the context of determining neutron energy, the unknown is of course $\phi_j$, which is non-trivial to determine from the two known quantities: the inversion of $R_{ij}$ cannot be done analytically ***check this*** so needs to be done by some other method.

In order to do this inversion, then, a piece of software called UMG is used. UMG has two slightly different methods of unfolding available to it but both use an iterative approach where they compare the measured spectrum to a spectrum created by "refolding" the data using the equation above by determining a $\chi^2$ value.

The first code is called GRAVEL, which does a gradient descent on the $\chi^2$ as a function of the parameters $\phi_j$. This approach is fairly robust to initial conditions and can generally find a solution. 

The other is called MAXED, which uses a Monte Carlo metropolis method to search the $\phi_j$ parameter space. This is very sensitive to initial conditions and performs best with a first guess of the spectrum being the solution found using GRAVEL. In this way, the two codes work together to find a good solution.
