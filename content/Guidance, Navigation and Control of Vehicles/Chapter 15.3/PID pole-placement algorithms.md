PID controllers can be applied to a large number of industrial motion control systems including dynamic- positioning systems, autopilots for steering and diving as well as path- following control systems. 

### Linear mass-damper-spring system 

$$
\begin{align*}
m\ddot{x} + d\dot{x} + kx = 0 \\
\ddot{x} + 2\zeta \omega_{n}\dot{x} + \omega^2_{n} = 0
\end{align*}
$$
These two equations are equal. In the first equation d is equal to the damping term and k is equal to the spring constant. The second equations includes the natural damping ratio omega and relative damping factor zeta.
$$
2\zeta \omega_{n} = \frac{d}{m},\text{ } \omega^2_{n} = \frac{k}{m}
$$
$$
\omega_{n} = \sqrt{ \frac{k}{m} }
$$
$$
\zeta = \frac{d}{2m\zeta_{n}}
$$
$$
\lambda_{1,2} = -\zeta \omega_{n} \pm j\omega
$$
#### Damped oscillator
For a damped system d > 0, the frequency of the oscillations will be smaller than the natural frequency of the undamped system. 

For a marine craft a reduction of 0.5% in the natural frequency is common.
$$
r = 1 - \frac{0.5}{100} = 0.995
$$
$$
\omega = r\omega_{n}
$$
$$
a^2 + (r\omega_{n})^2 = \omega^2_{n}
$$
$$
a = \sqrt{1-r^2} \omega_{n}
$$
The term under the square root is equal to the relative damping ratio.
**Undamped oscillator: a = 0**

![[Mass_damping.png]]

#### Heave, roll and pitch damping
To determine the linear damping in heave, roll and pitch, we use the following formula for linear damping:

$$
d = 2\zeta \sqrt{km}, \text{ } \zeta = \sqrt{ 1 -r^2 }
$$
where **r** is the design parameter.

#### Surge, sway and yaw damping
To determine the damping in these states we need to treat each of them as a pure mass-damper system. Linear damping for such a system can be found by specifying the time constant T > 0 corresponding to:
$$
m\ddot{x} + \dot{x} = \tau
$$
which for the design parameter T = m/d is equivalent to
$$
T\ddot{x} + \dot{x} = \frac{1}{d}\tau
$$
This yields the following design formula for linear damping
$$
d = \frac{m}{T}
$$
(For marine craft we can specify the time constant).

### SISO linear PID control

##### PD control law applied to a mass damper spring system:![[PID.png]]

##### Closed loop system:
$$
m\ddot{x} + (d + K_{d})\dot{x} + (k + K_{p})\tilde{x} = 0
$$
##### PID pole-placement formulas:
$$
K_{p} = m\omega^2_{n} - k
$$
$$
K_{d} = 2\zeta \omega_{n}m-d
$$
$$
K_{i} = \frac{\omega_{n}}{10}K_{p} = \frac{\omega_{n}}{10}(m\omega^2_{n}-k)
$$
(integral time should be 10 times slower than the natural frequency)


##### Relationship between natural frequency and control bandwidth
$$
\omega_{b} = \omega_{n}\sqrt{1-2\zeta^2+\sqrt{ 4\zeta^4-4\zeta^2+2 }}
$$
For a critically damped system with relative damping ratio = 1, this expression reduces to:

$$
\omega_{b} = \omega_{n}\sqrt{ \sqrt{ 2 }-1 } \approx 0.64\omega_{n}
$$
Control bandwidth gives us information about how fast of a reference we can follow.

##### Main result (PID controller tuning rule)
![[pid2.png]]![[pid_3.png]]