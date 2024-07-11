# Don't forget to do the submission form thing, for supervisor signature etc.

# Introduction
Neutrons as secondary radiation from high energy charged particles are present in many environments and pose a great risk biologically and to electronics and machinery. Two of those environments are at aviation altitudes, due to spallation in the atmosphere from cosmic rays, and in proton therapy centres, where interactions of the protons with the materials present result in fast neutrons. The characterisation of these fields using a neutron spectrometer is clearly of great importance.

In both these cases, the energy spectrum of the neutrons is dominated by two peaks. One is on the order of 1 MeV, while the other is around 100 MeV. For a neutron spectrometer to suit the application of characterisation and monitoring of these fields, it must be sensitive over the entire range. For a Bonner sphere-based detector system, this requires a large number of repeat measurements with different moderating spheres, and a complicated analysis. Consequently, a logical choice for this application would be organic scintillator-based detectors. Industry standard scintillators like the liquid NE213/EJ-301 are capable of neutron-gamma ray pulse shape discrimination and are sensitive to a wide range of incident neutron energies, but since they need to be kept in glass containers and are made from extremely toxic and dangerous materials, they don't lend themselves to applications outside of strict laboratory environments. This along with the fact that they are usually coupled with a photomultiplier tube that is fragile and operates at ~1000 V, mean that liquid organic scintillators are also not a great choice for this application.

This work aimed to explore three new technologies and how they can be used to create new detectors for neutron spectrometry that are suitable for use in extreme conditions, are much safer to handle, and hopefully lead to more compact detector systems for collaboration with Cosmic on air. Those new technologies are: Eljen EJ-276 PSD-capable plastic scintillator, ONSEMI MicroFC-60035 silicon photomultipliers, and digital data acquisition.


# Detector Concept
- EJ-276
- SiPMs from ONSEMI
- digital data acquisition
## Plastic Scintillator
To replace the organic liquid scintillator, Eljen's EJ-276 plastic scintillator was used. As seen in the table below, it has about 2/3 the light output of the liquid EJ-301 as well as a lower scintillation efficiency, leading to worse energy resolution. This trade-off is acceptable though, as it is completely safe to handle and can be easily machined into whatever geometry is required for the application.

- Want the table comparing the stats between EJ-301 and EJ-276.

The sensitivity of the detector system to the direction of the incident radiation depends almost entirely on the geometry of the scintillating medium. Below is an example of a detector system that is made of long, thin prisms of the scintillator, set up in such a way that the direction of the incident radiation is able to be determined. On the other end of the spectrum would be something like the standard cylindrical shape. Different applications will necessitate different requirements of the sensitivity of the detector system to the direction of the incident radiation, so the flexibility of EJ-276 to accommodate this is a strength.


- Picture of Angus's detector with 4 scints

## Silicon Photomultipliers
The plastic scintillator is coupled directly to the 6 mm x 6 mm silicon photomultiplier (SiPM) from ONSEMI. These operate at 28.5 V - much lower than their traditional counterparts. These SiPMs have a fast and slow output, where the fast is usually used for trigger and timing applications, and the slow is used for pulse height/pulse integral (need to reword this for sure) applications. For this work, only the slow output was used. This resulted in a slower detector response than the traditional PMTs, but there is no effect on the quality of the data.

## Digital Data Acquisition
Lastly, a CAEN DT-5730 desktop digitiser was used to record the event pulses for offline analysis. The DT-5730 has 8 channels, each with 14 bit ADCs. It runs at 500 MS/s and has a variable input voltage range, with the choice between 2.0 Vpp and 0.5 Vpp. It connects by USB or optical link to a PC and interfaces with a bespoke software written by a former UCT PhD student, called QtDAQ. QtDAQ (shown below) is able to do a lot of the analysis online, but for the sake of iteration and flexibility, in this case it was used simply to record each incoming pulse and save them to a file. QtDAQ triggers when an event trace goes above a specified voltage threshold, then captures a specified number of samples (2 samples per ns), with a specified window before the trigger time being captures, for baseline calculations. After measurement, the data are analysed offline in Python.

# Pulse Shape Discrimination
Neutron radiation fields are practically never present without an accompanying gamma ray field. This is due to the fact that fast neutrons are created in nuclear reactions, which more often than not leave the mother nucleus in an excited state, resulting in an emitted gamma ray. For this reason, it is necessary to be able to distinguish between neutron and gamma ray events in the detector systems. To do this, the scintillator needs to be produced in such a way that the time-scale on which the scintillation light is produced depends slightly on the mass of the charged particle that is ionising the material itself. 

For organic scintillators, heavier ionising particles have a higher chance of exciting the fluorescent material into triplet states, rather than singlet states. These triplet states take slightly longer to de-excite, resulting in a slightly different shape of event pulse. See figure below for the difference between a neutron and gamma ray event of the same pulse integral. Taking the integral of the event pulse over two intervals, named $t_{short}$ and $t_{long}$, and taking the ratio results in a pulse shape parameter S. Figure below shows the different loci produced from a mixed radiation field such as from AmBe.

- n-gamma PSD event trace plot
- classic PSD plot

# MeVee units
On the x-axis of the figure above is the unit $MeV_{ee}$, or MeV electron equivalent. When gamma rays are incident on the scintillation medium, they produce recoil electrons through Compton scattering. For inorganic scintillators other processes also contribute. These electrons travel through the scintillator and ionise the fluorescent material, which then de-excites and emits light that gets collected by the SiPM. Since it is relatively easy to calibrate a scintillator with gamma ray sources, due to them being commonplace in most nuclear research labs, the electron is chosen as the standard to which all other recoiling particle is compared. 

Due to Bethe-Bloch and Birks' Law, particles with different masses and different charges will ionise the medium in different ways that are not easily linearly related to each other. Because of this, the energy deposition of a particle that isn't an electron cannot be simply equated to an electron's because they produced the same amount of scintillation light. This is the reason for the $MeV_{ee}$ unit for light output.

# Unfolding
EJ-276 scintillator is made of hydrogen and carbon atoms, with a roughly equal number density. Because of this, the interactions of neutrons with the material is split between two categories: (n,p) elastic scatter on hydrogen, and inelastic scatter on carbon, resulting in an alpha particle and a 9-Be nucleus, which either deposits energy itself or decays into two more alphas. Elastic scatter on carbon is also observed, but the recoiling nucleus is so massive that the light output for those events is greatly reduced (Bethe-Bloch) and practically never goes above the trigger threshold. The same is true for the recoiling 9-Be nuclei. 

This means that there are effectively 3 reactions that produce enough light to actually be detected: (n,p) elastic scatter on hydrogen, 1 alpha (& 9-Be), and 3 alphas. These three are dominated by elastic scatter on hydrogen, which is where the vast majority of the usable data come from. Below is a diagram showing the kinematics of the (n,p) elastic scatter. Note that the proton can recoil with any angle $-\pi/2 \leq \theta \leq \pi/2$, with the cross-section being about equal for all angles. This means that the energy of the recoiling proton cannot necessarily carry any information about the energy of the incident neutron. On an event-by-event basis, the energy of the incident neutron cannot be known. 

- Scattering diagram from Knoll

Since the intention of this work is to create a neutron spectrometer, knowing the energy of the neutrons incident on the detector is quite important, so another technique must be used to determine this information. Instead of finding the energy event-by-event, the energy of the spectrum as a whole is determined using a technique called spectral unfolding, which assumes that the measured light output spectrum of a neutron field with a complex combination of neutron energies is simply the linear combination of light output spectra corresponding to monoenergetic neutrons. 

$$ 
z_{i} = \sum\limits_{j=1}^{m}R_{ij}\phi_{j}
$$

Then, with $z_i$ being the measured neutron light output spectrum, $R_{ij}$ being a matrix containing the monoenergetic light output responses, and $\phi_j$ being the actual energies of the neutrons detected, the above equation can be deconvolved or "unfolded", to determine the energy spectrum of the neutrons detected. This unfolding process is done using a code called GRAVEL or MAXED and works by doing a gradient descent on the parameters in the case of GRAVEL, or a Monte Carlo-based search of the parameter space in the case of MAXED.

Of course, the spectrum of the neutrons detected is not necessarily the same as the spectrum of neutrons incident on the detector, as detection efficiency varies with neutron energy. As such, the detection efficiency must be considered when doing unfolding, which leaves the equation looking like

$$
z_{i} = \sum\limits_{j=1}^{m}R_{ij}{\color{red}\epsilon_j}\phi_{j},
$$

where $\epsilon_j$ is the efficiency of detecting a neutron of a given energy $\phi_j$. With this modification, the unfolding process will produce a neutron energy spectrum corresponding to the *incident* neutrons, as opposed to just those detected. 

# Time of Flight


# Simulation with GEANT4

# Measurements


