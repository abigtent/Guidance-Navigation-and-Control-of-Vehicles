---
title: 
draft: false
tags:
  - kinematics
---
The **FLOW** frame is a body- fixed reference frame used to express the hydrodynamic forces and moments acting on the marine craft. The **FLOW** axes are found by rotation the **BODY** axes such that the resulting *x_f* axis is parallel to the freestream flow. 

### Definitions
![[crab boat.png]]
#### Course angle 
$$
\chi
$$
[Cardinal](https://en.wikipedia.org/wiki/Cardinal_direction) direction in which the vessel is moving.

#### Heading (yaw) angle
$$
\psi
$$
The direction the crafts [bow](https://en.wikipedia.org/wiki/Bow_(watercraft)) is pointing.

#### Crab angle 
$$
\beta_{c}
$$
Difference between the course angle and the heading angle.
$$
\chi = \psi + \beta_{c}
$$
$$
\beta_{c} = \text{atan2}(v,u)
$$
### Crab angle versus sideslip angle
Aircraft operate in the wind while marine craft operate in conditions with waves, currents and also wind.

These conditions have an impact on the velocity of the vehicle and produces relative velocities:

$$
\begin{align*}
u_{r} = u - u_{f} \\
v_{r} = v - v_{f}
\end{align*}
$$
where *u_f* and *v_f* is flow due to conditions.

**Lift** will be **perpendicular** and *drag* will be *parallel* to the relative flow. The 2-D linear velocities can be expressed as:

$$
\begin{align*}
u_{r} = U_{r}\cos(\beta) \\
v_{r} = U_{r}\sin(\beta)
\end{align*}
$$
$$
U_{r} = (u^2_{r} + v^2_{r})^{1/2}
$$

**Crab angle** is the angle between the direction the vehicle is moving due to external forces such as ocean currents, waves or winds and the heading of the vessel. 

**Sideslip angle** is the angle between the *x_b* axis of the vehicle and the direction of the flow velocity.

#### Interesting observations

1) A vehicle moving on a straight line in calm water will have zero crab angle.
2) As soon as the vehicle is turning, the sway velocity will be non-zero and the crab angle will be non-zero. The crab angle corresponds to the amount of correction a vehicle must be turned to maintain the desired course. 
3) A flow velocity (wind/current) is induced if the vehicle is exposed to environmental forces. The environmental force will change both *v* and **U** trough the equations of motion, thus the crab angle. 

**Sideslipping is caused by a nonzero crab angle, not the sideslip angle.**

### Ocean current triangle: vertical plane
![[triangle.png]]

### Summary: Angle of attack and sideslip angle
![[angleofattack.png]]
