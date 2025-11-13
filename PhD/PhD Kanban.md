---

kanban-plugin: board

---

## To-do

- [ ] Test new SiPM boards in a consistent manner (and come up with the testing method)
- [ ] Research off-the-shelf DAQ systems with stats that we need
- [ ] Want to test cylinder on 4 SiPM and glued and painted sphere on SiPM in 14.1 MeV beam to try understand why the edge is so much lower for sphere on SiPM in my thesis
- [ ] Count number of neutrons in lead cap stuff in peak and not in peak, as fn of lead thickness
- [ ] Efficiency measurements
- [ ] Energy peak must be the same as the peak energy as calculated. Fudge the distance to make it work (distance in sphere)
- [ ] When looking at particle type and dose from simulation, look at high and low LET
- [ ] In repository, redo the mononenergetic list
- [ ] repository: add the calibrated cut to ambe, and make a readme
- [ ] The Q value as calculated uses the mass of hydrogen, which includes the electron. If you use a proton you get my value...
- [ ] Make notes for each slide


## In Progress

- [ ] Analyse the different source tests with the balloon detectors, based on the activities measured using CAPINTEC
- [ ] Have a look at simulating a lead cap for a cylindrical detector, to see what the neutron multiplication looks like. Might need higher energy neutrons?
- [ ] [[Build up light output spectrum with the MAXIQ SiPM board by changing the threshold]]
- [ ] Use MC to simulate detectors to get the geometric term for efficiency calculation
- [ ] Andy will pull me into the third year project to do coincidence method for activity of a source and then do efficiency of detectors
- [ ] Send time histogram to Kutullo to convert to energy to see if it looks the same
- [ ] [[MSc repository]]
- [ ] What happens to E_n when using the summed pulse? Why is it all wiggly like that?
- [ ] Email Bongi about paris accoms


## Completed

- [ ] [[Notes from ASNR]]
- [ ] Plot with CARI7 for the balloon, at least at low altitudes to calibrate CPM to dose
- [ ] Normalise timing_photon code by det volume.
	- This was weird. Idk if it worked
- [ ] Plot L-T and L-E to see where the slope at high energies is coming from in terms of L
- [ ] Put some comments in the code...
- [ ] Plot different tof options on the same axes, for with and without PSD
- [ ] Play with CFD parameters to see how that affects the time (probably shouldn't shift by 6 samples)
- [ ] Which spectra in CARI7 do we use? Feels strange to take everything except neutrons
- [ ] Get particle type out of EXPACS


***

## Archive

- [ ] The ADC read happens not in a task, but on core 1, which is where the loop() function runs but nothing else. The rest runs on core 0, with RTOS.
- [ ] [[Timeline for the n-gamma counter]]
- [ ] Test the stability of the USB vs optical inputs of QtDAQ, somehow. I think it has to do with if the USB is plugged in but the optical is being used
- [ ] Start familiarising with the RedPitaya, and then we'll talk to PSI intern about it all
- [ ] We're gonna run on the assumption that you never take the SD card out. If you do that, it'll just restart until you put it back in or turn it off.
- [ ] [[n-gamma counter for Francois]]
- [ ] Get an idea of run length needed to get certain levels of statistics for certain bin widths. Talk to Elizabeth about fluence at 8 m etc, guess an efficiency, and work it out.
- [ ] M5Stack 5V output current max
- [ ] ToF spectrum "fixed" for all three options
- [ ] Check balloon SiPM board for PSU issues. Burnt
- [ ] Balloon analysis when we have GPS data
- [ ] iTL analysis
- [ ] Email francois about deadline for UCT negotiations
- [ ] I need to be saving the time as well as Q_S and Q_L whenever the interrupt triggers
- [ ] Presentation for ASNR
- [ ] [[iThemba LABS September Campaign]]
- [ ] Check if writing to file affects interrupt response time
- [ ] Currently it's not writing the header to the file for some reason
- [ ] [[presentation for Francois]]
- [ ] Email travel agent mark about the flights
- [ ] We want to test out optical photons from the centre of the sphere and see how the size of scintillator, size of flat spot, and size of collection area change the light collection
- [ ] [[Collect evidence that the sphere on SiPM shows better light collection than the cylinder on PMT, and that it has an isotropic response.]]
- [ ] Bug Tom to get his PSD circuit and play with it
- [ ] Simulate the 6 mm sipm and diff flat spots
- [ ] Look at opensource code on safecast github for the M5 stack thing
- [ ] Make a timeline for Andy, and mostly ask Clint how quick he can make things
- [ ] Test what happens to files when power is removed, when stack is turned off, etc
- [ ] Restart new file every 30 mins or so
- [ ] Currently writing to disk after each event, lets find a way to add to a buffer and then save to disk every n second (n=5?)
- [ ] Let's save all events to a buffer for 5 seconds, then pause interrupts and write to file, then clear buffer and restart interrupts
- [ ] Any operation on log files needs to stop interrupts and then start them again
- [ ] Parameterise the flat spot size in the simulation and make the .mac file that can run it
- [ ] Find a switch for Clint to order. 3mm pitch. 3 pins, through hole mounting.
- [ ] Test what the stack does when 5V power is abruptly removed. Does it seamlessly switch to battery?
- [ ] Check the timing of events in simulation
- [ ] Check different SPI modes and frequencies on the scope
- [ ] Values for Tom: run 20250825_12
- [ ] Lead cap simulation: Just look at neutron fluence spectra, not necessarily neutron energy deposition
- [ ] I've got it working on interrupts, but while the interrupt function is called within 2 us of the interrupt being triggered, the data transfer only seems to happen after 15 us (about 12 after the interrupt function is called). Try find out if we can speed that up.
- [ ] Check if the battery charges from 5V in.. Shouldn't but might be nice
- [ ] Test the new medium sphere after glued and painted. Compare to old data
	- Old: 1.457 FoM
	- New: 1.423 FoM
- [ ] How can we power the stack
- [ ] PSI RedPitaya code is coming in soon as a good starting point
- [ ] Ask clint to make up next board with PSU and pulse processing on, we'll put on the rest
- [ ] Learn to use CARI-7
- [ ] Play with CAPINTEC. Andy sent the manual and Mike's activity measurements
- [ ] Patent application last 3 pages (the claim)
- [ ] Test rate limits with sources for each detector, for each code
- [ ] Analyse Andy's GRU data
- [ ] Test rate limits with function generator for both codes, going above 1 kHz if possible
- [ ] Check if the geiger was working properly with my code
- [ ] Downsampling: Make it just choose every 4 samples or whatever. But make sure it randomly chooses which sample to start on
- [ ] Test red detector with glue before flight
- [ ] Play with MAXIQ board to learn about flashing, and get something working for the acquisition of the balloon detector(s)
- [ ] Geant4 Scintillation package wrapping work
- [ ] Continue the downsampling tests, check with Tanya what might be going wrong
- [ ] Implement interrupts on the MAXIQ board
- [ ] Test red detector with glue after flight
- [ ] Add a lead cap to a detector and check how that affects the x-ray (<100 keV) distribution changes. Use Cs if possible, on probs the sphere for low threshold.
- [ ] Check if the attenuation makes sense given the thickness of the lead hat and the energies of the gamma rays
- [ ] Write something to an SD card and read it on the laptop
- [ ] Ask jill for PHYLAB3 access
- [ ] Make the wrapping a volume around the sphere, excluding the sipm bit
- [ ] Put just protons into the detector in simulation, to see if you can match the edge position from sim to measured
- [ ] Optimise integral lengths new SS25
- [ ] Try with the MAXIQ board to see if there's any info I can gain from pulse length etc
- [ ] Email Ayesha about registration
- [ ] Include the SiPM nonlinearity into the simulation/post processing
- [ ] Think of how best to loop through the scintillator size, notch size, and collection area size.. Do we need all three?
- [ ] Efficiency measurements using coincidence. NaI first

%% kanban:settings
```
{"kanban-plugin":"board","list-collapse":[false,false]}
```
%%