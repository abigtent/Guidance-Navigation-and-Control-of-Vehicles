$$
\begin{gather}
f^b_{b} = \begin{bmatrix} X&Y&Z \end{bmatrix}^T \text{--- force trough the CO expressed in body frame} \\
m^b_{b} = \begin{bmatrix} K&M&N \end{bmatrix}^T \text{--- moment about the CO expressed in body frame} \\
v^b_{b} = \begin{bmatrix} u&v&w \end{bmatrix}^T \text{--- linear velocity of the CO relative to origin of NED frame expressed in body frame} \\
\omega^b_{b} = \begin{bmatrix} p&q&r \end{bmatrix}^T \text{--- angular velocity of body frame relative to NED frame expressed in body frame} \\
r^b_{b} = \begin{bmatrix} x_{g}&y_{g}&z_{g} \end{bmatrix}^T \text{--- vector from the CO to the CG expressed in body frame}
\end{gather}
$$
#### Rigid-body system inertia matrix
![[intertia_matrix.png]]

[rbody.m](https://github.com/cybergalactic/MSS/blob/master/LIBRARY/modeling/rbody.m)

#### Coriolis- centripetal matrix from system inertia matrix
![[coriolis.png]]

#### Lagrangian parameterization
![[lagrangian.png]]

[m2c.m](https://github.com/cybergalactic/MSS/blob/master/LIBRARY/modeling/m2c.m)

#### Linear velocity- independent parameterization
![[linear_velocity.png]]

Can also be computed for nonzero values of:
$$
r^b_{bg}
$$
$$

$$
![[linear_velocity_2.png]]
