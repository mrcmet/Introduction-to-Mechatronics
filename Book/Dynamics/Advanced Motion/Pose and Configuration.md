---
tags: [dynamics, pre-release]
---
#dynamics #pre-release

## Definition
> [!definition]
> **Pose** is the complete geometric description of a rigid body's state in space: its position (where it is) plus its orientation (how it is rotated). **Configuration** is the set of all coordinates needed to fully specify the pose of a system — it lives in a mathematical space called the **configuration space** (or **C-space**). Knowing the configuration tells you exactly where every point of the system is.

Notes:
- A free rigid body in 3D has **6 degrees of freedom** — 3 for position $(x, y, z)$ and 3 for orientation (e.g., [[Euler Angles]] roll, pitch, yaw). Its configuration space is therefore 6-dimensional.
- In 2D (planar motion), a rigid body has 3 DOF: $(x, y, \theta)$. A wheeled robot restricted to the floor lives in a 3D configuration space.
- The configuration space is not always flat (Euclidean). Orientation lives on the rotation group $SO(3)$, which is a curved manifold — this is why [[Euler Angles]] have singularities ([[Gimbal Lock]]) and why [[Quaternion (Intro)|quaternions]] are sometimes preferred.
- For a robot arm, the configuration is the vector of joint angles $\boldsymbol{\theta} = [\theta_1, \theta_2, \ldots, \theta_n]^T$. Each joint angle is one coordinate of the configuration space. The arm's pose (end-effector position and orientation in the world) is then computed from the configuration via [[Forward Kinematics]].
- **Pose vs. configuration:** For a robot arm, "configuration" refers to the joint angles; "pose" refers to the end-effector's position and orientation in the world frame. They are related but distinct — one configuration maps to one pose ([[Forward Kinematics]]), but one pose may correspond to multiple configurations ([[Inverse Kinematics]]).
- A [[Homogeneous Transformation]] matrix $T \in SE(3)$ is the standard compact representation of a 3D pose.

## Examples and Non-Examples

- **6-axis arm configuration.** A 6-axis industrial robot arm has configuration $\boldsymbol{\theta} = [30°, -45°, 90°, 0°, 60°, 180°]^T$. This single vector of six joint angles completely determines where the arm is — every link position and the end-effector pose can be computed from it via [[Composing Transformations]].

- **Drone pose.** A drone has pose $(x, y, z, \phi, \theta, \psi) = (2.1, -0.5, 3.0,\ 0°, 5°, 90°)$ in the world frame: it is at height 3 m, slightly pitched forward 5°, and facing east (90° yaw). This 6-number tuple is the complete description of its instantaneous pose.

- **Counter-example — velocity is not pose.** Velocity tells you how quickly the configuration is changing, not what the configuration is. Two drones at the same pose but with different velocities have the same configuration but are in different *states*. The full state of a dynamical system typically includes both configuration and velocity.

## Resources

- ![](https://www.youtube.com/watch?v=29LhXWjn7Pc)
- **[Modern Robotics — Chapter 2: Configuration Space](https://www.youtube.com/playlist?list=PLggLP4f-rq02vX0OQQ5vrCxbJrzamYDfx)**

## Practice

- A planar robot arm has two revolute joints. Joint 1 angle is $\theta_1 = 45°$ and joint 2 angle is $\theta_2 = -30°$. (a) What is the configuration of this arm? (b) Is this the same as the end-effector's pose? Explain.

> [!NOTE]- Answer
> **(a)** The configuration is the vector of joint angles: $\boldsymbol{\theta} = [45°, -30°]^T$. This is a point in a 2D configuration space.
>
> **(b)** No — the configuration and the end-effector pose are related but not the same thing. The configuration lives in joint space (angles). The end-effector pose lives in task space (position + orientation in the world frame). To find the pose from the configuration, you apply [[Forward Kinematics]].
