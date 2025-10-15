# Introduction
- My name
- I will be talking to you about "title"
- Supervisors

# 2
- Starting PhD at UCT
- n-lab

# Neutrons in the atmosphere
- Cosmic rays hit the atmosphere
- This causes all types of radiation, including neutrons and gamma rays
- Neutrons make up ~40% of the dose at 10 km.
- We see similar energy spectra in other workplace environments
- Impact of solar weather events on neutron dose is not well-known

# Requirements for a neutron spectrometer
- Due to the nature of the problem, there are some must-haves
- Compact, so as to be able to be used as a citizen science project, or to be used in the racks on aircraft for constant monitoring
- Safe to use/handle for similar reasons
- Must be able to discriminate between neutron and gamma ray events as practically all processes that create neutrons also create gamma rays
- Neutron energy peaks at 1 and 100 MeV, so the detector must easily be able to measure over that entire energy range
- Flexible geometries are required to be able to best suit the application
- So we are led to the following materials and components

# EJ-276
- Non-toxic and easily machined from slabs or cylinders into the required shape
- Much more robust compared to traditional liquid scintillators and their glass housings

# SiPMs
- 6 mm x 6 mm sensors that can be assembled into arrays
- Provide excellent light collection
- Run at  ~30 V, which is much lower than standard PMTs, so allows for operation outside of lab environments
- Less fragile

# Digital data acquisition
- We use the CAEN DT5730 desktop digitiser in conjunction with QtDAQ, which is software written by one of our old PhD students
- Allows for simultaneous full waveform capture on 8 channels in list mode
- Two input voltage ranges
- 500 MS/s
- These data are saved and processed offline with Python scripts
- This method is what we are using to characterise detectors and to get a better understanding of the interaction of materials etc

# n-lab
- This is the facility we have at UCT
- Produces fast neutrons in two ways
- STNG - 14.1 MeV neutrons
- AmBe - broad spectrum up to 11 MeV
- Along with the machine shop and electronics department, it allows us to quickly prototype and test devices in fast neutron beams

# MSc work
- 25 mm sphere of EJ-276 wrapped in PTFE tape
- Mounted to a SiPM with optical grease
- Sealed in an aluminium container
- Outputting directly to digitiser
- Spherical for isotropic response, as the field at aviation altitudes is diffuse
- Proof of concept to check isotropic response, light collection, etc

# Fast neutron facilities
- PIAF at PTB: Monoenergetic and broad beam neutrons up to 20 MeV, with ToF
- AMANDE in Cadarache: Monoenergetic neutrons up to 20 MeV, with ToF
- iThemba LABS in South Africa: 30-200 MeV neutrons with ToF

# MSc measurements
- Measurements were made at two facilities: AMANDE in Cadarache and PIAF at PTB
- AMANDE provided monoenergetic neutron beams up to 20 MeV, which were used to validate simulations as well as the time-of-flight calibration from PTB
	- Measured at 4 energies, without ToF
- PTB provided broad spectrum neutrons up to 16 MeV with time-of-flight
	- Measured at 2 monoenergetic energies
	- Measured broad beam for many hours 

# Pulse Shape Discrimination
- To distinguish between neutron and gamma ray events we use pulse shape discrimination
- Neutrons and gamma rays result in the light emitted by the scintillator occurring on slightly different timescales
- If we integrate the voltage pulse from the detector over a short and a long time interval, we can output a "pulse shape parameter S"
- Results in a plot such as this, where we have neutrons on the bottom and gamma rays on the top
- The further away the two loci are, the better
- On the x-axis, we have what we call the light output parameter, which is measured in MeVee
- Neutron events result in complicated energy depositions, so we "calibrate" to gamma rays
- This means to get energy of the incident neutrons, we can't just measure the light output

# Response functions
- At PTB, we measured broad beam for hours, getting incident neutron energy from ToF
- Neutron events separated out with PSD
- Neutron events separated into energy bins of width 0.25 MeV (limited by statistics and runtime)
- "Monoenergetic" neutron responses so we can unfold the unknown spectrum as a sum of known spectra

# Simulations using Geant4
- Geant4 is a Monte Carlo particle transport code
- We score energy deposited by recoiling particles as a result of neutron interactions
- Energy deposited to light output is determined from the ToF measurements, as well as the broadening factors
- The light output response due to any particle other than protons was unable to be calculated as it was not possible to measure L vs E
- This lead to a cutoff value at 1 MeVee since at 16 MeV, the alpha edge is still below 1 MeVee
- Simulations were used to determine detector efficiency. The simulated, broadened light output responses were used in conjunction with efficiency calculations for EJ-301 to produce an efficiency curve for our detector

# Unfolding broad neutron spectra
- We produced efficiency-corrected detector response functions from 2-16 MeV.
- Managed to unfold a number of spectra, most notable AmBe at the n-lab.
- Energy resolution is limited by statistics in the responses.
- Lower limit determined by efficiency calculations (alphas).
- It shows good agreement to the reference detector, which is reasonable as we can expect slight changes in spectrum due to differences in source construction, so where the source is identical, there is better agreement

# Comparison to a traditional detector system
- We compared our detector to a cylinder of EJ-276 about the same size, coupled to a traditional PMT
- We see improvements in both PSD and light output resolution
- For low energy gamma rays and neutrons, we see the output looks similar but with a slightly sharper edge
- For higher energy neutrons, we see a reduction in light output relative to the traditional system, which we believe is due to the SiPM
	- This is fine, and even possibly a benefit when we go to even higher energies, provided we calibrate the neutron response while considering this effect
- We clearly see better PSD separation

# Direction sensitivity tests
- We measured the response to monoenergetic 5 MeV neutrons at three different incident angles (show what that means)
- We see practically zero effect on the neutron light output spectrum when we change the incident angle


# MSc and poster
- That was the work done in the MSc, which produced a few posters and some talks.

# Future plans 
- Optimise detector efficiency and spectral response up to 120 MeV.
- Develop autonomous signal processing and data acquisition system.
- Characterise performance at fast- and high-energy reference neutron facilities.
- Evaluate stability under aviation-relevant temperature, vibration, and pressure conditions.
- Demonstrate capability through real-world testing and comparison with standard models and detectors.

# Next steps
- Light grey line is the important one.
- Below 1 MeV is interesting, particularly at eV scales. There are new scintillators being developed for that (boron- / lithium-doped)
- Above 20 MeV is the current focus. 
- Simulations are not experimentally verified above 20 MeV, so we must either measure a lot, or work on changing that.

# iThemba LABS
- We're making use of the facility on our doorstep
- Can get up to 200 MeV neutrons.
- We recently measured with 150 MeV neutrons, to try do the same thing as at PTB, to measure response functions.
- We have some preliminary results from the reference detector.

# PhD progress
- Tested the new version (bigger to handle higher energies) at iThemba LABS. Analysis is ongoing but looks promising.
- Simulation work is ongoing, to improve high energy behaviour and to use photon transport to properly measure light collection behaviour.
- A new board is being developed to handle the pulse processing, leading to PSD straight off the board, no need for a digitiser.
	- First step towards a device that can be operated without a laptop etc.
- We have developed a more lightweight acquisition system on an ESP32 microcontroller that can't do spectrometry yet, just counting.


# PhD goals
- Create a full prototype from the aforementioned boards and scintillators.
- Lab testing of vibration, pressure, temperature effects.
- Measured neutron L spectra -> unfolded neutron energy spectra
- Measure alongside reference detectors (Francois)
- Fly it! On aircraft, balloons, satellites(?)

# Cosmic on air
- We're aiming to make something that can be used in the cosmic-on-air project, to cover the neutron dose.
- Not necessarily a spectrometer, especially if it should be accessible to the public

# Balloon measurement
- We worked with a company called MAXIQ to put a version of our detector system onto a NASA high altitude balloon
- Device cut out mid-way and then reconnected
- Busy analysing data but it should be useful
