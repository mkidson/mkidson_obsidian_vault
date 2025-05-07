# What are the important metrics?
- Energy resolution of the Cs edge (std dev of the gaussian fitted to the gradient, divided by the mean)
- Figure of merit at a specific energy for AmBe (I've been using 0.4 < L < 0.8 MeVee)
- Edge position of the Cs edge, in uncalibrated units

# Important considerations
- The piece of scintillator should probably stay the same across all tests, so may need to consider the yellowing etc
- The threshold must be consistent. Not sure if this means being consistent globally or just wrt each Cs spectrum. I suppose a basic calibration can be done by measuring Cs for a bit, finding the edge (using the differential thing in QtDAQ), and then taking some constant fraction of that.
# The process
1. Measure