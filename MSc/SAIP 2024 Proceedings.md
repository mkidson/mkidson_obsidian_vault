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
Lastly, a CAEN DT-5730 desktop digitiser was used to record the event pulses for offline analysis. The DT-5730 has 8 channels, each with 14 bit ADCs. It runs at 500 MS/s and has a variable input voltage range, with the choice between 2.0 Vpp and 0.5 Vpp. It connects by USB or optical link to a PC and interfaces with a bespoke software written by a former UCT PhD student, called QtDAQ. QtDAQ (shown below) is able to do a lot of the analysis online, but for the sake of iteration and flexibility, in this case it was used simply to record each incoming pulse and save them to a file. QtDAQ triggers capture when an event trace goes above a specified voltage threshhold





# Pulse Shape Discrimination

# Time of Flight

# Unfolding

# Simulation with GEANT4

# Measurements


