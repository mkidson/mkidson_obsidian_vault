# Overview
- Where neutrons come from
- How they are damaging
- Energy ranges of the neutrons
- Current detector technologies
	- Moderator-based systems
	- Liquid organic scintillators
- Quick introduction to the three technologies
	- Plastic organic scintillators
	- Silicon Photomultipliers
	- Digital data acquisitions
- Direction insensitivity (yay I can finally talk about the sphere!)
# Introduction

Fast neutrons as secondary radiation from high energy charged particles are present in many environments. They have been shown to be damaging to both humans and electronics, so the characterisation and monitoring of fast neutron fields is of great importance. Of the many environments in which fast neutrons are present, aviation and spacecraft pose specific challenges for the measurement of neutron energy spectra due to the need for detectors to be robust, compact, and easy to use in extreme environments. 

The neutrons in these environments come from interactions of cosmic rays with the atmosphere in the case of aviation, and the materials that make up the spacecraft in the latter case. ***[[Details on neutron energies in space]]*** 

In the case of aviation, measurements of the neutron spectrum have been made and two distinct peaks in the fast neutron region have been identified, shown in the figure below, at around 1 MeV and around 100 MeV. In order to properly monitor these fields, the detector system must be capable of measuring neutrons from 1 to 120 MeV. 

![[Pasted image 20240717121822.png]] (Goldhagen et al. 2003)

In many applications, the characterisation of neutron fields is done with Bonner sphere systems; proportional counters that get surrounded by increasingly thicker shielding to moderate the neutrons, thus counting the neutrons at different energies ***[[Read up on Bonner sphere systems]]***. These systems work well to measure the neutron energy spectrum and are well understood as metrology devices, but they are often fairly large, fragile, and require tedious analyses, making them not particularly well-suited to the applications of interest. ***something about how the required energy sensitivity range will affect the length of analysis***

Another option for neutron spectrometry is liquid organic scintillator-based detectors, such as EJ-301/NE-213. These detectors are very well understood and used as reference detectors for neutron measurements in laboratories around the globe. They are able to discriminate between neutrons and gamma rays and are sensitive over a wide range of neutron energies, limited only by the mean path length of the recoiling protons, and thus the size of the scintillating medium. These detectors, however, are also subject to similar shortcomings as the Bonner sphere systems. The liquid scintillators themselves are extremely toxic materials and must be kept in fragile glass cases at all times. They are also usually coupled to traditional photomultiplier tubes, which run at ~1000 V and are also extremely fragile. For these reasons, liquid organic scintillators are not a good choice for this application.

Thankfully, that's not where this story ends. There exists a shining bastion of hope on the hill, in the shape of plastic scintillators and silicon photomultipliers. Eljen's EJ-276 plastic scintillator is capable of neutron-gamma ray pulse shape discrimination, which is required for any kind of neutron spectrometry as neutrons are produced in reactions that often leave nuclei in excited states, which then de-excite and produce gamma rays. It is also completely safe to handle and easy to machine into different shapes, depending on the application. In this case, a spherical scintillator shape was chosen in an attempt to make the detector system entirely insensitive to the direction of the incident radiation, as neutron fields in the environments of interest are diffuse ***check that one***. 

Silicon photomultipliers, such as the MicroFC-60035 model from ONSEMI, are new developments in photodetection technology that run at much lower voltages that traditional photomultuplier tubes (~28 V) and are much less fragile. 

These two technologies, along with digital data acquisition to reduce the bulk of the electronics systems, are the focus of this work. A new detector system for the characterisation and monitoring of neutrons in aviation and spacecraft has been developed and tested in the range of 1 - 20 MeV, as a proof of concept for a future system that will be sensitive to neutrons up to 120 MeV.