---
tags: [dynamics, pre-release]
---
#dynamics #pre-release

## Definition
> [!definition]
> The **degrees of freedom** (DOF) of a system is the minimum number of independent coordinates needed to fully specify its [[Pose and Configuration|configuration]]. Each DOF represents one independent way the system can move. Adding a constraint (a joint, a contact, a rigid connection) removes one or more DOF from a body that would otherwise be free.

Notes:
- A free rigid body in 3D has **6 DOF**: 3 translational (x, y, z) and 3 rotational (roll, pitch, yaw). In 2D, a free rigid body has **3 DOF**: (x, y, θ).
- A **joint** connects two bodies and constrains their relative motion. Different joint types remove different numbers of DOF:

| Joint type | Motion allowed | DOF provided | DOF removed (from 6) |
|---|---|---|---|
| Revolute (pin) | Rotation about 1 axis | 1 | 5 |
| Prismatic (slider) | Translation along 1 axis | 1 | 5 |
| Ball-and-socket | Rotation about 3 axes | 3 | 3 |
| Fixed (weld) | None | 0 | 6 |

- For an **open-chain robot arm**, the total DOF equals the sum of the DOF of each joint: a 6-axis arm with six revolute joints has 6 DOF. This is the minimum needed to place an end-effector at any position and orientation in 3D space.
- **Redundant** robots have more DOF than needed for the task (e.g., 7-DOF arm for a 6-DOF task). Extra DOF give flexibility to avoid obstacles or optimize posture.
- **Underactuated** systems have fewer actuators than DOF — they cannot independently control all their degrees of freedom. The two-wheeled balancing robot has 3 DOF (x, θ_wheel, θ_body) but fewer independently controlled inputs, making balance a control problem rather than a kinematic one. See [[Underactuated System]].
- DOF is a property of the *system*, not the mechanism alone. Constraints from the environment (a wheel rolling on the ground, a cable in tension) also reduce DOF.

## Examples and Non-Examples

- **6-axis industrial arm.** Each of the six joints is revolute (1 DOF each), so the arm has 6 DOF total. This matches the 6 DOF of a rigid body in space — the arm can reach any position and orientation within its workspace (subject to joint limits and reachability).

- **Self-balancing two-wheeled robot.** The robot body can translate forward/backward and rotate about the wheel axis — 2 relevant DOF for the control problem. The constraint that the wheels roll without slipping on the floor is a nonholonomic constraint that connects the translational and rotational DOF. See [[Holonomic and Nonholonomic Constraints]].

- **Counter-example — mechanisms with many links but few DOF.** A rigid four-bar linkage has four links and four joints, but after applying the Grübler formula to planar systems, it turns out to have only 1 DOF — turning one link determines all others. More links does not mean more DOF; joints remove DOF just as fast.

## Resources

- ![](https://www.youtube.com/watch?v=hBrHcHpMXmY)
- **[Modern Robotics — Chapter 2.1: Degrees of Freedom of a Rigid Body](https://www.youtube.com/playlist?list=PLggLP4f-rq02vX0OQQ5vrCxbJrzamYDfx)**
- **[Modern Robotics — Chapter 2.2: Degrees of Freedom of a Robot](https://www.youtube.com/playlist?list=PLggLP4f-rq02vX0OQQ5vrCxbJrzamYDfx)**

## Practice

- A robotic wrist has three revolute joints stacked in series (all axes intersecting at one point). (a) How many DOF does this wrist have? (b) What motions can it produce? (c) What task-space capability is missing compared to a full 6-DOF arm?

> [!NOTE]- Answer
> **(a)** 3 revolute joints × 1 DOF each = **3 DOF**.
>
> **(b)** The three intersecting axes allow rotation in any direction — roll, pitch, and yaw about the wrist center. This is a ball-and-socket equivalent in joint form.
>
> **(c)** The wrist has no translational DOF. It can orient the end-effector at any angle but cannot move it to a different position in space. A full arm adds 3 more DOF (e.g., shoulder + elbow joints) to provide 3D positioning.
