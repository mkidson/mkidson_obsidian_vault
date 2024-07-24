# Overview
- [ ] AMANDE
	- [ ] Motivation for monoenergetic
	- [ ] Actual measurements
- [ ] PTB
	- [x] Motivation (ToF)
	- [x] Measurements
	- [x] How ToF works

# Measurements
## PTB PIAF
The creation of response functions for unfolding requires a source of monoenergetic neutrons covering a wide range of energies, preferably with regular spacing between each energy. Instead of producing monoenergetic neutrons at all the required energies, time-of-flight was used to determine the energies of neutrons from a broad beam neutron source, after which events were split up according to their energy to determine their light output responses. Below is a description of the process by which the neutron energy is calculated.

### Time of Flight
The energy of a neutron, in this context, is entirely its kinetic energy. If the experiment was set up in such a way that the distance travelled by each neutron is known, and the time taken for each neutron to travel that distance could be calculated, then the kinetic energy can be found simply from the velocity of the neutron:

$$
E_n = m_n \left(\frac{1}{\sqrt{1-\frac{v_n^2}{c^2}}} - 1\right)
$$

The PTB PIAF cyclotron accelerates protons towards a thick Be target at a frequency of 959.60 kHz. Each time a new particle is accelerated, the system sends a pulse to some electronics and eventually to the digitiser to be captured alongside the event pulses. These are called RF pulses ***why??*** Not every accelerated particle results in an event in the detector, simply due to the fact that the detector is covering such a small relative solid angle. Because of this, the digitiser is set to trigger on events, not on the RF pulses.

When an event triggers the digitiser to record, it records both the event trace and the RF pulse. An example trace is shown in the figure below. In a perfect world, the RF pulse would occur before the event pulse and the time that the neutron was in flight would simply be the difference in time between the two pulses. Unfortunately, the RF pulses go through a number of processing steps before reaching the digitiser and cable lengths need to be considered, so it's just too a bit too much and too fiddly to get right. Instead, a calibration step is needed.

The difference in time between event and RF pulse is still calculated, but there are sometimes two RF pulses in the captured window, so the last pulse in the window is used. The RF pulses are also always after the event pulse, at least in this experiment's case, so the final time difference will need to be multiplied by $-1$. 

![[MSc/Thesis/attachments/ToF_event_trace.png]]

Calculating this uncalibrated time difference for each event produces the histogram in the figure below. The main locus is primarily neutrons, with some contamination from gamma rays, and the large, sharp spike around 1500 ns is the majority of the gamma ray events. Since gamma rays always travel at the same speed, they're expected to always arrive at the detector in at the same time relative to the RF pulses. As a result, this gamma "flash" is seen, and can be used to calibrate the technique.

![[ToF_T_uncalibrated.png]]

Below is a zoomed-in version of the gamma flash. To the right of the peak are events that arrive "early" and to the left are events that arrive "late". The reason for the slight asymmetry in the peak -- a gaussian is the expected shape here -- is the fact that a thick target is used for this experiment, meaning some of the protons are slowed down by scattering interactions before being captured ***citation needed on if that's the process that happens*** in the reaction that results in neutrons or gamma rays. Because of this, there can be a slight difference in timing between an event that happens without scatter and one that happens after one or more scattering events. 

![[ToF_Gamma_Peak.png]]


The "early" events are expected to behave like a gaussian though, so the peak can be found by fitting to that side of the peak. This provides a point in time that can be calibrated to. The distance from target to detector was measured to be 12.0 m, so the time at which gamma rays are expected to arrive is 

$$
t_\gamma = \frac{12 \;m}{299792458 \;m s^{-1} \cdot 10^{-9} \;s\,ns^{-1}} = 40.02769142378\;ns.
$$

The figure 2 above can then be calibrated by multiplying by $-1$ and shifting all events so the gamma flash peak aligns with $t_\gamma$, providing the figure below.

![[ToF_T.png]]

This is the calibrated time of flight for each event in the detector. Neutrons can be separated out using pulse shape discrimination and a velocity found for each event. Finally the neutron energy can be found, shown below.

![[ToF_E.png]]

