Trying to unfold the AmBe spectrum that I measured in Oct 2024 using response functions from PTB

# Response Functions
- 0.25 MeV energy slices
- 250 bins per response function
- All responses start at 0.5 MeVee and go up from there.
- Once the first bin on the high end reaches 0 counts, the rest are 0 above that.
- Energy slices are labelled by their centre, the first of which is at 0.625 MeV and the last of which is at 16.375 MeV
- Filename is `0_5_thresh_0_25_bin.rsp`

Using the old response functions (`cut_0_5_threshold_modified`), I still get shit unfolding results. 
I think it might have to do with the cut I made on the AmBe ph spectrum.
The new response functions are good as long as I use the AmBe measurement from before



# Pulse Height
- Unfolding the pulse height spectrum of the small AmBe source, measured on the granite workbench in the n-lab in October 2024. 
- Filename is `L_neutrons_ambe.ph`
- It's a histogram with 250 bins going from 0 to 10 MeVee
- Bins are labelled according to their lower edge and the final bin upper edge is given in the .ph file
- 