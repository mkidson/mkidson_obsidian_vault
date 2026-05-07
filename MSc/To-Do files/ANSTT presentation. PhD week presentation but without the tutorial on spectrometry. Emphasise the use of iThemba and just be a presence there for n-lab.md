
- [x] New slide 2 (high energy neutrons in general). Include neutron dose as fn of energy, so neutron spectra must be measured. Neutrons get produced by ???. Words from the IAEA meeting. Unfolding is necessary as it's not in the lab
- [x] Slide 3: aviation environments
- [x] Slide 4: space weather - reduce the words on the page a bit. Keep the words you're saying
- [x] slide 6: add in "spectral capability in situ" and the blue is unfolding with measured responses
- [x] slide 7: remove MSc, just previous work. Simplify it to say we validated below 20 MeV and are extending to higher energies
- [x] slide 8: Extending to higher energies by increasing scintillator size, both for higher efficiency and to account for the increase in proton recoil range. Remove anything that seems like it's a PhD update
- [x] slide 10: add in date and beam current
- [ ] 


# The challenge: high energy neutrons
- High energy neutrons are of high relevance in many fields.
- They are produced both naturally by cosmic rays interacting with matter such as in spacecraft of the atmosphere, and also in and around high energy accelerator facilities (research and therapy).
- In all cases, there is a low energy peak around 1 MeV and a high energy around 100 MeV. 
- In all cases, the dose received by a biological or electronic system is highly dependent on the energy spectrum, so measurement of the spectrum, not just dosimetry, is required.


# Neutrons in aviation
- Of particular interest to this presentation are neutron fields present in aviation environments.
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

# For aviation
- These are the requirements and the materials and techniques we are using to meet those requirements.

# Previous work

- Previously, measurements were made at PTB in Germany and AMANDE in France, to show a working prototype for the 1-20 MeV range. 
- We showed good unfolding capability provided there was enough statistics on the measured response functions.
- Our energy range was limited on the high end by scintillator size and on the low end by constraints in the efficiency simulation.

# Research goals
- Extending prototype to higher energies by increasing scintillator size. This is for detection efficiency and to account for proton recoil range.
- Aiming to combine simulation and measurement to create response functions up to 120 MeV
- Develop autonomous signal processing and data acquisition system.
- Characterise the performance of the unfolding at high energy reference neutron facilities.
- And evaluate the stability in the environments of interest (temperature, vibration, pressure).

# Measurements at iThemba LABS
- As you know, iThemba has a high energy neutron facility, where up to 200 MeV neutrons can be produced with time of flight.
- We made measurements in September last year of up to 150 MeV neutrons with an 8 metre flight path. Here are some plots of those data.
- We were able to create response functions, but the statistics on the data meant our energy bins are quite wide (10 MeV), which won't lead to very good unfolding performance.
- So, simulation will be used to fill in the gaps and improve the energy resolution.
- Emphasise the simulation is necessary to get better energy resolution (maybe 5 MeV bins?)


# Simulation with Geant4
- We are using Geant4 MC code to simulate the response functions. First for < 20 MeV and then extending above, which is hard to do.
- Measurement MUST be used above 20 MeV to guide the simulation as the models are not well verified wrt measured data.
- We simulate monoenergetic neutrons incident on the detector.
- Any recoil particles that are produced get tracked as they deposit their energy and each energy deposition step produces a number of photons.
- Energy deposition is converted to light output for each step.
- A Gaussian broadening function is applied to each event, producing the final result.

# summary
- Here are some of the other things that have happened and are ongoing.

# next steps
- Here are some of the things that I'm looking into doing next.

# CoA poster
- We are also working on a version that can be used in a citizen science project.



# Thanks for listening!


get from tanya
- elizabeth slides
- response function slides
- IAEA abstract thing
- new cosmic poster

