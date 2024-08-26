---
title: 
draft: false
tags:
  - kinematics
---

A point on or above the earth's surface is uniquely determined by:
$$
\begin{align*} \text{Longitude} &\to l \text{ (deg)} \\ \text{Latitude} &\to \mu \text{ (deg)} \\ \text{Ellipsoidal height} &\to h \text{ (m)} \end{align*}
$$
### Longitude and latitude transformation
Transformation of velocity vectors:
$$
\dot{p}^{e}_{eb} = R^e_{n}\dot{p}^n_{eb} = R^e_{n}R^n_{b}v^b_{eb}
$$
![[ecef_1.png]]

MSS toolbox Rll(l,mu)

### Longitude and latitude from ECEF coordinates
Satellite navigation system measurements are given in the ECEF frame, not very useful. It is then beneficial to express it in terms of longitude, latitude and height.
![[ecef_2.png]]

MSS toolbox ecef2llh(x,y,z)

### ECEF coordinates from longitude/latitude
![[ecef_3.png]]

MSS toolbox llh2ecef

