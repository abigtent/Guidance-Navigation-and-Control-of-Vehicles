
### Successive loop closure
![[successive loop.png]]

The inner loop is a unit- loop up to the bandwidth $\omega_{b_{1}}$.
The middle loop is a unit- loop up to the bandwidth $\omega_{b_{2}}$.

The bandwidth of the inner loop should be 5-10 times faster than the outer loop.
$$
\omega_{b_{2}} < (5-10)\omega_{b_{1}}
$$
### Saturation limits
![[saturation.png]]
The control signal $u$ is largest immediately after a step on $y_c$, at which point the output of the differentiator is essentially zeros. Therefore $u \approx k_{p}e$. Let $u^{max}$ be the input saturation limit, and $e^{max}$, the largest expected step, then set
$$
k_{p}=\frac{u^{max}}{e^{max}}
$$
The closed loop transfer function is:
$$
Y(s)=\frac{b_{0}k_{p}}{s^2+(a_{1}+b_{0}k_{d})+(a_{0}+b_{0}k_{p})}Y^c(s)=\frac{\omega^2_{n}}{s^2+2\zeta \omega_{n}s+\omega^2_{n}}Y^c(s)
$$
Equation terms gives
$$
\omega_{n}=\sqrt{ a_{o}+b_{0}k_{p} }
$$
$$
k_{d}=\frac{2\zeta \omega_{n}-a_{1}}{b_{0}}
$$



### Lateral-directional autopilot
DOF 2,4,6 is called lateral dynamics. 
![[lateral autopilot.png]]

Roll rate $\dot{\phi} \approx p$, integrate to find roll angle. We neglect q and r. 
So the roll equation gets integrated twice to end up with the roll angle. 

The inner loop should be approximately 1. So the commanded roll angle should be almost the same as the roll angle calculated in the inner loop. 

#### Roll autopilot
![[roll_auto.png]]

Design parameters are $e^{max}_{\phi}$ and $\zeta_{\phi}$.

Gains are given by:
$$
k_{p_{\phi}}=\frac{\delta^{max}_{a}}{e^{max}_{\phi}}
$$
$$
k_{d_{\phi}}=\frac{2\zeta \omega_{n_{\phi}}-a_{\phi_{1}}}{a_{\phi_{2}}}
$$
A good suggestion is to not have any integrators inside the inner loops, including the roll loop. 
- Integrators add delay and instability, not optimal for inner loops. 
- An integrator will be used on the course loop to correct for steady-state errors. 

By removing the integrator in the inner loop, we might get a stationary error, but this will be fixed by the outer loops integrator. 

#### Course hold autopilot
![[Skjermbilde 2024-09-10 133633.png]]
For the course loop, note the presence of the input disturbance. Using a PI controller for course, the response to the course command and disturbance is given by:

![[Skjermbilde 2024-09-10 133649.png]]

Note:
- There is a zero in the response to the course command c. 
- The presence of the zero at the origin ensures rejection of low frequency disturbances.

![[Skjermbilde 2024-09-10 134132.png]]

Equation coefficients to canonical TF gives:
$$
\omega^2_{n_{\chi}}=\frac{k_{i_{\chi}}g}{V_{g}}
$$
$$
2\zeta_{\chi}\omega_{n_{\chi}}=\frac{k_{p_{\chi}}}{V_{g}}
$$
or
$$
\omega_{n_{\chi}}=\frac{1}{W_{\chi}}\omega_{n_{\phi}}
$$
$$
k_{p_{\chi}}=\frac{2\zeta_{\chi}\omega_{n_{\chi}}V_{g}}{g}
$$
$$
k_{i_{\chi}}=\frac{\omega^{2}_{n_{\chi}}V_{g}}{g}
$$
Design parameters are bandwidth separation $W_{\chi}$ and damping ratio $\zeta_{\chi}$.

#### Sideslip hold autopilot

It is necessary to have a autopilot that regulates sideslip $\beta$ to 0. 
![[sideslip hold.png]]


#### Summary 

If model is known the design parameters are:

##### Inner loop (roll attitude hold)
- $e^{max}_{\phi}$ - Error in roll when aileron just saturates.
- $\zeta_{\phi}$ - Damping ratio for roll attitude loop.

##### Outer loop (course hold)
- $W_{\chi} > 1$ - Bandwidth separation between roll and course loops.
- $\zeta_{\chi}$ - Damping ratio for course hold loop.

##### Sideslip hold (if rudder is available)
- $e^{max}_{\beta}$ - Error in sideslip when rudder just saturates.
- $\zeta_{\beta}$ - Damping ratio for sideslip loop

### Longitudinal- directional autopilot 

#### Longitudinal flight regimes
![[Skjermbilde 2024-09-13 143830.png]]

#### Longitudinal transfer function - Pitch

The differential equation model is 
$$
\ddot{\theta} = -a_{\theta_{1}}\dot{\theta}-a_{\theta_{2}}\theta+a_{\theta_{3}}\delta_{e}+d_{\theta_{2}}
$$
with associated transfer function:
$$
\theta(s)=\left( \frac{a_{\theta_{3}}}{s^2+a_{\theta_{1}}s+a_{\theta_{2}}} \right)\left( \delta_{e}(s)+\frac{1}{a_{\theta_{3}}}d_{\theta_{2}}(s) \right)
$$
![[Skjermbilde 2024-09-13 144951.png]]

##### Deriving the transfer function from elevator to pitch angle
![[Skjermbilde 2024-09-13 145028.png]]

#### Pitch attitude hold autopilot
![[Skjermbilde 2024-09-13 145247.png]]

##### Altitude hold using commanded pitch
![[Skjermbilde 2024-09-13 153851.png]]

Provided pitch loop functions as intended, we can simplify the inner-loop dynamics to $\theta^c/\theta \approx K_{\theta_{DC}}$.

##### Longitudinal transfer function - Altitude from pitch

To derive a transfer function from pitch to altitude (assuming constant air speed):
$$
\dot{h}=u\sin \theta-v\sin \phi \cos \theta-w\cos \phi \cos \theta \\

$$
$$
=V_{a}\theta+(u\sin \theta-V_{a}\theta)-v\sin \phi \cos \theta-w\cos \phi \cos \theta
$$
$$
=V_{a}\theta+d_{h}
$$
where 
$$
d_{h} = (u\sin \theta)-V_{a}\theta -v\sin \phi \cos \theta-w\cos \phi \cos \theta
$$
The associated transfer function is:
$$
h(s)=\frac{V_{a}}{s}\left( \theta+\frac{1}{V_{a}}d_{h} \right)
$$
![[Skjermbilde 2024-09-13 155155.png]]

##### Altitude from pitch simplified
![[Skjermbilde 2024-09-13 155727.png]]

##### Altitude from pitch gain calculations
![[Skjermbilde 2024-09-13 155826.png]]

#### Longitudinal transfer function - airspeed

Both pitch angle and throttle strongly affect airspeed. We wish to derive this relationship.

If there is no wind, then:
$$
V_{a}=\sqrt{ u^2+v^2+w^2 }
$$
![[Skjermbilde 2024-09-13 160815.png]]
![[Skjermbilde 2024-09-13 161158.png]]'![[Skjermbilde 2024-09-13 162036.png]]

#### Airspeed hold autopilot using commanded pitch
![[Skjermbilde 2024-09-13 162203.png]]

#### Airspeed from pitch gain calculations
![[Skjermbilde 2024-09-13 162225.png]]

#### Airspeed hold autopilot using throttle
![[Skjermbilde 2024-09-13 162352.png]]
![[Skjermbilde 2024-09-13 162427.png]]

#### Altitude control state machine
![[Skjermbilde 2024-09-13 162516.png]]

#### Summary

If model is known, the design parameters are

##### Inner loop (pitch attitude hold)
- $e^{max}_{\theta}$ - Error in pitch when elevator just saturates.
- $\zeta_{\theta}$ - Damping ratio for pitch attitude loop.

##### Altitude hold outer loop
- $W_{h} > 1$ - Bandwidth separation between pitch and altitude loops.
- $\zeta_{h}$ - Damping ratio for altitude hold loop.

##### Airspeed hold outer loop
- $W_{V_{2}}>1$ - Bandwidth separation between pitch and airspeed loops.
- $\zeta_{V_{2}}$ - Damping ratio for airspeed hold loop.

##### Throttle hold (inner loop)
- $\omega_{n_{V}}$- Natural frequency for throttle loop.
- $\zeta_{V}$ - Damping ratio for throttle loop.
