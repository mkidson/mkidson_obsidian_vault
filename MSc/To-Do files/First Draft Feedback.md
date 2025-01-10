# Chapter 1
- [ ] Overall needs a change away from aviation to more general workplace environments, of which aviation is one
- [ ] Go through Tanya's comments
- [ ] Introduction is about the "why" of the research
- [ ] Need to talk about accelerator and reactor facilities' neutron fields
- [ ] "This is where we get neutrons"
- [ ] "This is what they do to the body and electronics"
	- [ ] DNA etc
	- [ ] SEU or long-term degredation
- [ ] "This is why we need spectrometers and why in-situ is better than simulation, plus the challenges of measuring in these environments"
- [ ] ToF is the gold standard for neutron metrology, but obvi that's not possible in these environments
- [ ] Bonner spheres use unfolding, but they're bulky and complicated
- [ ] Activation is an option, but mention its drawbacks
- [ ] Solid state detectors (also unfolding, don't know much about them so might leave them out)
- [ ] Previous work
	- [ ] What happened previously that we build on? 
	- [ ] Can ignore some specifics 
- [ ] Objectives
	- [ ] We chose the size of scintillator because it's similar to cylinders that are used for 20 MeV stuff, and it was easily machinable from the stock cylinder. Could be in 
	- [ ] Basically run through the major sections
	- [ ] Remove the cosmic on air bit and put it in the conclusion and future work

# Chapter 2
- [ ] 



# Chapter 3
- [ ] Photo of n-lab
- [ ] Photo of sphere wrapped
- [ ] Photo of deconstructed and constructed
- [ ] Angular Tests
	- [ ] Collimator width
	- [ ] Change title to talk about 14.1 MeV with the STNG
	- [ ] Start with PSD plots at 3 angles
	- [ ] Then the resulting light output spectra (one plot)
	- [ ] Then the actual analysis
	- [ ] Emphasise use of STNG

# Chapter 4
- [ ] In general, stop referring to monoenergetic neutron fields. Refer to them as neutron fields with peak energy etc.
- [ ] AMANDE
	- [ ] Sphere in position at AMANDE
	- [ ] PSD plots at AMANDE
	- [ ] L plots at AMANDE (check they're ok)
	- [ ] Consider removing the paragraph that begins "The neutron light output spectra measured at IRSN AMANDE"
- [ ] PTB
	- [ ] Move mono after broad
	- [ ] Mono
		- [ ] Fix the hall picture to have white words
		- [ ] Add the detector picture
		- [ ] PSD plots (just the two)
		- [ ] L spectra (just two)
		- [ ] Show the ToF energy spectrum for 19 MeV
		- [ ] Then show L for 19 MeV only
		- [ ] Table formatted like AMANDE
			- [ ] Remove the contamination
	- [ ] Broad
		- [ ] Rename to include using ToF
		- [ ] Target thickness
		- [ ] Sphere in position instead of the diagram
		- [ ] Remove the ToF heading :(
		- [ ] Detector event pulse in legend for tof pulse plot
		- [ ] Possibly move "Figure 4.12 shows the T spectrum after the PSD and L threshold cuts were applied" closer to the plot it's referencing
		- [ ] ToF PSD plot with gamma and neutron labels
		- [ ] More care for the "Monoenergetic neutron lineshapes were created" paragraph. See notes on page
		- [ ] "Cut" in the L-E plot instead of "Slice"
		- [ ] Andy wants that BIG page plot of the lineshapes. Make it and then decide if you need to include the smaller subset one
			- [ ] Big plot needs like 30 lineshapes and they need to be offset from each other on a linear scale. 
			- [ ] Portrait mode
		- [ ] The ToF verification using AMANDE and n-lab needs to go here
			- [ ] Play with the gamma calib for AMANDE to see if it's plausible to make it fit better with the other two.
				- [ ] Test if moving up or down by the standard deviation fixes it. If that overshoots, then just pick the right number within the range to make it work
			- [ ] Then no need to mention anything, just say how nicely they agree.
			- [ ] Also include the 5 MeV and 2.5 MeV from AMANDE and see how they compare


# Chapter 5
- [ ] Title needs to include "Spectrometry" in some way. Possibly "Tests of spectrometry". Possibly even about unfolding as that's all that happens in this chapter
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
	- [ ] 