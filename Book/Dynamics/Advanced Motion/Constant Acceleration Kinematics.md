---
tags: [dynamics, pre-release]
---
#dynamics #pre-release

## Definition
> [!definition]
> **Constant acceleration kinematics** describes the motion of a particle moving with a fixed acceleration. When acceleration $a$ does not change over time, three scalar equations — sometimes called the **kinematic equations** or SUVAT equations — relate displacement $\Delta x$, initial velocity $v_0$, final velocity $v$, acceleration $a$, and elapsed time $t$ without needing calculus.

Notes:
- These equations apply only when acceleration is **constant** throughout the interval. Variable acceleration requires integration — see [[Variable Acceleration]].
- "Constant" includes the special case $a = 0$ (uniform motion, no acceleration).
- In 2D and 3D, apply the equations independently along each axis. This is the basis for [[Projectile Motion]], where $a_x = 0$ and $a_y = -g$.
- The equations are the integrated forms of $v = \int a\,dt$ and $x = \int v\,dt$. If you want to see where they come from, expand the *Where this comes from* callout below.
- Free fall is the most common constant-acceleration scenario: $a = -g = -9.81\ \text{m/s}^2$ downward when air resistance is negligible.
- These equations connect directly to [[Newton's Laws of Motion]]: a constant net force on a particle with constant [[Weight and Mass|mass]] produces constant acceleration.

> [!note]- Where this comes from
> Starting from $a = \text{const}$, integrate once:
> $$v(t) = v_0 + at$$
> Integrate again:
> $$x(t) = x_0 + v_0 t + \tfrac{1}{2}a t^2$$
> Eliminating $t$ from the first two gives the velocity–displacement relation. All three kinematic equations follow from these two integrations.

## Equations

> [!equation] Velocity–time
> $$v = v_0 + at$$
>
> - $v$ — final velocity (m/s)
> - $v_0$ — initial velocity (m/s)
> - $a$ — constant acceleration (m/s²)
> - $t$ — elapsed time (s)

> [!equation] Displacement–time
> $$\Delta x = v_0 t + \tfrac{1}{2}a t^2$$
>
> - $\Delta x = x - x_0$ — displacement (m)
> - Useful when you know time but not final velocity

> [!equation] Velocity–displacement
> $$v^2 = v_0^2 + 2a\,\Delta x$$
>
> - Time-independent relation
> - Useful when you know displacement but not time

## Examples and Non-Examples

- **Free fall from rest.** A ball is dropped from a height of $h = 20\ \text{m}$. How fast is it moving just before impact? Taking downward as positive with $a = 9.81\ \text{m/s}^2$, $v_0 = 0$:
$$v = \sqrt{v_0^2 + 2a\Delta x} = \sqrt{0 + 2(9.81)(20)} \approx 19.8\ \text{m/s}$$

- **Braking car.** A car traveling at $v_0 = 25\ \text{m/s}$ decelerates at $a = -6\ \text{m/s}^2$. How long to stop, and how far does it travel?
$$t = \frac{v - v_0}{a} = \frac{0 - 25}{-6} \approx 4.17\ \text{s}$$
$$\Delta x = v_0 t + \tfrac{1}{2}a t^2 = 25(4.17) + \tfrac{1}{2}(-6)(4.17)^2 \approx 52.1\ \text{m}$$

- **Counter-example — spring system.** A mass on a spring has acceleration $a = -(k/m)x$ that depends on position — it is not constant. Kinematic equations do not apply; the motion is governed by a second-order ODE (simple harmonic motion).

- **Counter-example — robotic joint.** A servo-driven arm joint accelerates and then decelerates through a trapezoidal velocity profile. The acceleration changes at two points during the move, so you cannot apply a single set of kinematic equations to the whole motion — split it into constant-acceleration segments.

## Resources

![](https://www.youtube.com/watch?v=ZM8ECpBuQYE)

![](https://www.youtube.com/watch?v=3lTpSqVcmcg)

**[Wikipedia — Equations of motion](https://en.wikipedia.org/wiki/Equations_of_motion)**

## Practice

- A robot arm end-effector starts from rest and accelerates linearly at $a = 2.5\ \text{m/s}^2$ for $t = 1.8\ \text{s}$. (a) What is its final speed? (b) How far did it travel?

> [!NOTE]- Answer
> **(a) Final speed.**
> $$v = v_0 + at = 0 + (2.5)(1.8) = 4.5\ \text{m/s}$$
>
> **(b) Distance traveled.**
> $$\Delta x = v_0 t + \tfrac{1}{2}a t^2 = 0 + \tfrac{1}{2}(2.5)(1.8)^2 = 4.05\ \text{m}$$
