
### Earth- centered reference frames

*{i}: The Earth- centered inertial reference frame (ECI)*
$$
{i} = (x_{i}, y_{i}, z_{i})
$$

*{e}: The Earth- centered- fixed reference frame (ECEF)* 
$$
e = (x_{e},y_{e},z_{e})
$$
Has its origin fixed to the center of the earth but the axes rotate relative to the intertial frame ECI.
![[Skjermbilde 2024-08-21 kl. 21.57.39.png]]

#### **Geographic reference frames (tangent planes)**

*<span style="font-weight:bold; color:rgb(255, 192, 0)">Usually chosen as tangent planes on the surface of the earth</span>*

*{n}: The North-East-Down reference frame* 
$$
n = (x_{n},y_{n},z_{n})
$$
Has its origin defined relative to the Earth´s reference ellipsoid ([WGS 84](https://no.wikipedia.org/wiki/World_Geodetic_System)), usually as the tangent plane to the ellipsoid with
$$ \begin{align*} x_{n} &\to \text{axis points towards true north} \\ y_{n} &\to \text{axis points towards east} \\ z_{n} &\to \text{axis points downwards normal to the earth's surface} \end{align*} $$


***Terrestrial navigation:***
The tangent plane moves with the craft and its location is specified by time-varying longitude-latitude values. It is usually rotated such that the axes points in the NED directions. 

**Local navigation:**
The tangent plane is fixed at constant values and the position is computed with respect to a local coordinate origin. This plane usually also points in the NED directions. 
![[Skjermbilde 2024-08-21 kl. 21.59.04.png]]

### **Body- fixed reference frames**

*{b}: The body-fixed reference frame (BODY)*
For marine craft, the body axes are chosen as
$$ \begin{align*} x_{b} &\to \text{longitudinal axis (directed from aft to fore)} \\ y_{b} &\to \text{transversial axis (directed to starboard)} \\ z_{b} &\to \text{normal axis (directed from top to bottom)} \end{align*} $$
*{f}: The body-fixed flow axes reference frame (FLOW)*
Flow axes are used to align the x-axis with the craft´s velocity vector such that lift is perpendicular to the relative flow and drag is parallel. 

### **Body- fixed reference points**

![[Skjermbilde 2024-08-21 kl. 21.41.39.png]]
$$ CO \to \text{Coordinate origin of the body fixed frame} $$
$$ \begin{align*} CG &\to \text{Center of gravity} \\ CB &\to \text{Center of buoyancy} \\ CF &\to \text{Center of flotation} \end{align*} $$
### **6- DOF motions** 

6-DOF refers to the freedom of movement of a rigid body in 3-D space. It describes how the object can translate and rotate relative to its own body-fixed axes. **It is not used for NED coordinates.** 

![[Skjermbilde 2024-08-21 kl. 21.52.03.png]]


### **Summary of 6-DOF vectors**

![[Skjermbilde 2024-08-21 kl. 21.55.45.png]]