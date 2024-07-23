# Overview
- [ ] Development of the detector
	- [ ] Wrappings
	- [ ] Shapes
	- [ ] SiPM boards?
- [x] Design


# Design
The EJ-276 was machined into a sphere with diameter 25 mm. A flat spot was milled on the sphere with the diameter of 9 mm. See the diagram below. This piece of scintillator was wrapped in PTFE tape (Teflon, plumber's tape, etc) to create a diffuse, white wrapping. This allows for any light produced in the scintillator that reaches the edges to be diffused, giving it a better chance of reaching the photomultiplier. This is in contrast to having a reflective wrapping, as tends to be done for the face of cylindrical scintillators that sits opposite the photomultiplier. 

The scintillator was then wrapped in a layer of tinfoil, in order to support the more flimsy PTFE tape and provide an opaque backing for better diffuse reflection rather than transmission. After wrapping, the scintillator was placed on the 6 mm x 6 mm SiPM sensor after applying ***the goo***. Best practice is to apply a small amount to both surfaces, let it settle for a minute, and then press the two faces together. Alignment of the sphere to the SiPM was done using spacers in the aluminium casing. 

Parts were designed in CAD to be 3D printed and fit into a small aluminium casing. One held the SiPM board in place in the bottom piece, centring the sensor in the casing, and a second was placed in the dome-shaped top piece to centre the sphere. The sphere was placed in the top piece and the two pressed together, taking care to make sure the flat spot on the sphere was as parallel to the SiPM sensor as possible before the two met. Small bolts screwed from the top piece into the bottom, with washers to keep them together and try remove any opportunity for light to leak in through any small slits. Some Prestik (tm) was used to cover any remaining gaps, such as those caused by the connectors sticking out the side.

