- Neutrons in aviation environments
- Current detector systems for those environments
- Quick note on previous work


# Introduction (the challenge)
- At aircraft cruising altitudes, the atmosphere provides less shielding than it does at sea level, leading to an increased dose received by passengers and crew. 
- The radiation is mostly secondary radiation due to interactions of cosmic rays with the atmosphere, which can be categorised into galactic cosmic rays and solar energetic particles.
- A large proportion of the dose is due to neutrons.
- The dose received by air crew is calculated only using a simulation -- there is no constant monitoring and the field isn't particularly well characterised.

# Space weather
- GCRs are a sort of background, constant source of radiation.
- SEPs, however, can vary considerably in terms of amount and energy as a result of varying solar activity. 
- Solar activity also affects the GCR component that reaches the atmosphere as the magnetic field could enhance the earth's shielding, leading to an overall decrease in e.g. proton flux.
- The flux can also increase if there are just so many particles coming from the sun.
- Most of the events that we experience and which affect the dose received at flight altitude have timescales of a few hours, so constant monitoring is necessary to be able to catch and characterise them for future simulations.

# Why measure SPECTRA
- The general shape of the neutron spectrum in aviation is like the figure shown, with peaks at 1 and 100 MeV. The shape could change during solar events.
- So measurement is necessary in these fields as the dose due to neutron radiation is heavily dependent on the the shape and intensity of that spectrum.

# Detector systems for neutron spectrometry
- The goal is to measure the energy distribution of the neutrons present in the environment.
- There are a number of techniques that can be used in the lab, but in the field there is practically only one: spectrum unfolding.
- Especially where the spectrum changes, relatively high efficiency detectors are needed, hence organic scintillators.
- To do unfolding, measurements must be made of known neutron fields and the unknown field is reconstructed from those measured response functions.

# For aviation
- These are the requirements and the materials and techniques we are using to meet those requirements.

# MSc work
- Previously, measurements were made at PTB in Germany and AMANDE in France, to show a working prototype for the 1-20 MeV range. 
- We showed good unfolding capability provided there was enough statistics on the measured response functions.
- Our energy range was limited on the high end by scintillator size and on the low end by constraints in the efficiency simulation.

# PhD goals
- Aiming to combine simulation and measurement to create response functions up to 120 MeV
- Develop autonomous signal processing and data acquisition system.
- Characterise the performance of the unfolding at high energy reference neutron facilities.
- And evaluate the stability in the environments of interest (temperature, vibration, pressure).

# Measurements at iThemba LABS
- As you know, iThemba has a high energy neutron facility, where up to 200 MeV neutrons can be produced with time of flight.
- We made measurements in September last year of up to 150 MeV neutrons with an 8 metre flight path. Here are some plots of those data.
- We were able to create response functions, but the statistics on the data meant our energy bins are quite wide (10 MeV), which won't lead to very good unfolding performance.
- So, simulation will be used to fill in the gaps and improve the energy resolution.

# Simulation with Geant4
- We are using Geant4 MC code to simulate the response functions, using the measured data as a guide for what they should look like.
- We simulate monoenergetic neutrons incident on the detector.
- Any recoil particles that are produced get tracked as they deposit their energy and each energy deposition step produces a number of photons.
	- Geant4 has a scintillation package which we are exploring, which produces the photons and tracks them as they bounce around and eventually some of them hit the photomultiplier.
	- We are also looking into converting straight from energy deposition to the "light output" measured by the acquisition system, as this reduces complexity and run time.

# PhD progress to date
- Here are some of the other things that have happened and are ongoing.

# PhD next steps
- Here are some of the things that I'm looking into doing next.

# Cosmic on air
- We are also working to produce a version of the detector that is capable of doing some basic neutron dosimetry that can be used for the cosmic on air citizen science project.
- Here is some data from a recent flight with a prototype where we were hoping to see neutron gamma separation but no luck...

# Thanks for listening!