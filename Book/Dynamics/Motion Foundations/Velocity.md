---
tags: [dynamics, pre-release]
---
#dynamics #pre-release

## Definition
> [!definition]
> **Velocity** is the time rate of change of [[Position]]. In one dimension it is the signed scalar $v = dx/dt$, where the sign carries direction along the chosen [[Positive Direction]] and the magnitude is the [[Speed]]. For motion in a plane or in space, velocity generalizes to a [[Velocity Vector]] $\mathbf{v}(t) = d\mathbf{r}/dt$ defined relative to a [[Reference Frame]].

Notes:
- Velocity is a **vector quantity**: it has both magnitude and direction. The 1D scalar form $v$ is a shorthand that packs direction into a sign tied to the chosen [[Positive Direction]]. The magnitude alone, with no direction information, is [[Speed]].
- Velocity is the **time derivative of [[Position]]**, $v = dx/dt$. Differentiating it once more in time gives [[Acceleration]]. Position, velocity, and acceleration form a derivative chain that every kinematic equation in this section rests on.
- The sign of $v$ carries physical meaning. A reading of $v = -0.40\ \text{m/s}$ means the point is moving in the negative direction at 0.40 m/s — not that velocity is "0.40 m/s of error." Reversing the sign convention flips the meaning of every downstream controller term.
- Velocity is **frame-dependent**. A passenger walking inside a moving robot has one velocity in the robot frame and a different velocity in the world frame. Always state the [[Reference Frame]] before quoting a number — see [[Relative Velocity]] for the formal transformation.
- Two important specializations live on their own pages. [[Average Velocity]] is the displacement-over-time ratio between two instants; [[Instantaneous Velocity]] is the limit of that ratio as the interval shrinks to zero, i.e. the derivative itself. Most physical "velocity readings" from a sensor are really average velocities over a sample interval.
- For motion that isn't confined to a single axis, switch to the vector form. See [[Velocity Vector]] for the 2D and 3D treatment and [[Coordinate Frames]] for choosing the right basis.

## Equations

> [!equation] Scalar velocity in 1D
> $$v(t) = \frac{dx}{dt}$$
>
> - $v(t)$ — velocity along the chosen axis (m/s)
> - $x(t)$ — [[Position]] as a function of time (m)
> - Sign is set by the chosen [[Positive Direction]]

> [!equation] Vector velocity
> $$\mathbf{v}(t) = \frac{d\mathbf{r}}{dt}$$
>
> - $\mathbf{v}(t)$ — velocity vector (m/s)
> - $\mathbf{r}(t)$ — [[Position Vector]] in a chosen [[Reference Frame]]
> - $|\mathbf{v}|$ — magnitude is the [[Speed]]; see [[Velocity Vector]] for components

## Examples and Non-Examples

- **Worked example — constant-velocity slide.** A linear slide moves so that $x(t) = 0.05 + 0.20\,t$ metres, with $t$ in seconds. Differentiating,
$$v = \frac{dx}{dt} = 0.20\ \text{m/s}$$
The positive sign says the slide is moving in the [[Positive Direction]] of its axis, and the constant value means [[Acceleration]] is zero. The [[Speed]] is also $0.20\ \text{m/s}$ — magnitude only, no sign.

- **Encoder-based velocity (robotics).** A motor encoder samples shaft position every $\Delta t = 1\ \text{ms}$. Between two samples the reported positions are $x_1 = 0.12340\ \text{m}$ and $x_2 = 0.12352\ \text{m}$. A finite-difference estimate of velocity is
$$v \approx \frac{x_2 - x_1}{\Delta t} = \frac{0.12352 - 0.12340}{0.001} = 0.12\ \text{m/s}$$
This is really an [[Average Velocity]] over the 1 ms window — a discrete-time stand-in for the true [[Instantaneous Velocity]] $dx/dt$. The shorter the window, the closer the estimate, until quantization and sensor noise dominate.

- **Sign convention matters.** A two-wheeled balancing robot has its [[Positive Direction]] set as "forward." A velocity reading of $v = -0.30\ \text{m/s}$ means the robot is moving *backward* at 30 cm/s. The controller must respect that sign; a [[Speed]] reading of $0.30\ \text{m/s}$ alone cannot distinguish forward from backward and is not a substitute.

- **Counter-example — speed is not velocity.** A delivery robot circles a charging dock at a steady $0.5\ \text{m/s}$. Its [[Speed]] is constant, but its velocity is *not* constant: the direction is changing continuously, so $\mathbf{v}(t)$ changes even though $|\mathbf{v}|$ does not. Constant speed with changing velocity is exactly what produces centripetal [[Acceleration]] — the magnitude/direction distinction is doing real physics here.

## Resources

- **[CPPMechEngTutorials — Vector Dynamics playlist](https://www.youtube.com/playlist?list=PLZOZfX_TaWAEzhyvNT1e9jbmTt4Eqo8C0)** — engineering-mechanics treatment of position, velocity, and acceleration along a line and in vector form.
- **[Michel van Biezen channel](https://www.youtube.com/@MichelvanBiezen)** — short physics-style worked examples; search the channel for "average velocity" and "instantaneous velocity" for matched pairs.
- **[Wikipedia — Velocity](https://en.wikipedia.org/wiki/Velocity)** — concise reference for the formal definition, units, and contrast with speed.

## Practice

- An encoder on a linear axis reports the following positions at uniform $\Delta t = 10\ \text{ms}$ sample intervals: $x_0 = 0.000\ \text{m}$, $x_1 = 0.004\ \text{m}$, $x_2 = 0.009\ \text{m}$, $x_3 = 0.015\ \text{m}$. The [[Positive Direction]] is the direction of increasing $x$. (a) Estimate the average velocity over each of the three intervals using a finite-difference approximation. (b) Is the motion at constant velocity? (c) What is the [[Speed]] over the last interval, and how does it differ from the velocity?

> [!NOTE]- Answer
> **(a) Finite-difference velocities.**
> $$v_{0\to1} = \frac{0.004 - 0.000}{0.010} = 0.40\ \text{m/s}$$
> $$v_{1\to2} = \frac{0.009 - 0.004}{0.010} = 0.50\ \text{m/s}$$
> $$v_{2\to3} = \frac{0.015 - 0.009}{0.010} = 0.60\ \text{m/s}$$
> Each of these is an [[Average Velocity]] over its 10 ms window.
>
> **(b) Constant velocity?**
> No. The estimated velocity is increasing by about $0.10\ \text{m/s}$ per interval, so the axis is accelerating in the positive direction at roughly $\bar{a} \approx 0.10/0.010 = 10\ \text{m/s}^2$ — see [[Acceleration]].
>
> **(c) Speed over the last interval.**
> The [[Speed]] is the magnitude $|v_{2\to3}| = 0.60\ \text{m/s}$. The velocity is $+0.60\ \text{m/s}$ — same numeric value, but the velocity additionally tells us the motion is in the [[Positive Direction]]. A reading of $-0.60\ \text{m/s}$ would give the same speed but the opposite direction.
