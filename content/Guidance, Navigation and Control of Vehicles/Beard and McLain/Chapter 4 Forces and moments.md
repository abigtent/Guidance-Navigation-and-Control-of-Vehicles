The external forces are a combination of gravitational, aerodynamic, and propulsion:
$$
f = f_{g}+f_{a}+f_{p}
$$
The external moments are a combination of aerodynamic, and propulsion:
$$
m = m_{a}+m_{p}
$$
### Gravity force

The gravity vector expressed in the vehicle is:
$$
f^v_{g}=\begin{bmatrix}
0 \\
0 \\
mg 
\end{bmatrix}
$$
Expressed in the body frame we have:
$$
f^b_{g}=R^b_{v}\begin{bmatrix}
0 \\
0 \\
mg
\end{bmatrix}=\begin{bmatrix}
-mg\sin \theta \\
mg\cos \theta \sin \phi \\
mg\cos \theta \cos \phi 
\end{bmatrix}
$$
### Airfoil pressure distrubution
![[airfoil.png]]

Aerodynamic forces act in **CP** (center of pressure).

### Aerodynamic approximation 1
![[aerodynamic approx.png]]

$$
F_{lift}=\frac{1}{2}\rho V^2_{a}SC_{L}
$$
$$
F_{drag}=\frac{1}{2}\rho V^2_{a}SC_{D}
$$
$$
m = \frac{1}{2}\rho V^2_{a}ScC_{m}
$$
$$
\begin{bmatrix}
f_{x} \\
f_{z}
\end{bmatrix}=\begin{bmatrix}
\cos \alpha &-\sin \alpha \\
\sin \alpha  & \cos \alpha
\end{bmatrix}\begin{bmatrix}
-F_{drag} \\
-F_{lift}
\end{bmatrix}
$$
$C_{L}$ is lift coefficient.
$C_{D}$ is drag coefficient.
$C_{M}$ is pitch moment coefficient.

**Drag force** work against the velocity of the plane.
**Lift force** works against the gravity of the plane.
These forces are defined in the [[Chapter 2 Coordinate frames#Stability frame|stability frame]].

### Control surfaces
![[control surfaces.png]]

$$
\delta_{a} \to \text{Aileron} \to \text{controls roll rate of the plane.}
$$
$$
\delta_{e} \to \text{Elevator}\to \text{controls pitch rate of the plane}
$$
$$
\delta_{r}\to \text{Rudder}\to \text{control yaw rate of the plane}
$$
### Aircraft dynamics

Aircraft dynamics and aerodynamics are commonly separated into two groups:

-  Longitudinal 
	-  Up-down, pitch plane, pitching motions 

-  Lateral-directional 
	-  Side-to-side, turning motions (roll and yaw)

#### Longitudinal aerodynamics

- Act in the $i^b-k^b$ plane, also called the pitch plane
- Heavily influenced by angle of attack
- Also influenced by pitch rate and elevation deflection
$$
F_{lift}\approx\frac{1}{2}\rho V^2_{a}SC_{L}(\alpha,q,\delta_{e})
$$
$$
F_{lift}\approx\frac{1}{2}\rho V^2_{a}SC_{D}(\alpha,q,\delta_{e})
$$
$$
m\approx\frac{1}{2}\rho V^2_{a}ScC_{m}(\alpha,q,\delta_{e})
$$
**S** = top-down view of wing, area of wing seen from above.
**c** = mean chord = mean width of wing.


### Aerodynamic approximation 2
![[aero_2.png]]

#### Linear aerodynamic model
![[linear_aero.png]]

This linear model is valid for small **angles of attack**.
Flow remains attached over wing (laminar flow).

#### Nonlinear aerodynamics
![[nonlinear_aero.png]]

#### Nonlinear lift model
![[nonlinear_lift.png]]

#### Nonlinear aerodynamic model
![[nonlinear_model.png]]

The stability derivative: 
$$
CL_{\alpha}=\frac{\pi AR}{1+\sqrt{ 1+\left( \frac{AR}{2} \right)^2 }}
$$
represents the sensitivity of lift to the angle of attack, and can be approximated by physical dimensions of the airfoil, where

$$
AR =\frac{b^2}{S}
$$
b is the wingspan
S is the wing area

#### Drag vs. angle of attack
![[drag.png]]

#### Longitudinal forces/moments - body frame
![[Skjermbilde 2024-09-05 132538.png]]

### Lateral aerodynamics
$$
f_{y}=\frac{1}{2}\rho V^2_{a}SC_{Y}(\beta,p,r\delta_{a},\delta_{r})
$$
$$
l=\frac{1}{2}\rho V^2_{a}SbC_{l}(\beta,p,r\delta_{a},\delta_{r})
$$
$$
n=\frac{1}{2}\rho V^2_{a}SbC_{n}(\beta,p,r\delta_{a},\delta_{r})
$$
$f_{y}$ = force along y-axis
l = roll moment
n = yaw moment
b = wing span

$C_{Y}=$ coefficient for force in y-axis
$C_{l}=$ roll coefficient
$C_{n}=$ yaw coefficient 

#### Linearizing the coefficients
![[lateral_lin.png]]

### Aerodynamic coefficients
$C_{m_{\alpha}},C_{l_{\beta}},C_{m_{q}},C_{l_{p}},C_{n_{r}}$ are called stability derivatives because their value determine the stability of the aircraft.

- We distinguish between static and dynamic stability derivatives 
- Static stability determines moments that arise when the UAV is perturbed from a nominal condition. 
- Dynamic stability determines how the aircraft acts under the influence of disturbances

#### Longitudinal static stability derivative
![[Skjermbilde 2024-09-05 134348.png]]
**Center of Pressure** is the point where there is no moment due to aerodynamic forces. The lift and drag forces act at this point.

If the center of pressure is behind the center of gravity, then when $\alpha \neq 0$, the lift force will tend to push $\alpha$ back to zero. Otherwise, the lift force will tend to increase |$\alpha$|. Therefore $C_{m_{\alpha}}<0$.

#### Roll static stability derivative
![[Skjermbilde 2024-09-05 134401.png]]
Given the wind dihedral, a roll angle of $\phi$ will cause a side slip angle $\beta$ , which induces a side velocity $v$, which increases the lift on the leading wing, and decreases the lift on the trailing wing, causing a negative rolling moment. Hence the dihedral angle causes $C_{l_{\beta}}<0$

#### Yaw static stability derivative
![[Skjermbilde 2024-09-05 134414 1.png]]
For a positive side slip angle $\beta$ , the change in lift on the tail creates a moment arm about the center of gravity, that pushes the nose toward the direction of the wind, or in other words, creates a positive yawing moment $n$. Hence $C_{n_{\beta}}>0$.
$$
\dot{V}=\begin{bmatrix}
asas & 4545 & 4545 \\
asa & sdfsdf & df 
\end{bmatrix}
$$
