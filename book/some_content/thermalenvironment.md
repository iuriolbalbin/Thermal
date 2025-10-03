## Thermal Environment
In spacecraft thermal control, several distinct regions are of interest, beginning with Earth’s atmosphere, passing through outer space (the void between celestial bodies), and extending to the atmospheres and surfaces of other planets.  

The gases surrounding planets, moons, and stars are retained by gravity but do not have a clearly defined boundary. Gas density decreases exponentially with distance from the body until it blends into the surrounding environment. As such, the boundary of “space” is defined by convention rather than a precise physical marker.  

For spacecraft flight purposes, the boundary of space is generally accepted as 100 km altitude, known as the Kármán line, a definition adopted by the International Astronautical Federation (IAF). This height marks the transition from aeronautics (aerodynamic flight) to astronautics (non-powered orbital flight). Theodore von Kármán concluded in the 1950s that above this altitude, a vehicle would need to travel faster than orbital velocity to generate enough lift from the atmosphere to stay aloft. Following this definition: on Venus, the Kármán line is around 250 km, and on Mars, it's approximately 80 km.  

The two bodies controlling the space environment for most aircraft are the Earth and the Sun, with other celestial bodies being only important to specific spacecraft missions.   

#### Deep Space
Deep space is the cold darkness that surrounds the spacecraft. Cosmic background radiation s electromagnetic radiation in the microwave band filling the observable universe almost uniformly. This deep-space nearly-isotropic radiation (also known as cosmic microwave background, CMB) is a relic from the Big Bang, predicted by Gamov in 1948 and discovered in 1964 by A. Penzias and R. Wilson.  
The CMB behaves like a nearly perfect black-body radiator with a temperature of 2.73±0.05 K. For most engineering purposes this is set at 3K.   

Taking into account the background radiation is significant for certain applications, such as cryogenic radiators and sensors. However for other application, it can also be neglected, e.g. the thermal balance of a rocket nozzle.   
#### Solar Radiation

Solar radiation refers to the thermal energy emitted by the Sun and received by spacecraft and planetary bodies. The two main aspects of solar radiation that are critical for spacecraft thermal analysis are its power (irradiance) and spectral distribution.  

The solar spectrum closely resembles that of a black body at a temperature of approximately 5778 K (according to ECSS-E-ST-10-04C Rev.1).  The spectrum peaks at a wavelength of around 0.50 μm (500 nm), which lies in the visible range of the electromagnetic spectrum. Most of the solar radiation falls within the 0.3 to 3 μm range: with 10% in the ultraviolet (UV), 40% in the visible and 50% in the infrared (IR). This makes the Sun’s radiation particularly efficient at heating surfaces and generating electricity via photovoltaic cells.  
 
The Solar Constant, denoted S_⊙^N, represents the total solar irradiance (TSI) at a distance of 1 astronomical unit (1 au = 149,597,870,700 m). Despite the name, the solar constant is not truly constant, it is a time-averaged value that varies with solar activity and Earth’s distance from the Sun. Specifically, it is the mean total electromagnetic energy from the Sun, integrated over all wavelengths, incident per unit area, and per unit time at a distance of 1 AU. As such, it is usually expressed in W/m2. Our current best estimate is 1360.8±0.5 W/m2, updated in 2011 when the previous value was 1365.4±1.3 W/m2.  
This values also fluctuates slightly over the 11-year solar cycle (~±1.3 W/m²), ranging from 1360.8 W/m² (minimum) to ~1363 W/m² (maximum), primarily due to sunspot activity. There can be even larger changes in short periods over those monthly-averaged values, it is not uncommon to have variations of up to 5 W/m2 on time scales of days to weeks. 

Due to Earth's elliptical orbit, the Earth-Sun distance varies by ±1.7%, leading to a corresponding ±3.4% variation in solar irradiance. This means that in the Perihelion (early January) it will be ~1410 W/m² and in the Aphelion (early July): it will be ~1315 W/m². 

Solar irradiance decreases with the square of the distance from the Sun. The following table shows relative solar heating at various planets (compared to Earth = 1.00):
```{list-table} Relative solar heating 
:header-rows: 1
:name: Solarheating

* - Planet
  - Heat Relative to Earth
* - Mercury
  - 6.67
* - Venus
  - 1.91
* - Earth
  - 1
* - Mars
  - 0.431
* - Jupiter
  - 0.0369
* - Saturn
  - 0.0110
* - Uranus
  - 0.0027
* - Neptune
  - 0.0011
* - Pluto
  - 0.00064
```


This steep drop makes solar panels rare beyond Mars' orbit. Deep-space missions (e.g., to Jupiter or beyond) often rely on nuclear power sources instead.

At a distance of 1 au, the Sun subtends an angle of 0.53° (or 0.0093 rad), corresponding to a solid angle of ~68 × 10⁻⁶ sr. This makes solar radiation effectively collimated, that is: parallel rays, for most engineering applications.

However, for spacecraft operating very close to the Sun (e.g., BepiColombo), the angular divergence of solar rays becomes significant and must be accounted for in detailed thermal reflection and shadowing models.


#### Albedo
Solar radiation is also reflected by planetary bodies. When it is reflected by earth this is called Albedo. When the light is reflected, the spectral properties are not changed, though the radiation is assumed to be diffuse after reflection. In other words, the albedo radiation does not travel in parallel rays. 

Typically albedo is expressed as a fraction of the solar constant. An average value is 0.3. this means 30% of the power of the solar radiation is reflected, thus the heating of the albedo power is 0.3⋅1361=408 W/m^2.
Albedo varies locally in an orbit, especially around earth. You can see this yourself, deep sea is almost black, while snow and white clouds are very reflective. An example of daily variation over the earth surface is shown in the figure. You can see in this figure that the snowy polar regions are much more reflective than the equatorial regions. Note also that albedo only occurs on the sunlit parts of the globe. This figure was taken in winter, thus there is no reflection on the north pole. 

In many cases earth is considered a diffuse reflector with constant reflectivity. This can also be used for early calculations. For polar orbits this might not be valid, as albedo might greatly change over the orbit. This might also not hold for other planets, the moon for example has a non-diffuse reflection. Always take care with (thermally) lightweight parts and spacecraft, these will be more sensitive to variations in albedo. 

#### Planetary radiation
Planets also emit their own radiation. This radiation is emitted in the infrared spectrum in a diffuse manner. The average infrared radiation for earth is 230 W/m2 (black body spectrum with a temperature of 254 K, this is a spectrum with the peak between 10 and 15 µm), but can vary from 150-350 W/m2. The amount of infrared radiation varies based on latitude, whether it is day or night and part of the earth. In general the infra-red radiation is higher around the equator.
 
 
#### Orbital effects
The effect of the environments described in the previous sections, is dependent on the orbit of your spacecraft. For a typical mission of a Spacecraft in orbit, the thermal engineer will need to consider the planetary albedo and infrared radiation of the body it orbits and the solar input. So for example for a regular satellite orbiting the earth, the influence of earth and sun needs to be considered, but the thermal effect of the moon can be ignored. For a satellite on an interplanetary trajectory or in a Lagrange point, or even a trajectory between the moon and earth, only the sun can be considered.  It is of course up to the thermal engineer to decide whether these influences are indeed negligible. The orbit of a spacecraft is chosen for mission specific reasons. In the following paragraphs, some characteristics will be described. 

Many satellites fly in a sun-synchronous dusk dawn orbit in LEO. This orbit is nearly circular and praised for its constant light conditions. The thermal environment of a satellite in this orbit is also very constant. There are mostly no eclipses and hardly any orbital variation in the thermal conditions. The albedo and planetary radiation will also be relatively constant, as the satellite has the same altitude throughout the orbit, and the satellite (if nadir pointing) will have the same orientation with respect to the sunlit part of the planet. 

Any orbit LEO circular orbits will encounter eclipses, which vary with the season due to the solar inclination. The eclipse can be up to 40 minutes long. Note that these satellite will experience a lot of eclipses, and thus thermal cycles, throughout their lifetime. The influence of albedo and earth radiation is significant. 

A elliptical orbit, for example a molniya orbit will see more variation throughout their orbit, as the satellite travels from a low altitude in perigee to a high altitude in apogee. As the satellite will spend a long time in apogee, the thermal engineer might want to check whether this can occur in eclipse in any season. With some elliptical orbits this eclipse time can reach hours, which will be a driving thermal case. 
A satellite in GEO will have significantly less influence from the planet onto its thermal environment, though it cannot entirely be ignored. It will also encounter some seasonal eclipses due to the solar inclination. The number of eclipses can be a lot less, compared to a LEO orbit, but the time can be up to 70 minutes. 

When considering orbits around other objects in our solar system, their specific constraints need to be considered. For example, a spacecraft in Mercury orbit needs to consider that Mercury has a very slow rotation, so the planetary radiation greatly varies between the sun facing side and the dark side. 

#### On-Ground environments
Before the satellite reaches orbit, it will spent a considerable amount of time on the ground. To keep the systems safe, often the environment is controlled. Integration facilities are typically controlled at room temperature, and transportation happens in specialized containers with temperature control. 

Note that even specialized containers left out in the sun might heat up to unacceptable levels. The integration and many test occur also under none-vacuum conditions. This means convection can cause unexpected effects. One example of this is that convection might cool electronics during regular testing, while in space these elements might overheat due to the lack of convection. 

Once the system is integrated on the launch vehicle, it will also mostly be in a temperature controlled environment. Launch providers provide the temperature environment they offer in the launch manual. Once encapsulated and on the pad, the environment might be less controlled. This can be seen in the outtakes of the manuals for Ariane 5 and Falcon 9. Ariane 5 only specifies the air temperature in the last phases, whereas the falcon 9 does not offer any temperature control for the rollout of the system. 
 

#### Ascent environment
During ascent into orbit, the spacecraft will encounter a number of thermal effects: Thermal environment under the rocket fairing, aerothermal heating after fairing jettison and heating due to the rocket plumes. 
For the first minutes of a rocket flight, the satellite is under a fairing. This fairing will heat up significantly due to the aerodynamic friction with the atmosphere. The satellite is under the fairing for only a short mount of time, as a whole the satellite is unlikely to be affected, but external components can be, such as the insulation, external paint, radiators or solar panels. 
The heating under a fairing can be expressed as a infra-red flux (as done for Vega-C and Ariane 5), or as a temperature (As done by e.g. Falcon 9 and Atlas.) Vega-C and Ariane 5 manual state that the radiation due to heating of the fairing is at maximum 1000W/m2. Below is the figure from the Atlas manual, showing a peak temperature of 200 deg. C for parts of the fairing. 
 
After fairing jettison, the satellite itself is exposed to this aerothermal heating due to the free molecular flow. Generally the fairing is deployed when this effect drops below 1135 W/m2. The exact heating profile depends on the mission profile of the launcher. The effect decrease rapidly after fairing jettison, but can rise and drop during the mission. Also This will mainly affect external systems with a low thermal mass. 
An example of the aerothermal fluxes during a rocket launch are shown for the Ariane 5 rocket. 
 
In general thermal flux coming from the 1st and 2nd stage can be ignored. It is possible that 3rd stage engine fluxes can impinge on the spacecraft, the engine is located closer to the spacecraft, and outside the atmosphere the plume will expand a lot more. The Vega launcher for example can hit the “bottom” of the satellite with 1500W/m2 for a maximum of 2 minutes. 

#### Internal heat sources
The satellite has  a lot of internal heat sources. All electronics will dissipate heat. Dedicated heaters can raise the temperature and propulsive modules heat up. 
The plume generated by propulsive modules can also heat up other parts of the spacecraft when pointed at them. This might be particularly relevant for antennas and solar arrays, as they often extend from the spacecraft body. 
