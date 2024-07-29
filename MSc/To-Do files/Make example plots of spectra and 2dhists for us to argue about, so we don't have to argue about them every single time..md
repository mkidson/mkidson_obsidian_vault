
# Event Trace
```python
plt.figure(figsize=(13,9), layout='constrained')
matplotlib.rcParams.update({'font.size': 30})

plt.plot(trace_x, trace_0, label='', lw=2, color='blue')

plt.plot(trace_x, trace_1, label='', lw=2, color='red', ls='-.')

plt.plot(trace_x, trace_2, label='', lw=2, color='green', ls='--')


plt.xlabel('Time [ns]')
plt.ylabel('Voltage above baseline [a.u.]')
plt.ticklabel_format(axis='y', scilimits=[-3,3])

# legend to be in best place to not cover trace
plt.legend(frameon=False)

# floating y-lims because baseline goes below 0
plt.xlim(left=trace_x[0], right=trace_x[-1])

plt.show()
```
![[MSc/To-Do files/attachments/ToF_event_trace.png]]


# Light Output Spectrum
```python
plt.figure(figsize=(16,9), layout='constrained')

# using auto or sqrt, depending on need
# cut at low L for a sharp threshold
hist_L = np.histogram(L_calib[neutron_cut_mask], bins='auto', range=(0.15, 7), density=False)

plt.stairs(hist_L[0], hist_L[1], lw=1.5, color='blue')

plt.xlim(left=0)
plt.ylim(bottom=0)

plt.xlabel('Light Output Parameter L [$MeV_{ee}$]')
plt.ylabel('Counts')

plt.ticklabel_format(axis='y', scilimits=[-3,3])

plt.show()
```
![[AMANDE_14_1_L_coarse 1.png]]
![[AMANDE_14_1_L_fine 1.png]]


# Neutron Energy Spectrum
```python
plt.figure(figsize=(16,9), layout='constrained')

matplotlib.rcParams.update({'font.size': 30})

iso_low_bound = 24

plt.stairs(ambe_iso[1]/np.trapz(ambe_iso[1][iso_low_bound:], ambe_iso[0][iso_low_bound:]), np.concatenate((ambe_iso[0], [11.0])), lw=2, label='AmBe ISO Spectrum', color='black', ls='-')

uncorrected_low_bound = 11

plt.stairs(ambe_unf[1]/np.trapz(ambe_unf[1][uncorrected_low_bound:], ambe_unf[0][uncorrected_low_bound:]), np.concatenate((ambe_unf[0], [11.0])), lw=2, label='Unfolded Measured\nSpectrum', color='red', ls='--')

corrected_low_bound = 11

plt.stairs(ambe_unf_corrected[corrected_low_bound:]/np.trapz(ambe_unf_corrected[corrected_low_bound:], ambe_unf[0][corrected_low_bound:]), np.concatenate((ambe_unf[0][corrected_low_bound:], [11.0])), lw=2, label='Unfolded Measured\nSpectrum Corrected', color='blue', ls='-.')

plt.xlabel('Neutron Energy [MeV]')
plt.ylabel('Intensity [a.u.]')

plt.xlim(left=0)
plt.ylim(bottom=0)

plt.legend(frameon=False, loc='upper right')

plt.show()
```
![[ambe_unfolded_comparison.png]]


# Time-of-Flight Spectrum
```python
plt.figure(figsize=(16,9), layout='constrained')
matplotlib.rcParams.update({'font.size': 30})

plt.step(hist[1], np.concatenate((hist[0], [hist[0][-1]])), where='post', lw=1.5, color='blue')

plt.xlabel('Time of Flight [ns]')
plt.ylabel('Counts')

plt.xlim(left=0)
plt.ylim(bottom=0)

plt.ticklabel_format(axis='y', scilimits=[-3,3])

plt.show()
```
![[MSc/To-Do files/attachments/ToF_T.png]]


# PSD 2d-hist
```python
plt.figure(figsize=(13,9), layout='constrained')
matplotlib.rcParams.update({'font.size': 30})

plt.hist2d(L_calib, S, bins=[512,512], cmap='inferno', norm=colors.LogNorm(vmin=1), range=((0, 8), (0.2, 0.45)))

plt.xlabel('Light Output Parameter L [$MeV_{ee}$]')
plt.ylabel('Pulse Shape Parameter S [arb.]')

plt.colorbar(label='Counts')

plt.show()

```
![[AMA_SS25C_103_L_S 1.png]]


# Other 2d-hists





# Gamma flash




# Response Functions
```python
cols_1 = plt.cm.rainbow(np.linspace(0,1,len(energy_bin_middles)))

plt.figure(figsize=(16,9), layout='constrained')
matplotlib.rcParams.update({'font.size': 30})

for h, hist in enumerate(L_histograms):

	plt.stairs(hist[0], hist[1], color=cols_1[h], lw=2, label=f'$E_n$ = {energy_bin_middles[h]:.3n}')
	
plt.xlabel('Light Output Parameter L [$MeV_{ee}$]')
plt.ylabel('Counts')

plt.yscale('log')
plt.xlim(left=0, right=10)

plt.legend(title='In MeV', frameon=False, fontsize=20)

plt.show()
```
![[ToF_response_functions.png]]




# Efficiency Curve
```python
plt.figure(figsize=(16,9), layout='constrained')

plt.errorbar(energies, tot_counts_norm[:-1], label='', color='blue', marker='^', linestyle='', ms=8)

plt.xlabel('Neutron energy [MeV]')
plt.ylabel('Neutron detection efficiency')

plt.xlim(0,21)
plt.ylim(bottom=0)

plt.legend(frameon=False, loc='lower right')

plt.show()
```


![[0_5_MeVee_threshold.png]]