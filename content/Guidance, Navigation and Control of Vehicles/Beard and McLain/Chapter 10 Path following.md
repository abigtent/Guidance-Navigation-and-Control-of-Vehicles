![[Skjermbilde 2024-09-17 095024.png]]

For small UAVs, a major issue is wind
- Always present to some degree
- Usually significant with respect to commanded airspeed

Wind makes traditional trajectory tracking approaches difficult, if not infeasible.
- Have to know the wind precisely at every instant to determine the desire airspeed

Better approach: path following
Rather than **"follow this trajectory"**, we control the UAV to **"stay on this path"**.

#### Path types

Straight lines between two points in 3-D
- Inclination of path within climb capabilities of UAV
- Circular orbits or arcs in the horizontal plane

Paths for common applications can be built from these path primitives
- Methods for following other types of paths found in literature

We need an **algorithm** for each of the path primitives.

#### Straight line path description
![[Skjermbilde 2024-09-17 101416.png]]

#### Lateral tracking problem
![[Skjermbilde 2024-09-17 101431.png]]

Relative error dynamics in path frame:
$$
\begin{bmatrix}
\dot{e}_{px} \\
\dot{e}_{py}
\end{bmatrix}= \begin{bmatrix}
\cos \chi_{q} & \sin \chi_{q} \\
-\sin \chi_{q} & \cos \chi_{q}
\end{bmatrix}\begin{bmatrix}
V_{g}\cos \chi \\
V_{g}\sin \chi
\end{bmatrix} = V_{g}\begin{bmatrix}
\cos(\chi-\chi_{q}) \\
\sin(\chi-\chi_{q})
\end{bmatrix}
$$
Regulate the cross-track error $e_{py}$ to zero by commanding the course angle:
$$
\dot{e}_{py}=V_{g}\sin(\chi-\chi_{q})
$$
$$
\ddot{\chi}=b_{\dot{\chi}}(\dot{\chi}^c-\dot{\chi})+b_{\chi}(\chi^c-\chi)
$$
Select $\chi^c$ so that $e_{py}\to 0$

$\chi = \chi_{d}$ course autopilot.

#### Longitudinal tracking problem
![[Skjermbilde 2024-09-17 102954.png]]

By similar triangles
$$
\frac{(h_{d}+r_{d})}{\sqrt{ s^2_{n}+s^2_{e} }}=\frac{-q_{d}}{\sqrt{ q^2_{n}+q^2_{e} }}
$$
Desired altitude based on current location
$$
h_{d}(r,p,q)=-r_{d}-\sqrt{ s^2_{n}+s^2_{e}}\left( \frac{q_{d}}{\sqrt{ q^2_{n}+q^2_{e} }} \right)
$$
Select $h^c$ so that $h\to h_{d}(r,p,q)$

##### Longitudinal guidance strategy
![[Skjermbilde 2024-09-17 103500.png]]

#### Lateral tracking- Vector field concept
![[Skjermbilde 2024-09-17 104022.png]]

##### Vector field tuning
![[Skjermbilde 2024-09-17 104121.png]]

$k_{path}$ is a positive constant that affects the rate of transition of the desire course
- $k_{path}$ large -> short, abrupt transition
- $k_{path}$ small -> long, gradual transition

#### Lyapunovs 2nd method

For a system having a state vector $x$, consider an energy like function $V(x)$:
$R^n\to R$ such that

$V(x) \geq \text{(positive definite)}$
$V(x)= 0$ for $x=0$
and
$\dot{V}(x) \leq 0 \text{(negative definite)}$
$\dot{V}(x)=0$ for $x=0$

If such a function $V(x)$ can be defined, then $x$ goes to zero asymptotically and the system is stable. 

#### Lateral tracking stability analysis
![[Skjermbilde 2024-09-17 105251.png]]

#### Smallest angle turn logic
![[Skjermbilde 2024-09-17 105309.png]]

#### Orbit following
![[Skjermbilde 2024-09-17 110142.png]]
![[Skjermbilde 2024-09-17 110215.png]]
![[Skjermbilde 2024-09-17 110225.png]]

##### Algorithm
![[Skjermbilde 2024-09-17 110405.png]]
#### Orbit tracking stability analysis
![[Skjermbilde 2024-09-17 110315.png]]
