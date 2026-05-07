
- [ ] New slide 2 (high energy neutrons in general). Include neutron dose as fn of energy, so neutron spectra must be measured. Neutrons get produced by ???. Words from the IAEA meeting. Unfolding is necessary as it's not in the lab
- [ ] Slide 3: aviation environments
- [ ] Slide 4: space weather - reduce the words on the page a bit. Keep the words you're saying
- [ ] slide 6: add in "spectral capability in situ" and the blue is unfolding with measured responses
- [ ] slide 7: remove MSc, just previous work. Simplify it to say we validated below 20 MeV and are extending to higher energies
- [ ] slide 8: Extending to higher energies by increasing scintillator size, both for higher efficiency and to account for the increase in proton recoil range. Remove anything that seems like it's a PhD update
- [ ] slide 10: add in date and beam current
- [ ] 


# Introduction (the challenge (high energy neutrons))
And then why aviation

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
- Aiming to combine simulation and measurement to create response functions up to 120 MeV
- Develop autonomous signal processing and data acquisition system.
- Characterise the performance of the unfolding at high energy reference neutron facilities.
- And evaluate the stability in the environments of interest (temperature, vibration, pressure).

# Measurements at iThemba LABS
- As you know, iThemba has a high energy neutron facility, where up to 200 MeV neutrons can be produced with time of flight.
- We made measurements in September last year of up to 150 MeV neutrons with an 8 metre flight path. Here are some plots of those data.
- We were able to create response functions, but the statistics on the data meant our energy bins are quite wide (10 MeV), which won't lead to very good unfolding performance.
- So, simulation will be used to fill in the gaps and improve the energy resolution.

## Slide 11 date and beam current

# Simulation with Geant4
We're starting below 20 MeV and then extending. Remove the "below" from the title. Above 20 MeV it MUST be matched to measurement

- We are using Geant4 MC code to simulate the response functions, using the measured data as a guide for what they should look like.
- We simulate monoenergetic neutrons incident on the detector.
- Any recoil particles that are produced get tracked as they deposit their energy and each energy deposition step produces a number of photons.
	- Geant4 has a scintillation package which we are exploring, which produces the photons and tracks them as they bounce around and eventually some of them hit the photomultiplier.
	- We are also looking into converting straight from energy deposition to the "light output" measured by the acquisition system, as this reduces complexity and run time.

# summary
- Here are some of the other things that have happened and are ongoing.

# next steps
- Here are some of the things that I'm looking into doing next.

# Cosmic on air remove title. just have poster (new from website)
- We are also working to produce a version of the detector that is capable of doing some basic neutron dosimetry that can be used for the cosmic on air citizen science project.
- Here is some data from a recent flight with a prototype where we were hoping to see neutron gamma separation but no luck...

# Thanks for listening!


get from tanya
- elizabeth slides
- response function slides
- IAEA abstract thing
- new cosmic poster

