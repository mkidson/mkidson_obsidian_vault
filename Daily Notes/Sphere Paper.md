# Part 1
not my problem right now




# Part 2: Characterisation of the sphere
## Response functions
- Measured at PTB
- We get L vs E out for free
	- Birks relation?
- Something about efficiency, though we don't have access to fluence so....
## Unfolding
- We can unfold the monoenergetic measurements at AMANDE
- And AmBe at nlab



# Text
To characterise the detector system, measurements of a broad beam neutron source were made at the PTB Ion Accelerator Facility (PIAF). A beam of 17 MeV protons were accelerated by a CV28 cyclotron onto a 3 mm thick Be target, producing neutrons up to 15.95(15) MeV (?) along with gamma rays. The detector was placed 11.998(1) m from the target and the neutron energy determined with time-of-flight, using the gamma rays as a time calibration. The front face of the detector was flooded with neutrons.

Neutron events were separated from gamma ray events using PSD and with neutron energy from ToF, neutron events were separated into bins of width 0.25 MeV, from 1.25 MeV to 16.5 MeV. The projection of these events into light output produced the response of the detector to neutrons of the energy in a given bin. 

The positions of the proton recoil edges, in MeVee, were determined by differentiating the $L$ spectra and fitting a negative-going Gaussian function to the result, taking the centroid value to be the position of the edge and the width, $\sigma$, to be $\Delta L$. 

Simulations with Geant4 were used to determine the neutron detection efficiency of the detector system. Incident monoenergetic neutrons were simulated from 1.00 MeV to 19.75 MeV in steps of 0.25 MeV. At each energy, 1 million neutrons were generated, uniformly flooding the front face of the detector. For each incident neutron event, the type of recoiling particle, along with the energy it deposited in the scintillator, was recorded. Energy deposited was converted to light output using the relationship determined above as well as a Gaussian broadening function, taking $\Delta L$ at a given value of $L$ as the width of the function.

