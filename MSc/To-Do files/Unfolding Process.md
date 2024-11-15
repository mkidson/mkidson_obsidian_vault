Trying to unfold the AmBe spectrum that I measured in Oct 2024 using response functions from PTB

# Response Functions
- 0.25 MeV energy slices
- 250 bins per response function
- All responses start at 0.5 MeVee and go up from there.
- Once the first bin on the high end reaches 0 counts, the rest are 0 above that.
- Energy slices are labelled by their centre, the first of which is at 0.625 MeV and the last of which is at 16.375 MeV
- Filename is `0_5_thresh_0_25_bin.rsp`


# Pulse Height
- Unfolding the pulse height spectrum of the small AmBe source, measured on the granite workbench in the n-lab in October 2024. 
- Filename is `L_neutrons_ambe.ph`
- It's a histogram with 250 bins going from 0 to 10 MeVee
- Bins are labelled according to their lower edge and the final bin upper edge is given in the .ph file
- I found that in order to get a result that makes any sense, the .ph file MUST include the very tippy top of the spectrum, event those bins that have 1 event in.

# Unfolding Settings

```
../phs/L_neutrons_ambe.ph                       file with data
../resps/0_5_thresh_0_25_bin.rsp   file with response functions (RF)
ambe_unf                                     name of output file
../defs/Ambeiso.flu                 file with default spectrum (DS)
0.5,6.8                      lo, hi MC E bin edges (in MC E units)
2.25,11.0                      lo, hi RF E bin edges (in MeV) 
1.0                                         chi-square factor
10000,100                                     msand,idr
3,1                        3 = use RF bin structure, 1 = dF/dE
1                               1 = use a scale factor for the DS
0                                    0 = use GRAVEL scale factor
```


![[ambe_unfolded_comparison 1.png]]