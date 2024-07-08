## Outline

1. Data in .dtz format, gets unzipped to .dat
    
    - probably just need a little script for this, could also be included in the dDAQ zip
2. .dat files get read in using read_dat, either going to lst_out in .csv form, or being final processed on the fly for really big files
    
    - For processing on the fly, some form of parallel computing needs to go on here
    - I like Tanya’s idea of 10000 events at a time, could then offload those and process them on another thread
    - Ultimately, saving L, S data for each event is not that space intensive so could be possible to just always do that. Needs to be explored
3. Processing
    
    - How do we make cuts so that high energy neutrons don’t get excluded?
    - Automated calibration? pretty tough but we can streamline it somewhat
4. Figure of Merit automation is important
    
    - I think the usual idea is to calculate FoM for a small range of L, increasing L as you go to get a “functional” dependence.