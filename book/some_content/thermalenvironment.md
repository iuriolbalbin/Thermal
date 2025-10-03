## Thermal Environment
In spacecraft thermal control, several distinct regions are of interest, beginning with Earth’s atmosphere, passing through outer space (the void between celestial bodies), and extending to the atmospheres and surfaces of other planets.  

The gases surrounding planets, moons, and stars are retained by gravity but do not have a clearly defined boundary. Gas density decreases exponentially with distance from the body until it blends into the surrounding environment. As such, the boundary of “space” is defined by convention rather than a precise physical marker.  

For spacecraft flight purposes, the boundary of space is generally accepted as 100 km altitude, known as the Kármán line, a definition adopted by the International Astronautical Federation (IAF). This height marks the transition from aeronautics (aerodynamic flight) to astronautics (non-powered orbital flight). Theodore von Kármán concluded in the 1950s that above this altitude, a vehicle would need to travel faster than orbital velocity to generate enough lift from the atmosphere to stay aloft. Following this definition: on Venus, the Kármán line is around 250 km, and on Mars, it's approximately 80 km.  

The two bodies controlling the space environment for most aircraft are the Earth and the Sun, with other celestial bodies being only important to specific spacecraft missions.   

#### Deep Space
Deep space is the cold darkness that surrounds the spacecraft. Cosmic background radiation s electromagnetic radiation in the microwave band filling the observable universe almost uniformly. This deep-space nearly-isotropic radiation (also known as cosmic microwave background, CMB) is a relic from the Big Bang, predicted by Gamov in 1948 and discovered in 1964 by A. Penzias and R. Wilson. The CMB behaves like a nearly perfect black-body radiator with a temperature of 2.73±0.05 K. For most engineering purposes this is set at 3K.   
Taking into account the background radiation is significant for certain applications, such as cryogenic radiators and sensors. However for other application, it can also be neglected, e.g. the thermal balance of a rocket nozzle.   
#### Solar Radiation

Solar radiation refers to the thermal energy emitted by the Sun and received by spacecraft and planetary bodies. The two main aspects of solar radiation that are critical for spacecraft thermal analysis are its power (irradiance) and spectral distribution.  

The solar spectrum closely resembles that of a black body at a temperature of approximately 5778 K (according to ECSS-E-ST-10-04C Rev.1).  The spectrum peaks at a wavelength of around 0.50 μm (500 nm), which lies in the visible range of the electromagnetic spectrum. Most of the solar radiation falls within the 0.3 to 3 μm range: with 10% in the ultraviolet (UV), 40% in the visible and 50% in the infrared (IR). This makes the Sun’s radiation particularly efficient at heating surfaces and generating electricity via photovoltaic cells.  
 
The Solar Constant, denoted S_⊙^N, represents the total solar irradiance (TSI) at a distance of 1 astronomical unit (1 au = 149,597,870,700 m). Despite the name, the solar constant is not truly constant, it is a time-averaged value that varies with solar activity and Earth’s distance from the Sun. Specifically, it is the mean total electromagnetic energy from the Sun, integrated over all wavelengths, incident per unit area, and per unit time at a distance of 1 AU. As such, it is usually expressed in W/m2. Our current best estimate is 1360.8±0.5 W/m2, updated in 2011 when the previous value was 1365.4±1.3 W/m2.  
This values also fluctuates slightly over the 11-year solar cycle (~±1.3 W/m²), ranging from 1360.8 W/m² (minimum) to ~1363 W/m² (maximum), primarily due to sunspot activity. There can be even larger changes in short periods over those monthly-averaged values, it is not uncommon to have variations of up to 5 W/m2 on time scales of days to weeks. 

Due to Earth's elliptical orbit, the Earth-Sun distance varies by ±1.7%, leading to a corresponding ±3.4% variation in solar irradiance. This means that in the Perihelion (early January) it will be ~1410 W/m² and in the Aphelion (early July): it will be ~1315 W/m². 

Solar irradiance decreases with the square of the distance from the Sun. The following table shows relative solar heating at various planets (compared to Earth = 1.00):

PlanetHeat Relative to Earth
|Mercury   | 6.67                   |
| Venus    | 1.91                   |
| Earth    | 1.00                   |
| Mars     | 0.431                  |
| Jupiter  | 0.0369                 |
| Saturn   | 0.0110                 |
| Uranus   | 0.0027                 |
| Neptune  | 0.0011                 |
| Pluto    | 0.00064                |

This steep drop makes solar panels rare beyond Mars' orbit. Deep-space missions (e.g., to Jupiter or beyond) often rely on nuclear power sources instead.

At a distance of 1 au, the Sun subtends an angle of 0.53° (or 0.0093 rad), corresponding to a solid angle of ~68 × 10⁻⁶ sr. This makes solar radiation effectively collimated, that is: parallel rays, for most engineering applications.

However, for spacecraft operating very close to the Sun (e.g., BepiColombo), the angular divergence of solar rays becomes significant and must be accounted for in detailed thermal reflection and shadowing models.
