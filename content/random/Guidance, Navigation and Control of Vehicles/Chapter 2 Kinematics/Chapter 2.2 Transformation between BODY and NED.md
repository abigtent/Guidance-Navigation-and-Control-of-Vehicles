### Useful properties

#### **Rotation matrices**
$$
R*R^T = R^T*R = I_{3}
$$
$$
\det(R) = 1
$$
The following notation is used to transform a vector from one coordinate frame to another:
$$
v^{to} = R^{to}_{from}v^{from}
$$

#### **Skew- symmetry of a matrix and cross- product operator**
$$
S = -S^T
$$
The vector cross product is defined by:
$$
\lambda \times a := S(\lambda)a
$$
where
$$
S(\lambda) = -S^T(\lambda) = \begin{bmatrix}
0 & -\lambda_{3} & \lambda_{2} \\ 
\lambda_{3} & 0 & -\lambda_{1} \\ 
-\lambda_{2} & \lambda_{1} & 0
\end{bmatrix}
$$
[Smtrx.m](https://github.com/cybergalactic/MSS/blob/master/LIBRARY/kinematics/Smtrx.m)

The inverse operator is denoted vex(.) such that
$$
\lambda = vex(S(\lambda))
$$
[vex.m](https://github.com/cybergalactic/MSS/blob/master/LIBRARY/kinematics/vex.m)

### Euler angle transformation

$$
R_{z,\psi}(\psi) = \begin{bmatrix} \cos\psi & -\sin\psi & 0 \\ \sin\psi & \cos\psi & 0 \\ 0 & 0 & 1 \end{bmatrix}
$$
$$
R_{y,\theta}(\theta) = \begin{bmatrix} \cos\theta & 0 & \sin\theta \\ 0 & 1 & 0 \\ -\sin\theta & 0 & \cos\theta \end{bmatrix}
$$
$$
R_{x,\phi}(\phi) = \begin{bmatrix} 1 & 0 & 0 \\ 0 & \cos\phi & -\sin\phi \\ 0 & \sin\phi & \cos\phi \end{bmatrix}
$$
#### Linear velocity transformation (zyx convention)
![[1.png]]

[Rzyx.m](https://github.com/cybergalactic/MSS/blob/master/LIBRARY/kinematics/Rzyx.m)
#### Angular velocity transformation(zyx convention)
![[2.png]]

[Tzyx.m](https://github.com/cybergalactic/MSS/blob/master/LIBRARY/kinematics/Tzyx.m)
#### 6 DOF kinematic equations
![[3.png]]

### Unit quaternions
#### Linear velocity transformation
![[quat1.png]]

[Rquat.m](https://github.com/cybergalactic/MSS/blob/master/LIBRARY/kinematics/Rquat.m)
#### Angular velocity transformation
![[quat2.png]]
![[quat3.png]]

[Tquat](https://github.com/cybergalactic/MSS/blob/master/LIBRARY/kinematics/Tquat.m)

#### 6 DOF kinematic equations 7 ODEs
![[quat4.png]]

#### Unit quaternion from euler angles
![[quat6.png]]

[euler2q.m](https://github.com/cybergalactic/MSS/blob/master/LIBRARY/kinematics/euler2q.m)

#### Euler Angles from a unit quaternion
![[quat5.png]]

[q2euler.m](https://github.com/cybergalactic/MSS/blob/master/LIBRARY/kinematics/q2euler.m)