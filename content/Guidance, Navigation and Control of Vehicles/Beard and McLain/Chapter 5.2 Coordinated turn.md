1. Used to find a simpler model between roll and heading/course rate 
2. Can use aileron and roll to change the course over ground 
3. No acceleration along the body y axis during a coordinated turn 
4.  Comfortable for passengers. 
5. No sideslip is assumed during a coordinated turn 
6. It is defined in Beard & McLain, but the assumptions are not described thoroughly
![[coordinated turn.png]]
Wish to find a connection between the yaw-rate $\dot{\psi}$ and roll- angle $\phi$.

$$
\delta_{a}\to \phi\to \psi
$$

Wish to change to **aileron** to initiate a change in **roll** that in turn results in a change of **heading**.

![[Skjermbilde 2024-09-09 135337.png]]

**Lift** is decomposed into **two** equations when initiating a turn from level flight. 

$$
F_{lift}\sin \phi \cos(\chi-\psi)=\frac{mv^2}{R}=mv\omega=m(V_{g}\cos \gamma)\dot{\chi}
$$
$$
F_{lift}\cos \phi=mg\cos \gamma
$$

Dividing the two expressions gives:
$$
\dot{\chi}=\frac{g}{V_{g}}\tan \phi \cos(\chi-\psi)
$$
which is the coordinated turn condition in wind.

In the absence of wind we have $Va = Vg$ and $\psi = \chi$  which gives:
$$
\dot{\psi}=\frac{g}{V_{a}}\tan \phi
$$
which is the expression commonly seen in the literature.

#### Turning radius
The turning radius is given by:

$$
R=\frac{V_{g}\cos \gamma}{\dot{\chi}}=\frac{V^2_{g}\cos \gamma}{g\tan \phi \cos(\chi-\psi)}
$$
For level flight in the absence of wind we have the standard formula:
$$
R=\frac{V^2_{a}}{g\tan \phi}
$$
