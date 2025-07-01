---

kanban-plugin: board

---

## To-do

- [ ] Test new SiPM boards in a consistent manner (and come up with the testing method)
- [ ] Research off-the-shelf DAQ systems with stats that we need
- [ ] Efficiency measurements using coincidence. NaI first
- [ ] Put just protons into the detector in simulation, to see if you can match the edge position from sim to measured
- [ ] Analyse the different source tests with the balloon detectors, based on the activities measured using CAPINTEC


## In Progress

- [ ] Email travel agent mark about the flights
- [ ] Include the SiPM nonlinearity into the simulation/post processing


## Complete

- [ ] Ask clint to make up next board with PSU and pulse processing on, we'll put on the rest
- [ ] Learn to use CARI-7
- [ ] Play with CAPINTEC. Andy sent the manual and Mike's activity measurements
- [ ] Patent application last 3 pages (the claim)
- [ ] Test rate limits with sources for each detector, for each code
- [ ] Analyse Andy's GRU data
- [ ] Test rate limits with function generator for both codes, going above 1 kHz if possible
- [ ] Check if the geiger was working properly with my code
- [ ] Downsampling: Make it just choose every 4 samples or whatever. But make sure it randomly chooses which sample to start on


***

## Archive

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
{"kanban-plugin":"board","list-collapse":[false,false,false]}
```
%%