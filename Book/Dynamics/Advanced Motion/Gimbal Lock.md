---
tags: [dynamics, pre-release]
---
#dynamics #pre-release

## Definition
> [!definition]
> **Gimbal lock** is the loss of one rotational degree of freedom that occurs when two rotation axes in an [[Euler Angles|Euler angle]] sequence become aligned. When this happens, the two coincident axes can only produce the same rotation, so one independent direction of rotation is lost — the system can no longer express arbitrary small orientation changes without first moving to a different configuration.

Notes:
- In ZYX (yaw–pitch–roll), gimbal lock occurs when pitch $\theta = \pm90°$. At this angle, the roll axis ($x$ after pitching) aligns with the yaw axis ($z$), and any combination of roll and yaw produces the same net rotation. One degree of freedom vanishes.
- Gimbal lock is a singularity of the Euler angle *parameterization*, not of the physical orientation space $SO(3)$ itself. The body can still occupy that orientation; it just cannot be described uniquely by Euler angles near that point.
- In practice, gimbal lock shows up as: (1) numerical instabilities in Euler-angle-based calculations, (2) jerky animation interpolation, (3) erratic IMU output when an aircraft points straight up or down.
- **Avoidance strategies:**
    - Use [[Quaternion (Intro)|quaternions]] for internal representation and convert to Euler angles only for display.
    - Use a different Euler convention if the singularity falls outside your operating range.
    - Add a singularity check and switch representations when near the singular configuration.
- The physical gimbal lock of a mechanical gyroscope (a common classroom demo) is the same phenomenon: when two gimbal rings align, the gyroscope loses its ability to rotate freely about one axis.
- For the 6-axis industrial arm, the analogous phenomenon is [[Kinematic Singularity]] — a robot configuration where the Jacobian loses rank and the arm loses one or more task-space DOF instantaneously.

## Examples and Non-Examples

- **Aircraft pitching vertical.** A drone using ZYX Euler angles climbs steeply and reaches pitch $\theta = 90°$ (pointing straight up). At this instant, roll and yaw both rotate the body about the world $z$-axis — they are indistinguishable. If the flight controller tries to change heading (yaw) at this instant using Euler angle math, it will fail or produce unexpected motion.

- **Camera gimbal.** A 3-axis camera gimbal mounts the roll ring inside the pitch ring inside the yaw ring. If the camera pitches 90° forward, the roll ring and yaw ring align. Rotating the yaw motor now also rolls the camera — the yaw control input has lost its independent effect. Operators tilt the camera back to avoid this configuration.

- **Counter-example — singularity of representation, not of space.** A body can smoothly pass through the gimbal-lock orientation (pitch = 90°) with no physical discontinuity. The problem appears only in the Euler angle numbers, not in the physics. A quaternion representation tracks the same motion without any singularity.

## Resources

- ![](https://www.youtube.com/watch?v=zc8b2Jo7mno)
- **[Wikipedia — Gimbal lock](https://en.wikipedia.org/wiki/Gimbal_lock)**
