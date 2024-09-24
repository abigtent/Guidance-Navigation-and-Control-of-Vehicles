
## Longitudinal stability analysis

For conventional aircraft the  characteristic equation is of the 4-th order:

$$
(\lambda^2+2\zeta_{ph}\omega_{ph}\lambda+\omega^2_{ph})(\lambda^2+2\zeta_{sp}\omega_{sp}\lambda+\omega^2_{sp}) = 0
$$
where **ph** and **sp** denote the the following modes:

- Short period mode (largest natural frequency)
- Phugoid mode

The **phugoid** mode is observed as a long period oscillation with little damping. In some cases the phugoid mode can be unstable such that the oscillations increase with time.

The **phugoid** mode is characterized by the natural frequency $\omega_{ph}$ and relative damping ratio $\zeta_{ph}$. The **short-period mode** is a fast mode given by the natural frequency $\omega_{sp}$ and relative damping factor $\zeta_{sp}$. The **short period mode** is usually well damped.

Conventional aircraft have usually **two complex conjugated pairs** of phugoid and short- period types.

### Tuck mode

Supersonic aircraft may have a very large aerodynamic coefficient $M_{u}$. This implies that the oscillatory Phugoid equation gives two real solutions where one is positive (unstable) and one is negative (stable). This is referred to as the tuck mode since the phenomenon is observed as a downwards pointing nose (tucking under) for increasing speed.

### A third oscillatory mode:

For fighter aircraft the center of gravity is often located behind the neutral point or the aerodynamic center (the point where the trim moment $M_{w}w$ is zero). When this happens, the aerodynamic coefficient $M_{w}$ takes a value such that the roots of the characteristic equation has four real solutions. When the center of gravity is moved backwards one of the roots of the Phugoid and short-period modes become imaginary and they form a new complex conjugated pair. This is usually referred to as the 3rd oscillatory mode.

## Lateral stability analysis

The lateral characteristic equation is usually of the 5th order:

$$
\lambda(\lambda+e)(\lambda+f)(\lambda^2+2\zeta_{D}\omega_{D}\lambda+\omega^2_{D}) = 0
$$
where the term $\lambda$ in the last equation corresponds to a pure integrator in roll ($\frac{d\psi}{dt} = r$).

The term $(λ + e)$ is the aircraft spiral/divergence mode. This is usually a very slow mode. Spiral/divergence corresponds to horizontally leveled wings followed by roll and a diverging spiral maneuver.

The term $(λ + f)$ describes the subsidiary roll mode while the 2nd-order system is referred to as **Dutch roll**. This is an oscillatory system with a small relative damping factor $ζ_{D}$. The natural frequency in Dutch roll is denoted $ω_{D}$