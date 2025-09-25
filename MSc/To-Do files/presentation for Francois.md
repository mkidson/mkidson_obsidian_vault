# Introduction
- My name
- Supervisors
- Starting PhD at UCT
- Cosmic-on-air

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

# Future plans 
- To create a detector that can run on its own, the PSD and spectroscopy needs to be done on-board
- We are developing an analogue circuit to integrate the pulses online and output a light output value as well as a PSD factor
- Neutrons and gamma rays separated and the neutron light output spectra saved
- In future this L spectrum can be unfolded on-device and a neutron spectrum determined
- Something like an M5Stack or a RedPitaya

# MSc detector
- 25 mm sphere of EJ-276 wrapped in PTFE tape
- Mounted to a SiPM with optical grease
- Sealed in an aluminium container
- Outputting directly to digitiser

# MSc measurements
- Measurements were made at two facilities: AMANDE in Cadarache and PIAF at PTB
- AMANDE provided monoenergetic neutron beams up to 20 MeV, which were used to validate simulations as well as the time-of-flight calibration from PTB
- PTB provided broad spectrum neutrons up to 16 MeV with time-of-flight

# Response functions
- Neutron events separated out with PSD
- Neutron events separated into energy bins of width 0.25 MeV (limited by statistics and runtime)
- "Monoenergetic" neutron responses

# Simulations using Geant4
- Geant4 is a Monte Carlo particle transport code
- We score energy deposited by recoiling particles as a result of neutron interactions
- Energy deposited to light output is determined from the ToF measurements, as well as the broadening factors
- The light output response due to any particle other than protons was unable to be calculated as it was not possible to measure L vs E
- This lead to a cutoff value at 1 MeVee since at 16 MeV, the alpha edge is still below 1 MeVee
- Simulations were used to determine detector efficiency. The simulated, broadened light output responses were used in conjunction with efficiency calculations for EJ-301