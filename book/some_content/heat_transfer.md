## Types of heat transfer
Heat transfer deals with the transfer of the thermal energy between the environment and the spacecraft and between spacecraft elements. It is either expressed as a heat flow or as a heat flux. 

**Heat Flow**  is the transfer of thermal energy (heat) per unit time. This is denoted with the symbol a capital Q. This is a scalar and expressed in Watt (W=J/s).

**Heat Flux** is the transfer of thermal energy (heat) per unit time per unit area. This is denoted with a Φ. The heat flux is a vector and expressed in W/m2 (=J/s/m2).


Three mechanisms of heat transfer are:

*Conduction* is the transfer of heat through molecular interactions. It occurs at contact points and within solid parts. This type of heat transfer is important at a local level within spacecraft systems.  

*Convection* is the transfer of heat through the movement of gases or fluids. Although convection does not occur naturally in the vacuum of space, it can still be present in spacecraft systems such as fuel systems, heat pipes, or environments with human occupants. Convection can happen naturally or be forced by a device like a fan. It behaves differently in space compared to environments with gravity. On Earth, for example, warmer fluids rise because they are less dense than their surroundings, with gravity helping to drive the motion.  

*Radiation* is the transfer of heat through electromagnetic waves and does not require a medium. Heat moves directly from one surface to another. This is the primary mechanism of heat transfer in space and is also how energy from the sun and planets is transmitted.  

 
In the next sections, all three mechanisms will be explained in more detail. 
### Conduction
Conduction is the heat transfer by molecular interaction. This is heat transfer through parts and contact points. Locally this is important and essential within your system. Conduction through a part is driven by the dimensions and material of the part. 
For a part made of a material with temperature independent properties, the heat flow can be described by a conductive coupling and a temperature difference. 

In this equation Q_ij is the heat flow between node i and j, and C_ij is the conductive coupling between node i and j. Note that the equation scales linearly with the temperature difference. 

The conductive coupling is a function of the material conductivity and a shape factor. In the equation below k is the conductivity in W/mK and S is the Langmuir conductive shape factor with units meter. 

For a “simple” part like a rectangle, a cylinder or a plate the shape factor can be described as the division of cross-section (A in m2), divided by the length of the thermal path (L in m). 


In practice in a thermal model or analysis, a structure will often be simplified into bars, plates and cylinders. For more complex shapes like discs, equations can be found in literature, e.g. in ECSS-E-HB-31-01. Whenever that is not possible a FEM or CAD tool can be used to analyse the thermal conduction between two interface points of a structure. 

Material conductivity is not a constant with temperature. When analysing the properties in a certain temperature band, a constant can be assumed. When this is not possible, a conductivity integral needs to be used.

The conductivity of some materials is also not homogenous in all directions. Examples of these are glass or carbon reinforced materials. In these materials the conductivity along the fibre is driven by the fibre material, while in the direction perpendicular to the fibre the conductivity is driven by the conductivity of the resin. An example of this is a CFRP M40 material, which has a conductivity of 55 W/mK along the fibre, while perpendicular to the fibre this is only 1.3 W/mK. 

A special case of conduction is conduction between two adjacent surfaces. This contact is not perfect due to the roughness of the surfaces. This forces the heat flow through a smaller area. 

The conduction between these two surfaces can be described with a contact conductance coefficient and the area of contact in m2:


The contact conductance coefficient is measured in watts per square meter per kelvin (W/m²K) and depends on several factors. These include the thermal conductivity of both surfaces, the roughness and machining method, the type of surface finish such as anodizing, the hardness and stiffness of the parts in contact, the distribution of contact pressure, and the contribution of radiation between parts when temperatures exceed 900 K. Because many of these parameters are not known in advance, the contact conductance coefficient is typically determined through testing. Before testing, estimates can be made using empirical correlations, such as those provided in ECSS-E-HB-31-01 part 4A.

To enhance heat transfer and reduce uncertainty associated with contact conductance, the coefficient can be increased. This can be done by using interface fillers, increasing the contact pressure, or improving the surface condition through cleaning and polishing. Thermal grease may also be considered, although it is generally avoided in space applications because of its potential to outgas.

### Convection
Convection is the transfer of heat through the movement of a gas or fluid. It consists of two mechanisms: diffusion, which is the random molecular motion similar to conduction, and advection, which is heat transfer through the bulk motion of the fluid.
Convection can be classified into two types:
*Free (or natural) convection*, driven by buoyancy forces caused by density differences that result from temperature variations. In a gravity environment, warmer fluid, being lighter, rises, while cooler, denser fluid sinks. Gravity is essential for this process to occur.
*Forced convection*, where fluid movement is caused by external drivers such as fans or pumps.

In the space environment, convection is generally absent due to the lack of a medium. However, it remains relevant for several spacecraft systems and mission phases. It must be considered in thermal control subsystems like fuel systems, pumped-loop cooling, heat pipes, and especially in human spaceflight.  
Convection is also important during certain ground-based phases such as transport or launch.  In correlation tests conducted in non-vacuum environments, convection introduces additional cooling or heating that must be accounted for.
To include convection in a thermal model the newton rate equation can be used. Note that this equation scales linear with the temperature difference like the conduction equation.  

q/A=h⋅ΔT

Where
q    : Rate of convective heat transfer in W
A    : Area normal to heat flow in m^2
ΔT : Temperature difference in K between the fluid and solid node
h    : Convective heat transfer coefficient in W/m^2 K:

However, the convective heat transfer coefficient h is a highly uncertain parameter. While this approach is suitable for early-stage analysis, more detailed models or aerodynamic simulations may be developed for greater accuracy when required. Typical values of h for air are: 5 -50 W/m²·K for free convection and 25 - 250 W/m²·K for forced convection. 

### Radiation
All objects with a temperature above 0 K emit thermal radiation due to microscopic energy transitions and electron oscillations. Temperature reflects the intensity of this microscopic activity. Radiation heat transfer does not require a material medium and spans the electromagnetic spectrum from 0.1 μm to 100 μm. Emitted radiation varies with wavelength and direction, and its intensity depends on the object's material, surface condition, and temperature.

#### Black Body Radiation
The concept of black body radiation serves as a useful standard for comparing the radiative properties of real materials. A black body is an idealized object that absorbs all incident radiation, regardless of wavelength or direction, without any reflection. It also emits the maximum possible radiation at a given temperature and wavelength, uniformly in all directions. The closest physical approximation to a black body is a cavity with a small aperture.
 
The spectral of a black body at a given wavelength and temperature can be described by Planck’s law:

Φ_b (λ,T)=(2πhc^2)/λ^5   1/(e^(hc/kTλ)-1)[W/m^3]

Where:
 = wavelength [m],   T = absolute temperature  
k = Boltzmann’s constant = 1.4E-23 kg m2/s2/K  
h = Planck’s constant = 6.6E-34 J s  
c = velocity of light in vacuum = 3E8 m/s  

Integrating over the wavelength spectrums, results in Stephan Boltzmann’s law, the total flux emitted per unit area as a function of only temperature:

Where
Stephan Boltzmann’s constant = 5.67E-8 W/m2/K4  

Note in that Planck’s law uses the Boltzmann’s constant k, and Stephan Boltzmann’s law uses the Stephan Boltzmann’s constant . While named after the same person, these are not the same constants and have vastly different values and units. During this course you will make a lot of use of the Stephan Boltzmann’s constant , the other we won’t encounter again. 
The black body radiation as function of the wavelength for several temperatures is shown in Figure 3. Note that both the magnitude and location of the peak changes with the temperature. Higher temperatures will emit more radiation overall, and the peak of the graph is located at lower wavelengths. Compare for example the sun with a glowing ember; the sun is hot white, while the relatively cooler ember glows in a deep red. 

The wavelength at which the peak of the radiation occurs is inversely proportional to the temperature of the black body. This effect is described by Wien’s displacement law:
λ_max T≈2898 [μmK]

Using Wien’s displacement law, it is possible to determine the peak radiation point of any black body. Figure 4 compares the black body radiation of the Sun, boiling water and earth. The top two graphs show the absolute values with at different scales for the Y-axis, the bottom graph shows the data normalized to the maximum value of each dataset. The grey vertical bar shows the wavelengths of visible light. 

From Figure 4 and Table 1, several interesting observations can be made. First, it can be seen that the wavelength of maximum radiation of the sun is at a much lower wavelength than those of boiling water and Earth. 
```{list-table} Black Body temperature
:header-rows: 1
:name: BlackBody

* - 
  - Black Body temperature [K]
  - λ-max []
* - Sun
  - 5772 
  - 0.5
* - Boiling water
  - 372
  - 7.8
* - Earth
  - 252
  - 11.5  
```

#### Optical properties
However, in reality, black bodies emit and absorb less radiation than a black body. Atoms have different energy state, a single atom can be in a finite number of energy bands. Absorption and emission of atoms changes these energy states. The frequency of the radiation that causes these changes depend on the atomic and molecular structure of the surface and the interactions between neighbouring molecules. This creates per surface a continuous absorption and emission spectrum. 
The total emission of a non-black body at a certain temperature can be described by the following equation, assuming the emissivity is independent of temperature:

An effective material emissivity can be determined for a material:

Where:

The emissivity, a material properties, is thus defined as the fraction of energy a grey body absorbs with respects to the same black body at a given temperature. 
Similarly as emissivity, the non-black body absorptivity can be described. 

In this equation Φ(λ) is the flux emitted by another body at a given temperature, impinging on the body that is absorbing the radiation. It is after all external radiation, dependent on another body and it’s temperature, that is absorbed. 
Kirchhoff’s law states that a good emitter is a good absorber at a particular wavelength (or for a specific range of wavelengths). It is out of the scope of this reader and course to discuss the proof, it is based on the conservation of energy. In certain conditions it can be shown that a body needs to absorb the same ratio of radiation as it emits at a certain wavelength to maintain energy conservation laws. 
In short this results in the simple statement:

Be very careful, this only holds if the wavelength or wavelength band is the same for the two values. Moreover, this law is valid under the condition that the surface temperature is equal to the temperature of the source of irradiation, which is not always accurate. 

As a grey body does not fully absorb all incoming radiation, part of the radiation is reflected or transmitted. As shown below, the sum of absorptivity, transmissivity and reflectivity must be 1. Note that emissivity is not part of this relation, as it is not part of the incoming radiation, but rather different radiation produced by the body. 

1=α+ρ+τ
 

Most bodies are not transmissive. Just as absorptivity, reflectivity and transmissivity are wavelength dependent properties. Take for example glass, in the visual spectrum it is very transmissive, but in infrared wavebands glass is opaque. This difference in optical properties at different wavelengths is the working principal of green houses. 

The optical properties can be expressed in the absorptivity, reflectivity or emissivity of the material as function of the wavelength. Due to Kirchoff’s law, and the relation between absorptivity and reflectivity, the properties can be described in a single graph. This graph shows either the reflectivity or absorptivity/emissivity as function of the wavelength of the radiation. Figure 6 shows one of these graphs for a white paint. 
 

The radiation absorbed from another heat source, or emitted by a body, can be determined by integrating the relevant radiation spectrum with the corresponding graph. In practice, this spectrum is typically either the solar spectrum or an infrared (IR) spectrum. To simplify calculations, this integration over the wavelength-dependent reflectance and radiation spectrum is not performed for every case. Instead, the space industry commonly uses two coefficients: the solar absorption coefficient (α) and the infrared emission coefficient (ε).

Confusingly, these coefficients resemble the previously discussed wavelength-dependent absorptivity and emissivity in name and symbols, but they refer to different applications.

The solar absorption coefficient (α) is used to describe the absorption and reflection of solar radiation and albedo. Since objects in typical thermal engineering applications are not at the same temperature as the Sun, this coefficient is not used when calculating emitted radiation.
	
The infrared emission coefficient (ε) is equal to the IR absorption coefficient due to Kirchhoff’s Law. Because of this equivalence, ε is used for both emission and absorption of IR radiation—whether it’s radiation exchanged between parts of a satellite, emitted to space, or absorbed from planetary IR sources.

Importantly, α and ε are not equal, as they refer to different parts of the radiation spectrum.

As discussed before, the major part of the energy of solar radiation is between 0.2 and 3.0 μm and the major part of the IR radiation occurs between 1 and 35 μm. This difference can be used to create desired effects for an optical property. A theoretical example is shown in Figure 7. It can be seen that the different response of this theoretical material create an effect that relatively less solar radiation is absorbed, while IR is emitted (and absorbed) reasonably well. 

 
In general, optical properties can be divided into 4 categories:

	Solar absorbers: high α, low ε. For example polished aluminium. These surfaces heat up more under sunlight. A use for such a coating could be a solar stove for direct solar energy based propulsion. 
	Solar reflector: low α, high ε. For example white paint or Optical Solar Reflectors (OSR). These surfaces remain relatively cool, even under sunlight.  This is used for applications that need to stay cool, for example sun shields and sun facing radiators.
	Flat absorber: high α, high ε. For example black paint. These materials reduce heat exchange due to reflections, and can have better emission properties overall. These are often used inside spacecraft and inside test chambers. 
	Flat reflector: low α, low ε. For example aluminium paint. These surfaces reflect all types of radiation and reduce the effect of radiative heat exchange. 
 
Some example values for the (solar) absorptivity coefficient and the IR emissivity coefficient are shown. 
Table 2  Optical properties.
Material	Solar absorptance	Hemispherical emissivity	α/ϵ
Black paint	0.96	0.88	1.09
Aluminized Teflon foil	0.15	0.75	0.20
Silvered Teflon foil	0.11	0.80	0.14
Aluminized Kapton foil	0.42	0.72	0.58
Aluminized Kapton foil (metal side)	0.12	0.05	2.4
White Paint	0.17	0.82	0.21
Solar cell Si	0.75	0.82	0.91
Solar GaAs	0.91	0.81	1.12
CRFP	0.92	0.82	1.12

To get a sense of the temperature response of a material, you can setup a simple heat balance for a one sided panel:

From this equation it is immediately clear that the temperature of a surface under sunlight is dependent on the ratio between the absorption and emissivity coefficient. As an example, for a similar configuration, the Aluminized Kapton foil (metal side) will result in the warmest temperatures, despite the low α. Due to the very low ε of this surface, the ratio is still the largest of the materials listed. 
In general, emissivity is reported either as normal emittance or hemispherical emittance. The normal emittance is the emission coefficient normal to the surface. This value is easy to determine with measurements. The hemispherical emittance is the average emittance over all solid angles in a hemisphere on top of a flat surface. 
The emissivity is not the same for all angles with respect of the surface. For dielectric materials there is a drop under large angles, while for conductive coatings the emissivity might be increased under certain angles.  

Surfaces can also respond differently to incoming radiation. A specular reflector is like a mirror, all radiation is reflected at the incoming angle. A diffuse reflector is the opposite and reflects an equal amount of radiation irrespective of the incoming angle. For much of the surfaces in this reader diffuse reflectivity is assumed, unless otherwise specified. 
The total reflected heat flux leaving a surface in all directions (complete hemisphere) due to spectral directional irradiation is referred to as the spectral directional-hemispherical reflectance. 

#### View and Gebhart factors
Radiative heat transfer between surfaces depends on several factors, including the orientation of the surfaces relative to each other, their radiation properties, and their temperatures. To account for the effect of orientation, view factors are used. These are purely geometrical and describe the fraction of radiation leaving one surface that directly reaches another.
The view factor from surface i to surface j, denoted F_(i,j) , is defined as the fraction of the radiation leaving surface i that directly strikes surface j.
 

Considering the surfaces in Figure 10, to calculate the view factor between them, first we assess the total rate of radiation leaving dA_1  in all directions is which is: 
Q ̇_dA1=I_1 πdA_1
where  I_1is the radiation intensity.  
The portion of radiation from dA_1  striking dA_2 can be expressed as:
Q ̇_(dA1→2)=I_1  cos⁡〖(θ_1 )dA_1 dω_21=〖I_1 cos〗⁡〖(θ_1 )dA_1  (〖dA〗_2  cos⁡(θ_2 ))/r^2 〗 〗  
where dω_21 is the solid angle,  θ_1, θ_2 are the angles relatives to the normal and r is the distance between two surfaces. 
Putting together both equations, the differential view factor (fraction of radiation leaving dA_1   that strikes dA_2 directly is: 
dF_(dA1→dA2)=Q ̇_(dA1→2)/Q ̇_dA1 =(cos⁡〖(θ_1 )  cos⁡(θ_2 ) 〗 dA_2)/(πr^2 )
The view factor by dA1 is then obtained by integrating over A_2  :
F_(dA1→dA2)=∫_(A_2)▒cos⁡〖(θ_1 )  cos⁡(θ_2 ) 〗/(πr^2 ) dA_2
A special case occurs when a surface "sees" itself. In general, the view factor is zero, except in the case of concave surfaces, as illustrated in Figure 11.
 
When analysing an enclosure, where all surfaces are visible to one another, several general relationships can be defined among the N2 possible view factors. These are known as view factor algebra:

Bounding: View factors are fractions and are therefore bounded between 0 and 1. 

Conservation: The sum of all view factors from a surface, including any self-view factor (for concave surfaces), must equal 1. This reflects energy conservation, radiation emitted from a surface must be fully accounted for within the enclosure.

Reciprocity: Based on the geometry of radiative exchange, the following relation holds:

Distribution: When a surface radiates to two or more targets, the view factor to the combined area equals the sum of the individual view factors:
F_(i,j+k)=F_ij+F_ik  

Composition: Using reciprocity and distribution, the total radiation from two source areas to a third can be written as:
A_i F_ik+A_j F_jk=(A_i+A_j ) F_(i+j,k)

In a system with N surfaces, there are N2 total view factors. However, only N(N−1)/2 are independent, since another N(N−1)/2 can be derived from reciprocity, and N more from the conservation condition. For example, in a 3-surface enclosure, there are 9 possible view factors. Of these, 3 must be independently determined, 3 can be derived using reciprocity, and the remaining 3 from the conservation condition.
To calculate the view factors that must be independently determined, several approaches are available. One option is to perform the surface-to-surface integration directly, although this is generally not recommended due to its complexity. A more practical method is to use analytical expressions available in established references, such as the European standard ECSS-E-HB-31-01 Part 1A. Alternatively, Monte Carlo raytracing software can be employed to numerically estimate view factors, especially for complex geometries.

In thermal radiation analysis, **Gebhart factors** are used to describe how much of the radiation leaving one surface is ultimately absorbed by another, accounting for all possible reflections within an enclosure. This approach is used when working with diffuse grey surfaces, where surface properties such as emissivity do not vary with wavelength, and radiation is emitted uniformly in all directions.

The Gebhart factor *Bij* represents the fraction of radiation leaving surface i that is eventually absorbed by surface j. Unlike view factors, Gebhart factors include the effects of multiple reflections between surfaces.
For an enclosure of N surfaces, the Gebhart factor can be calculated as:
```{math}
:label: Gebhart1
\( B_{ij} = F_{ij}\,\varepsilon_{j} + \sum_{k=1}^{N} (1-\varepsilon_{k})\,F_{ik}\,B_{kj} \)
```
where *Fij* is the view factor from surface *i* to *j*, and *εj* is the emissivity of surface *j*. 

When analysing an enclosure, several general relationships among the possible Gebhart factors can be defined. These follow rules similar to view factor algebra:
- Bounding: Gebhart factors are fractions by definition and are bounded between 0 and 1:

- Conservation: The total of all Gebhart factors from a given surface must equal 1, including the portion it reabsorbs itself:

- Reciprocity: There is a symmetry in energy exchange between surfaces.   The factor Rij is the radiative coupling factor between surfaces i and j (in m²). 

In practical thermal analysis, Gebhart factors allow for more accurate calculation of radiative heat exchange in enclosures, particularly when multiple reflections are significant. These values can be obtained from known view factors and surface emissivities or by using specialized radiation analysis software with Monte Carlo raytracing.
