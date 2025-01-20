# Overall stuff
- [ ] Double check that all PSD plots and all L plots have consistent wording

# Chapter 1
- [x] Overall needs a change away from aviation to more general workplace environments, of which aviation is one
- [x] Get some better references for the intro
- [x] Go through Tanya's comments after rearranging
- [x] Introduction is about the "why" of the research
- [x] Need to talk about accelerator and reactor facilities' neutron fields
- [x] "This is where we get neutrons"
	- [x] Also gamma rays at the same time
- [x] "This is what they do to the body and electronics"
	- [x] DNA etc
	- [x] SEU or long-term degredation
- [x] "This is why we need spectrometers and why in-situ is better than simulation, plus the challenges of measuring in these environments"
- [x] ToF is the gold standard for neutron metrology, but obvi that's not possible in these environments
- [x] Bonner spheres use unfolding, but they're bulky and complicated
- [x] Activation is an option, but mention its drawbacks
- [x] Solid state detectors (also unfolding, don't know much about them so might leave them out)
- [x] Previous work
	- [x] What happened previously that we build on? 
	- [x] Can ignore some specifics 
- [x] Objectives
	- [x] We chose the size of scintillator because it's similar to cylinders that are used for 20 MeV stuff, and it was easily machinable from the stock cylinder. Could be in 
	- [x] Basically run through the major sections
	- [x] Remove the cosmic on air bit and put it in the conclusion and future work

# Chapter 2
- [ ] Go through Tanya's notes after rearranging
- [x] Organic scintillators 
	- [x] gets the neutron (and gamma) interaction physics as part of it, maybe before the anthracene response pictures
		- [x] Show cross-sections
		- [x] The components of L plot doesn't go there, but rather after talking about light output units, before PSD
	- [x] Anthracene response becomes one figure, with an inset for the low energy electrons. Put the dots into the x values
	- [x] Compare liquid to plastic scintillator
- [x] Photomultipliers
	- [x] Don't start general, just go straight in with the PMTs
	- [x] SiPMs
		- [x] Maybe put a circuit diagram in there
		- [x] Get more physics-y. This is a physics master's after all
		- [x] Get rid of the quench cycle plot. Just explain it better in words
		- [x] Why do we operate at an overvoltage rather than just over the breakdown? (because of gain)
		- [x] Show an example pulse from a SiPM
- [x] Light output units and PSD gets combined into "pulse processing" where we can show a gamma and neutron lineshape
	- [x] The components of L plot (neutrons) goes here with explanation
	- [x] Then a PSD explanation
		- [x] PSD pulse image could be one of the Comrie ones that includes the cumulative integral
- [ ] Unfolding and ToF combine into one, with ToF first, called Neutron spectroscopy
	- [ ] Need a reference and figure for the scattering probability distribution (not in knoll)
	- [x] ToF is the gold standard for neutron spectrometry. It can be used to produce response functions
	- [ ] Which can be used in unfolding analyses, which are more appropriate for in-field measurements
	- [ ] More detail in the ToF procedure. Tanya wants that fuckin weird figure in that I don't understand



# Chapter 3
- [ ] Photo of n-lab
- [ ] Photo of sphere wrapped
- [ ] Photo of deconstructed and constructed
- [ ] Check the labels of t_long and t_short etc to fit those used in chapter 2
- [ ] Angular Tests
	- [x] Collimator width
	- [ ] Change title to talk about 14.1 MeV with the STNG
	- [ ] Start with PSD plots at 3 angles
	- [ ] Then the resulting light output spectra (one plot)
	- [ ] Then the actual analysis
	- [ ] Emphasise use of STNG

# Chapter 4
- [ ] In general, stop referring to monoenergetic neutron fields. Refer to them as neutron fields with peak energy etc.
- [x] AMANDE
	- [x] Sphere in position at AMANDE
	- [x] PSD plots at AMANDE
	- [x] L plots at AMANDE (check they're ok)
	- [x] Consider removing the paragraph that begins "The neutron light output spectra measured at IRSN AMANDE"
- [ ] PTB
	- [x] Move mono after broad
	- [ ] Mono
		- [ ] This section kinda flops a bit
		- [ ] Change the title to something about peak energy idk
		- [x] Fix the hall picture to have white words
		- [x] Add the detector picture
		- [x] Target thicknesses 
		- [x] PSD plots (just the two)
		- [x] L spectra (just two)
		- [x] Show the ToF energy spectrum for 19 MeV
		- [x] Then show L for 19 MeV only
		- [x] Table formatted like AMANDE
			- [x] Remove the contamination
	- [ ] Broad
		- [x] Rename to include using ToF
		- [x] Target thickness
		- [x] Sphere in position instead of the diagram
		- [x] Remove the ToF heading :(
		- [x] Detector event pulse in legend for tof pulse plot
		- [x] Possibly move "Figure 4.12 shows the T spectrum after the PSD and L threshold cuts were applied" closer to the plot it's referencing
		- [x] ToF PSD plot with gamma and neutron labels
		- [ ] More care for the "Monoenergetic neutron lineshapes were created" paragraph. See notes on page
		- [x] "Cut" in the L-E plot instead of "Slice"
		- [ ] Andy wants that BIG page plot of the lineshapes. Make it and then decide if you need to include the smaller subset one
			- [ ] Big plot needs like 30 lineshapes and they need to be offset from each other on a linear scale. 
			- [ ] Portrait mode
		- [x] The ToF verification using AMANDE and n-lab needs to go here
			- [x] Title change?
			- [x] Play with the gamma calib for AMANDE to see if it's plausible to make it fit better with the other two.
				- [x] Test if moving up or down by the standard deviation fixes it. If that overshoots, then just pick the right number within the range to make it work
				- [x] Up by two bin widths was perfect
			- [x] Then no need to mention anything, just say how nicely they agree.
			- [x] Also include the 5 MeV and 2.5 MeV from AMANDE and see how they compare


# Chapter 5
- [x] Title needs to include "Spectrometry" in some way. Possibly "Tests of spectrometry". Possibly even about unfolding as that's all that happens in this chapter
- [ ] Some introductory words and then straight into unfolding
- [ ] First section is UMG and how to work it
	- [ ] Tanya needs to read this bit to confirm it all
- [ ] Simulation with Geant4
	- [ ] Reference for Geant4
	- [ ] L vs E rename x-axis to be recoil proton energy
	- [ ] More about the deviation at high L (idk man)
	- [ ] Just "Light output spectra" as a section title
	- [ ] Produce an efficiency curve
- [ ] Now, we use the NRESP response functions to scale the efficiency curve to something in fluence units, and extend it down to like 1 MeV hopefully
- [ ] Remove the lone light output spectrum
- [ ] Then we get the unfolded monoenergetic guys, with sensible vertical axes
- [ ] Then the AmBe unfolding
	- [ ] Send unfolding things to Tanya so she can check I'm doing it right
	- [ ] We're unfolding as low energy as possible
	- [ ] The response functions we use must be normalised to unit area, then scaled by the efficiency
	- [ ] Compare to ISO and to the n-lab AmBe measurement made with EJ-301


# Chapter 6
- [ ] Convince yourself that there is a linear growth in the deficit as pulse size increases
- [ ] Look at the difference in L for low to high energy neutrons between PMT and SiPM
- [ ] 