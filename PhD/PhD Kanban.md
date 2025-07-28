---

kanban-plugin: board

---

## To-do

- [ ] Test new SiPM boards in a consistent manner (and come up with the testing method)
- [ ] Research off-the-shelf DAQ systems with stats that we need
- [ ] Want to test cylinder on 4 SiPM and glued and painted sphere on SiPM in 14.1 MeV beam to try understand why the edge is so much lower for sphere on SiPM in my thesis
- [ ] PSI RedPitaya code is coming in soon as a good starting point
- [ ] Start familiarising with the RedPitaya, and then we'll talk to PSI intern about it all
- [ ] Bug Tom to get his PSD circuit and play with it
- [ ] Look at opensource code on safecast github for the M5 stack thing
- [ ] iThemba LABS September Campaign
- [ ] Test the stability of the USB vs optical inputs of QtDAQ, somehow
- [ ] Andy will pull me into the third year project to do coincidence method for activity of a source and then do efficiency of detectors
- [ ] Use MC to simulate detectors to get the geometric term for efficiency calculation
- [ ] Try with the MAXIQ board to see if there's any info I can gain from pulse length etc


## In Progress

- [ ] Email travel agent mark about the flights
- [ ] Efficiency measurements using coincidence. NaI first
- [ ] We want to test out optical photons from the centre of the sphere and see how the size of scintillator, size of flat spot, and size of collection area change the light collection
- [ ] Analyse the different source tests with the balloon detectors, based on the activities measured using CAPINTEC
- [ ] Have a look at simulating a lead cap for a cylindrical detector, to see what the neutron multiplication looks like. Might need higher energy neutrons?
- [ ] Simulate the 6 mm sipm and diff flat spots
- [ ] [[Timeline for the n-gamma counter]]
- [ ] [[n-gamma counter for Francois]]


## Completed

- [ ] Think of how best to loop through the scintillator size, notch size, and collection area size.. Do we need all three?
- [ ] [[Collect evidence that the sphere on SiPM shows better light collection than the cylinder on PMT, and that it has an isotropic response.]]
- [ ] Include the SiPM nonlinearity into the simulation/post processing
- [ ] Parameterise the flat spot size in the simulation and make the .mac file that can run it
- [ ] Put just protons into the detector in simulation, to see if you can match the edge position from sim to measured
- [ ] Email Ayesha about registration


***

## Archive

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

%% kanban:settings
```
{"kanban-plugin":"board","list-collapse":[false,false]}
```
%%