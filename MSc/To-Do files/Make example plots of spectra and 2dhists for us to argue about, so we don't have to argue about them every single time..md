
# Event Trace
```python
plt.figure(figsize=(13,9), layout='constrained')

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




# Neutron Energy Spectrum




# Time-of-Flight Spectrum
```python
plt.figure(figsize=(16,9), layout='constrained')

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





# Other 2d-hists





# Gamma flash




# Response Functions
```python
cols_1 = plt.cm.rainbow(np.linspace(0,1,len(energy_bin_middles)))

plt.figure(figsize=(16,9), layout='constrained')

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

