Neutrons are simulated incident on the detector volume, flooding the volume. If an event occurs within the volume, a proton, alpha particle(s), deuteron, or carbon nucleus is produced (or some combination of these). These will be called "recoil particles". 

Whenever a recoil particle starts and ends a step within the detector volume, it will deposit some energy. We use the `G4VSensitiveDetector` module to process the energy deposition and turn it into light output. 

The start of the process is getting the recoil particle energy, and if it is below 1 eV, we stop the track and move on. This is to avoid any thermal neutron problems. Then, we determine what the particle type is. Each particle type has a unique conversion between energy deposited and light output, so we have functions defined, with parameters determined from fitting. The functions are as follows:

$$
L_{p}(E_{p)}= \alpha + \beta E_{p} + \gamma E_{p}^{2} + \delta E_{p}^{3} + \epsilon E_{p}^{4}+ \zeta E_{p}^{5} \\
$$
$$
L_{\alpha}(E_{\alpha})=

$$


At each step in the simulation, the recoil particle deposits some energy. The simulation records the energy of the particle before and after each step.

In NRESP, the energy deposition to light output is handled differently for each particle, using the following functions.
