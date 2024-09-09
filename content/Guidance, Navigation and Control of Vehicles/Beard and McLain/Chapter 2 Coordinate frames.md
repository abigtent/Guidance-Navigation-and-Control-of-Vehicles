### Inertial frame and vehicle frame
![[intertial_frame.png]]
1) Vehicle frame has same orientation as inertial frame.
2) Vehicle frame is fixed at **CG** of aircraft
3) Inertial and vehicle frames are referred as NED frames

### Vehicle-1 frame 
![[vehicle_1.png]]
1) Rotation around z-axis of vehicle frame
2) This rotation is defined as the **heading angle**

Rotation from vehicle to vehicle-1 frame is defined as:
$$
R^{v_{1}}_{v}(\psi) = \begin{bmatrix}
\cos \psi & \sin \psi & 0 \\
-\sin \psi & \cos \psi & 0  \\
0 & 0 & 1
\end{bmatrix}
$$
### Vehicle-2 frame
![[vehicle_2.png]]
1)  Rotation around y-axis of vehicle-1 frame
2) This rotation is defined as the **pitch angle**
3) Euler angle singularity at $90^o$ also called gimbal lock

Rotation from vehicle-1 frame to vehicle-2 frame is defined as:
$$
R^{v_{2}}_{v_{1}}(\psi) = \begin{bmatrix}
\cos \theta & 0 & -\sin \theta \\
0 & 1 & 0  \\
\sin \theta & 0 & \cos \theta
\end{bmatrix}
$$

### Body frame
![[body_frame.png]]
1) Rotation around x-axis of vehicle-2 
2) This rotation is called **roll angle**

Rotation from vehicle-2 frame to body frame is defined as:
$$
R^{b}_{v_{2}}(\phi) = \begin{bmatrix}
1 & 0 & 0 \\
0 & \cos \phi & \sin \phi  \\
0 & -\sin \phi & \cos \phi
\end{bmatrix}
$$
### Stability frame
![[Stability frame.png]]
This frame helps us rigorously define **angle of attack** and is useful for analyzing stability of aircraft.

Rotation from body frame to stability frame is defined as:
$$
R^s_{b}(\alpha) = \begin{bmatrix}
\cos \alpha & 0 & \sin \alpha \\
0 & 1 & 0 \\
-\sin \alpha & 0 & \cos \alpha
\end{bmatrix}
$$

### Wind frame
![[wind_frame.png]]
1) Wind frame is equal to flow frame in Fossen
2) Wind frame helps us rigorously define side-slip angle
3) **Side-slip** angle is nominally zero for tailed aircraft

Rotation from stability frame to wind frame is define as:
$$
R^w_{s}(\beta)=\begin{bmatrix}
\cos \beta & \sin \beta & 0 \\
-\sin \beta & \cos \beta & 0 \\
0 & 0 & 1
\end{bmatrix}
$$
### Airspeed, wind speed and ground speed
$$
V_{a}= \text{airspeed}
$$
$$
V_{w}=\text{windspeed}
$$
$$
V_{g}=\text{groundspeed}
$$
![[wind_triangle.png]]

$$
V_{a}=V_{g}-V_{w}
$$
$$
V^b_{g} = \begin{bmatrix}
u \\
v \\
w 
\end{bmatrix} \to \text{speed over ground in body frame}
$$
$$
V^b_{w}=\begin{bmatrix}
u_{w} \\
v_{w} \\
w_{w}
\end{bmatrix} = R^b_{v}(\phi,\theta,\psi)\begin{bmatrix}
w_{n} \\
w_{e} \\
w_{d}
\end{bmatrix} \to \text{windspeed in body}
$$
$$
V^w_{a}=\begin{bmatrix}
V_{a} \\
0 \\
0
\end{bmatrix} \to \text{wind frame air speed}
$$

### Airspeed, angle of attack and sideslip angle
![[angle_of_attack.png]]
$$
V^b_{a}=\begin{bmatrix}
u_{r} \\
v_{r} \\
w_{r}
\end{bmatrix} = R^b_{w}\begin{bmatrix}
V_{a} \\
0 \\
0
\end{bmatrix} \to \text{relative velocity in body (airspeed)}
$$
$$
\begin{bmatrix}
u_{r} \\
v_{r} \\
w_{r}
\end{bmatrix}=V_{a}\begin{bmatrix}
\cos \alpha \cos \beta \\
\sin \beta \\
\sin \alpha \cos \beta
\end{bmatrix} \to \text{airspeed in body}
$$
$$
V_{a} =\sqrt{ u^2_{r}+v^2_{r}+w^2_{r} } \to \text{amplitude in airspeed}

$$
$$
\alpha = \tan^{-1}\left( \frac{w_{r}}{u_{r}} \right) \to \text{angle of attack}
$$
$$
\beta=\sin^{-1}\left( \frac{v_{r}}{\sqrt{  u^2_{r}+v^2_{r}+w^2_{r} }} \right) \to \text{sideslip}
$$
### Course and flight path angles
![[flight_path.png]]

### Wind triangle horizontal projection
![[wind_triangle_hor.png]]

### Wind triangle vertical plane
![[wind_triangle_vert.png]]
