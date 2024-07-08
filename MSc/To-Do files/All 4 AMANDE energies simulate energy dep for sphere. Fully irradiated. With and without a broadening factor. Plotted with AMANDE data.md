Simulation has been done for only protons as we don’t have an easy way of converting other charged particle energy dep to light output

Broadening needs to happen on the bins. I think 5 MeV is a good one to use as there’s no alpha contribution. There is, however, a step in the data and idk why

## Steps

- [x] Simulate protons
- [ ] Use one of the data runs to get energy resolution (probably 5 MeV)
- [ ] Go from energy res to gaussian broadening factor (is that just the same number?)
- [ ] How does the gaussian broadening work? Is it a convolution or something else?
    - [ ] Look into broadening event by event
    - [ ] Need to know the energy resolution as a function of energy
- [ ] Compare to data with and without broadening