# Definitions
## Absorbed Dose
Absorbed dose is defined as the amount of energy deposited per unit mass of any material. 
$$
D = \frac{d\varepsilon}{dm}
$$
Where $d\varepsilon$ is the mean energy imparted by ionising radiation to matter in a volume element of mass $dm$. We could use units of energy per mass, such as J/kg, but for convenience we define the gray (Gy) as 1 J/kg. Old units are the rad, which is 1/100th of a gray, and the erg/g, which is 1/100th of a rad.

Since different materials absorb dose in different ways and different particles deposit energy in different ways, we also use the following:

## Equivalent Dose
Equivalent dose is the absorbed dose modified by a factor accounting for the effectiveness of the radiation producing biological damage. Equivalent dose ($H_{T,R}$) is defined as:
$$
H_{T,R} = w_{R}D_{T,R}
$$
where $D_{T,R}$ is the dose delivered by radiation type $R$ averaged over a tissue or organ $T$, and $w_R$ is the radiation weighting factor for radiation of type $R$. The units are technically the same as $w_R$ is dimensionless, but for the sake of clarity we use different words in this case.

The sievert (Sv) is the SI unit, defined as the absorbed dose in Gy multiplied by the factor $w_R$. The rem is defined as the rad, multiplied by $w_R$. And similarly, 1 rem is 1/100th of a sievert.

Weighting factors change as more research is done, but they can be found from the [ICRP](https://icrpaedia.org/Radiation_weighting_factor). I have shown them below as well.

| Type of radiation                                                                      | $w_R$ |
| -------------------------------------------------------------------------------------- | ----- |
| Photons, all energies                                                                  | 1     |
| Electrons and muons, all energies (except Auger electrons<br>in emitters bound to DNA) | 1     |
| Protons, other than recoil protons, E > 2 MeV                                          | 2     |
| Alpha particles, fission fragments, heavy nuclei                                       | 20    |
| Neutrons described by an equation, see below                                           |       |
Neutrons:
$$
w_{R}= \begin{cases} 
2.5+18.2 e^{-[\ln(E_{n})]^{2}/6}, \,\;\;\;\;\;\; E_{n}< 1 \,\mathrm{MeV} \\
5.0+17.0 e^{-[\ln(2E_{n})]^2}{6}, \,\,\,\;\;\;\; 1\,\mathrm{MeV}\leq E_{n}\leq 50 \,\mathrm{MeV} \\
2.5+3.25 e^{-[\ln(0.04E_{n})]^2/6}, \;\; E_{n}> 50 \,\mathrm{MeV} \\
\end{cases}
$$
![[Pasted image 20251121123502.png]]

## Estimating Absorbed Dose in Tissue
We then need to know the absorbed dose in a specific tissue or organ. We imagine an object that has a uniform distribution of radioactive material throughout, with some activity and some type, which defines the type of emitted radiation. The object will have a mass, which we need to know.
### Absorbed Fraction $\phi$ 
Absorbed fraction, often denoted by $\phi$, is the fraction of energy released in the object, that is absorbed by the object. For photons, there is some escaping energy depending on material and size. For electrons, it's usually assumed that all the energy is deposited (sometimes called nonpenetrating emissions while photons are called penetrating radiation). 

### Generic Equation for Absorbed Dose in Tissue
$$
\dot{D} = \frac{kA\sum_{i}y_{i}E_{i}\phi_{i}}{m}
$$
where $\dot{D}$ is the absorbed dose rate (Gy/s), $A$ is activity (MBq), $y$ is number of radiations with energy $E$ emitted per nuclear transition, $E$ is energy per radiation (MeV), $\phi$ is fraction of energy emitted that is absorbed in the target, $m$ is mass of the target region, and $k$ is some proportionality constant with the relevant units.