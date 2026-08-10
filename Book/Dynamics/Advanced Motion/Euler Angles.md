---
tags: [dynamics, pre-release]
---
#dynamics #pre-release

## Definition
> [!definition]
> **Euler angles** are a set of three scalar angles that parameterize any 3D orientation as a sequence of three elementary rotations about coordinate axes. The most common engineering convention is **ZYX** (yaw–pitch–roll): rotate first about $z$ by yaw $\psi$, then about the new $y$-axis by pitch $\theta$, then about the newest $x$-axis by roll $\phi$. Because [[Rotation Order Matters]], the convention (which axes, in which order) must be specified explicitly.

Notes:
- There are 12 valid Euler-angle conventions (and even more if you allow repeated axes, like ZYZ used in aerospace). **ZYX (yaw–pitch–roll)** is standard in robotics and drones; ZYZ is common in aerospace rigid-body dynamics. Never mix conventions without converting.
- The three angles are **not independent coordinates on a flat space** — they live on $SO(3)$, a curved manifold. This causes [[Gimbal Lock]]: at certain angle combinations, two rotation axes align and one DOF is lost.
- The combined rotation matrix (ZYX convention):
$$R = R_z(\psi)\,R_y(\theta)\,R_x(\phi)$$
Because of [[Rotation Order Matters]], this product is applied right-to-left: roll first, then pitch, then yaw.
- Euler angles are intuitive for humans to visualize (roll–pitch–yaw of an aircraft or drone is easy to picture) but have computational disadvantages: singularities at gimbal lock, and interpolation between two orientations does not produce physically meaningful intermediate orientations.
- For the 6-axis industrial arm, the end-effector orientation is often commanded in Euler angles, but internal computations use rotation matrices or [[Quaternion (Intro)|quaternions]] to avoid singularities.
- When reading sensor data (IMUs, AHRS): most output roll–pitch–yaw in ZYX convention, but some use ZYZ or other orderings. Always verify the convention in the datasheet.

## Equations

> [!equation] ZYX Euler angle composition (yaw–pitch–roll)
> $$R(\phi, \theta, \psi) = R_z(\psi)\,R_y(\theta)\,R_x(\phi)$$
>
> - $\psi$ — yaw (rotation about $z$, horizontal heading)
> - $\theta$ — pitch (rotation about new $y$, nose up/down)
> - $\phi$ — roll (rotation about newest $x$, banking)
> - Applied right-to-left: roll first, then pitch, then yaw

## Examples and Non-Examples

- **Drone attitude.** A quadrotor has roll $\phi = 10°$, pitch $\theta = -5°$, yaw $\psi = 90°$ (facing east). These three numbers, in ZYX order, fully describe its orientation. The flight controller uses $R = R_z(90°)R_y(-5°)R_x(10°)$ internally to transform body-frame accelerometer readings into world-frame accelerations.

- **6-axis arm end-effector.** The end-effector orientation is commanded as $(\phi, \theta, \psi) = (0°, 90°, 45°)$ in ZYX — the tool points straight down (pitch 90°) and is rotated 45° about the vertical. The robot controller converts this to a rotation matrix before computing the inverse kinematics.

- **Counter-example — ZYZ vs. ZYX for the same angles.** $R_{ZYX}(30°, 45°, 60°) \neq R_{ZYZ}(30°, 45°, 60°)$. The same three numbers produce different orientations in different conventions. When importing orientation data, confirming the convention is not optional.

## Resources

- ![](https://www.youtube.com/watch?v=zjMuIxRvygQ)
- **[Modern Robotics — Chapter 3: Rigid-Body Motions playlist](https://www.youtube.com/playlist?list=PLggLP4f-rq01NLHOh2vVPPJZ0rxkbVFNc)**
- **[Wikipedia — Euler angles](https://en.wikipedia.org/wiki/Euler_angles)**
