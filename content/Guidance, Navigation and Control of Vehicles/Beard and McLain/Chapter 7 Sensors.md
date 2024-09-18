
### MEMS

MEMS is the technology of microscopic devices, particularly those with moving parts. They usually consist of a central unit that processes data and several components that interact with the surroundings.

#### MEMS accelerometer
![[Skjermbilde 2024-09-16 140600.png]]

##### Acceleration measurement![[Skjermbilde 2024-09-16 142635.png]]![[Skjermbilde 2024-09-16 142653.png]]![[Skjermbilde 2024-09-16 142714.png]]![[Skjermbilde 2024-09-16 142750.png]]
##### Accelerometer models
![[Skjermbilde 2024-09-16 143020.png]]
![[Skjermbilde 2024-09-16 142942 1.png]]

#### MEMS rate gyro
It is more correct to use attitude rate sensor (ARS) for MEMS. It it not a gyro.
![[Skjermbilde 2024-09-16 143731.png]]

##### ARS figure
![[Skjermbilde 2024-09-16 143848.png]]

##### ARS model

The manufacturing process implies that rate gyros will have a drift term, as well as zero mean Gaussian noise:
$$
\Upsilon_{gyro}= k_{gyro}\Omega + \beta_{gyro}+\eta^{'}_{gyro} 
$$
where $\beta$ is bias and $\eta$ is white measurement noise. 
$\Upsilon$ is in units of voltage. Calibrating to units of rad/s gives:
![[Skjermbilde 2024-09-16 144456.png]]

ARS will drift over time. We model the bias as random walk:
$$
\frac{d}{dt}\beta_{gyro}=\text{white noise}
$$
#### Pressure measurement
![[Skjermbilde 2024-09-16 145508.png]]

##### Altitude measurement

The basic equation of hydrostatics is:
$$
P_{2}-P_{1}=\rho g(z_{2}-z_{1})
$$
$\rho$ is constant. 

Using the ground as reference, and assuming constant air density gives us:
$$
P-P_{ground} = -\rho g(h-h_{ground}) = -\rho gh_{AGL}
$$
AGL = above ground level.

Below 11.000 m we can use the barometric formula:
$$
P=P_{0}\begin{bmatrix}
\frac{T_{0}}{T_{0}+L_{o}h_{ASL}}
\end{bmatrix}^{gM/RL_{0}}
$$
where 
$P_{0}$ = standard pressure at sea level
$T_{0}$= standard temperature at sea level
$L_{0}$= rate of temperature decrease
$g$ = gravitational constant
$R$ = universal gas constant for air
$M$= standard molar mass of atmospheric air

##### Airspeed measurement

From Bernoullis equation:
$$
P_{t}=P_{s}+\frac{\rho V^2_{a}}{2}
$$
or
$$
\frac{\rho V^2_{a}}{2}=P_{t}-P_{s}
$$
Pitot-static pressure sensor measures dynamic pressure:
$$
y_{diff(pres)} = \frac{\rho V^2_{a}}{2}+\beta_{diff(pres)} + \eta_{diff(press)}
$$
![[Skjermbilde 2024-09-16 150310.png]]

#### Magnetometers and digital compasses

Heading is the sum of declination angle and magnetic heading
$$
\psi=\delta+\psi_{m}
$$
Magnetic heading determined from  measurement of body-frame components of magnetic field projected onto horizontal plane
![[Skjermbilde 2024-09-16 150717.png]]
![[Skjermbilde 2024-09-16 150705.png]]

##### Magnetic declination

Magnetic declination or variation is the angle on the horizontal plane between magnetic North (the direction the North end of a compass needle points, corresponding to the direction of the Earth's magnetic field lines) and true North (the direction along a meridian towards the geographic North Pole).

Magnetic North is moving!
![[Skjermbilde 2024-09-16 151256 1.png]]

##### Magnetic declination variation
![[Skjermbilde 2024-09-16 151349.png]]

##### Magnetic inclination

Magnetic dip, dip angle, or magnetic inclination is the angle made with the horizontal by the Earth's magnetic field lines. This angle varies at different points on the Earth's surface.
![[Skjermbilde 2024-09-16 151750.png]]
![[Skjermbilde 2024-09-16 151843.png]]

#### Global positioning system



##### GPS error sources

 - Time of flight of radio signal from satellite to receiver used to calculate pseudorange 
	- Called pseudorange to distinguish it from true range 
- Numerous sources of error in time of flight measurement: 
	-  Ephemeris Data 
	-  errors in satellite location 
	-  Satellite Clock 
	-  due to clock drift 
	-  Ionosphere 
	-  upper atmosphere, free electrons slow transmission of GPS signal 
	-  Troposphere 
	-  lower atmosphere, weather (temperature and density) affect speed of light, GPS signal transmission 
	-  Multipath Reception 
	-  signals not following direct path 
	-  Receiver Measurement 
	-  limitations in accuracy of receiver timing 
- Small timing errors can result in large position errors 
	-  10 ns timing error à 3 m pseudorange error

##### GPS error characterization
Cumulative effect  of GPS pseudorange errors is described by user equivaltent range error (UERE).
UERE has two components:
- Bias
- Random
![[Skjermbilde 2024-09-16 152723.png]]

Effect of satellite geometry on position calculation is expressed by dilution of precision (DOP).
Satellites close together -> high DOP
DOP varies with time
Horizontal DOP is smaller than vertical DOP
**Nominal HDOP = 1.3**
**Nominal VDOP = 1.8**

##### Total GPS error (RMS)

Standard deviation of RMS error in the north-east plane:
![[Skjermbilde 2024-09-16 154731.png]]

Standard deviation of RMS altitude error:
![[Skjermbilde 2024-09-16 154750.png]]

![[Skjermbilde 2024-09-16 155109.png]]

##### GPS error model

Interested in transient behavior of errors - how does GPS error change with time

We use Gauss-Markov error model proposed by Rankin
$$
\nu \begin{bmatrix}
n+1
\end{bmatrix}=e^{-k_{GPS}T_{s}}\nu \begin{bmatrix}
n
\end{bmatrix}+\eta_{GPS}\begin{bmatrix}
n
\end{bmatrix}
$$
![[Skjermbilde 2024-09-16 155420.png]]
![[Skjermbilde 2024-09-16 155447.png]]
