---
tags: [dynamics, pre-release]
---
#dynamics #pre-release

## Definition
> [!definition]
> **Acceleration** is the time rate of change of [[Velocity]]. In one dimension it is the signed scalar $a = dv/dt = d^2x/dt^2$, where the sign carries direction along the chosen [[Positive Direction]]. For motion in a plane or in space, acceleration generalizes to the [[Acceleration Vector]] $\mathbf{a}(t) = d\mathbf{v}/dt$, and it is the kinematic quantity that [[Newton's Second Law]] ties directly to applied force.

Notes:
- Acceleration is a **vector quantity**: it has both magnitude and direction. The 1D scalar form $a$ packs direction into a sign tied to the chosen [[Positive Direction]]. For 2D and 3D treatments, see [[Acceleration Vector]].
- Acceleration is the **time derivative of [[Velocity]]** and the **second time derivative of [[Position]]**, so $a = dv/dt = d^2x/dt^2$. Position, velocity, and acceleration form the kinematic derivative chain that every equation in this section rests on.
- Units are **metres per second squared** ($\text{m/s}^2$): a change in velocity (m/s) divided by a time (s). The canonical reference value is gravitational acceleration near Earth's surface, $g \approx 9.81\ \text{m/s}^2$.
- The sign of $a$ alone does **not** tell you "speeding up" or "slowing down." See [[Negative Acceleration]]: a particle is *decelerating* only when $a$ and $v$ have opposite signs. A car moving in $+x$ with $a < 0$ slows; a car moving in $-x$ with $a < 0$ speeds up.
- [[Newton's Second Law]] links acceleration to net force, $\mathbf{F} = m\mathbf{a}$. Force does not cause velocity directly — it causes acceleration, and velocity follows by integration. This is the bridge from kinematics into dynamics proper.
- Like [[Velocity]], acceleration comes in two specializations on their own pages. [[Average Acceleration]] is the velocity-change-over-time ratio between two instants; [[Instantaneous Acceleration]] is the limit of that ratio as the interval shrinks to zero. Special case [[Constant Acceleration]] gives the familiar SUVAT equations.
- The time derivative of acceleration is [[Jerk]], $j = da/dt$. Jerk matters when you care about smoothness — motion profiles, ride comfort, and mechanical wear on a servo-driven axis.

## Equations

> [!equation] Scalar acceleration in 1D
> $$a(t) = \frac{dv}{dt} = \frac{d^2 x}{dt^2}$$
>
> - $a(t)$ — acceleration along the chosen axis ($\text{m/s}^2$)
> - $v(t)$ — [[Velocity]] along the chosen axis (m/s)
> - $x(t)$ — [[Position]] as a function of time (m)
> - Sign is set by the chosen [[Positive Direction]]

> [!equation] Vector acceleration
> $$\mathbf{a}(t) = \frac{d\mathbf{v}}{dt} = \frac{d^2\mathbf{r}}{dt^2}$$
>
> - $\mathbf{a}(t)$ — acceleration vector ($\text{m/s}^2$)
> - $\mathbf{v}(t)$ — [[Velocity Vector]] in a chosen [[Reference Frame]]
> - $\mathbf{r}(t)$ — [[Position Vector]]; see [[Acceleration Vector]] for components

## Examples and Non-Examples

- **Worked example — motor spin-up driving a linear load.** A geared motor accelerates a cart from rest to $v_f = 1.20\ \text{m/s}$ in $\Delta t = 0.40\ \text{s}$, with the [[Positive Direction]] taken as the direction of motion. Treating the spin-up as roughly [[Constant Acceleration]],
$$\bar{a} = \frac{\Delta v}{\Delta t} = \frac{1.20 - 0}{0.40} = 3.0\ \text{m/s}^2$$
This is an [[Average Acceleration]] over the 0.40 s window. If the cart has mass $m = 2.0\ \text{kg}$, [[Newton's Second Law]] gives the net force the drivetrain must deliver: $F = m\bar{a} = 2.0 \times 3.0 = 6.0\ \text{N}$.

- **Worked example — car braking.** A car moving at $v_0 = 20\ \text{m/s}$ in the $+x$ direction brakes uniformly to rest in $\Delta t = 5.0\ \text{s}$.
$$a = \frac{0 - 20}{5.0} = -4.0\ \text{m/s}^2$$
The negative sign means acceleration points in $-x$ — opposite the motion. Because $a$ and $v$ have opposite signs, the car is *decelerating*. See [[Negative Acceleration]] for why "negative" and "decelerating" are not synonyms.

- **Free fall.** A part dropped from rest near Earth's surface accelerates downward at $g \approx 9.81\ \text{m/s}^2$. If the [[Positive Direction]] is taken as upward, the acceleration of the part is $a = -9.81\ \text{m/s}^2$ throughout the fall — a textbook case of [[Constant Acceleration]].

- **Counter-example — constant velocity is zero acceleration.** A linear slide moves at a steady $v = 0.20\ \text{m/s}$. The velocity never changes, so $a = dv/dt = 0$ — even though the slide is moving the entire time. *Motion* alone is not acceleration; *change of velocity* is.

- **Counter-example — "negative acceleration" is not always deceleration.** A two-wheeled balancer is rolling backward at $v = -0.30\ \text{m/s}$ (i.e. in the $-x$ direction) and the controller commands $a = -1.0\ \text{m/s}^2$. Because $a$ and $v$ have the *same* sign, the robot is *speeding up* — it is moving backward faster, not slowing down. Sign of acceleration tells you direction along the axis; whether the body speeds up or slows down depends on how that sign compares to the sign of velocity.

## Resources

- **[CPPMechEngTutorials channel](https://www.youtube.com/@CPPMechEngTutorials)** — engineering-mechanics videos on rectilinear motion; search the channel for "acceleration" and "constant acceleration" for matched examples.
- **[Michel van Biezen channel](https://www.youtube.com/@MichelvanBiezen)** — short physics-style worked examples; search for "average acceleration" and "instantaneous acceleration" for the derivative-chain treatment.
- **[Learn Engineering channel](https://www.youtube.com/@LearnEngineering)** — visual explanations of dynamics concepts; useful for building intuition before working through the equations.
- **[Wikipedia — Acceleration](https://en.wikipedia.org/wiki/Acceleration)** — concise reference for the formal definition, units, and vector form.

## Practice

- A servo-driven linear stage starts at rest and reaches $v = 0.60\ \text{m/s}$ in $0.20\ \text{s}$, holds that velocity for $1.0\ \text{s}$, then decelerates uniformly back to rest in $0.30\ \text{s}$. The [[Positive Direction]] is the direction of initial motion. (a) Find the average acceleration during the spin-up phase. (b) Find the acceleration during the constant-velocity phase. (c) Find the average acceleration during the braking phase, and state whether the stage is decelerating or speeding up. (d) If the stage and its payload have a combined mass of $m = 4.0\ \text{kg}$, what net force does the drivetrain apply during the spin-up phase?

> [!NOTE]- Answer
> **(a) Spin-up phase.**
> $$\bar{a}_1 = \frac{0.60 - 0}{0.20} = 3.0\ \text{m/s}^2$$
> Positive sign — acceleration points in the [[Positive Direction]]. This is an [[Average Acceleration]] over the 0.20 s window.
>
> **(b) Constant-velocity phase.**
> Velocity does not change, so $a = dv/dt = 0$. Motion at non-zero velocity but zero acceleration — the classic counter-example above.
>
> **(c) Braking phase.**
> $$\bar{a}_3 = \frac{0 - 0.60}{0.30} = -2.0\ \text{m/s}^2$$
> The acceleration is negative while the velocity is still positive (the stage is still moving in $+x$ as it slows). Because $a$ and $v$ have *opposite* signs, the stage is decelerating — see [[Negative Acceleration]] for the general rule.
>
> **(d) Force during spin-up.**
> By [[Newton's Second Law]],
> $$F = m\bar{a}_1 = 4.0 \times 3.0 = 12\ \text{N}$$
> directed in the [[Positive Direction]].
