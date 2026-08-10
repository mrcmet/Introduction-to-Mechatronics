---
tags: [dynamics, pre-release]
---
#dynamics #pre-release

## Definition
> [!definition]
> The **instantaneous acceleration** of a particle is the limit of its [[Average Acceleration]] as the [[Time Interval]] shrinks to zero — equivalently, the time derivative of [[Velocity]] evaluated at a single instant. In one dimension it is the signed scalar $a(t) = dv/dt = d^2x/dt^2$, the second time derivative of [[Position]]. Geometrically it is the slope of the [[Velocity-Time Graph]] at that instant.

Notes:
- Instantaneous acceleration is the "at this instant" version of [[Acceleration]]. Where [[Average Acceleration]] answers *how much did the velocity change per unit time over a window*, instantaneous acceleration answers *how fast is the velocity changing right now*. The two converge as the window shrinks: $a(t) = \lim_{\Delta t \to 0} \bar a$.
- The geometric picture is the **tangent line** to the [[Velocity-Time Graph]] at the chosen instant. The slope of that tangent — rise over run — is $a(t)$. The average-acceleration slope is a **secant** between two points on the $v(t)$ curve; the instantaneous-acceleration slope is the limit of that secant as the two points slide together. Plotting $a(t)$ against time gives the [[Acceleration-Time Graph]].
- Equivalently, instantaneous acceleration is the **second derivative of [[Position]]**: $a(t) = d^2x/dt^2$. Position, velocity, and acceleration form the kinematic derivative chain — differentiate once to go from $x(t)$ to $v(t)$, again to get $a(t)$, and one more time to get [[Jerk]].
- Instantaneous acceleration is a **point property**, not a window property. Saying "the instantaneous acceleration at $t = 1\ \text{s}$ is $9\ \text{m/s}^2$" is meaningful; "the instantaneous acceleration between $t = 1\ \text{s}$ and $t = 1.1\ \text{s}$" is not — that quantity is an average.
- Like [[Acceleration]] itself, the value is **signed** and frame-dependent. Reversing the [[Positive Direction]] flips the sign of $a(t)$ at every instant. The sign by itself does not say "speeding up" or "slowing down"; that depends on how the sign of $a$ compares to the sign of $v$ at the same instant.
- Real hardware never measures a true instantaneous $a$. An IMU averages over its sampling window; a finite-difference acceleration estimator computes $(v_f - v_i)/\Delta t$, which is mathematically an [[Average Acceleration]] over the sample. Calling it "the instantaneous acceleration" is shorthand that works only when $\Delta t$ is small compared to the motion's time scale.

## Equations

> [!equation] Instantaneous acceleration as a limit and derivative
> $$a(t) = \lim_{\Delta t \to 0} \frac{\Delta v}{\Delta t} = \frac{dv}{dt} = \frac{d^2 x}{dt^2}$$
>
> - $a(t)$ — instantaneous acceleration at time $t$ ($\text{m/s}^2$)
> - $v(t)$ — [[Velocity]] along the chosen axis (m/s)
> - $x(t)$ — [[Position]] as a function of time (m)
> - $\Delta v$ — change in velocity over the interval (m/s)
> - $\Delta t$ — [[Time Interval]] over which the average is taken (s)
> - The limit collapses the window to a point and turns the secant slope into the tangent slope on the [[Velocity-Time Graph]]

## Examples and Non-Examples

- **Worked example — differentiate $v(t)$ and evaluate.** A linear stage moves with velocity $v(t) = 2t^2 + 5t$ m/s, with $t$ in seconds and the [[Positive Direction]] taken as the direction of motion. Differentiating term by term gives the instantaneous acceleration as a function of time:
$$a(t) = \frac{dv}{dt} = 4t + 5\ \text{m/s}^2$$
At the instant $t = 1\ \text{s}$,
$$a(1) = 4(1) + 5 = 9\ \text{m/s}^2$$
That single number is the slope of the [[Velocity-Time Graph]] at $t = 1\ \text{s}$, and a point on the [[Acceleration-Time Graph]] at the same instant. The positive sign says the acceleration points in the [[Positive Direction]]; because $v(1) = 2 + 5 = 7\ \text{m/s}$ is also positive, the stage is *speeding up* at that instant.

- **Worked example — from position to acceleration.** Suppose the position trace is $x(t) = 0.10 + 0.50t + 0.20t^2 + 0.10t^3$ metres. Differentiating once gives $v(t) = 0.50 + 0.40t + 0.30t^2$ m/s; differentiating again gives
$$a(t) = \frac{d^2 x}{dt^2} = 0.40 + 0.60t\ \text{m/s}^2$$
At $t = 2.0\ \text{s}$, $a(2.0) = 0.40 + 1.20 = 1.60\ \text{m/s}^2$. The same number you would get by differentiating $v(t)$ once and evaluating — the two paths through the derivative chain agree.

- **Tangent-line interpretation.** On the [[Velocity-Time Graph]] of $v(t) = 2t^2 + 5t$, draw the tangent at $t = 1\ \text{s}$. Its slope is $9\ \text{m/s}^2$ — the instantaneous acceleration. Draw a secant between $t = 0.5\ \text{s}$ and $t = 1.5\ \text{s}$ on the same curve; its slope is an [[Average Acceleration]] over that window. As the secant endpoints close in toward $t = 1\ \text{s}$, the secant rotates and approaches the tangent. That rotation *is* the limit in the definition.

- **Counter-example — average over a finite $\Delta t$ is not the instantaneous value.** Using the same $v(t) = 2t^2 + 5t$, take the average between $t_i = 0.5\ \text{s}$ and $t_f = 1.5\ \text{s}$:
$$\bar a = \frac{v(1.5) - v(0.5)}{1.5 - 0.5} = \frac{(2(2.25) + 7.5) - (2(0.25) + 2.5)}{1.0} = \frac{12.0 - 3.0}{1.0} = 9.0\ \text{m/s}^2$$
The average over $[0.5, 1.5]\ \text{s}$ happens to equal $a(1.0) = 9.0\ \text{m/s}^2$ here only because the underlying $a(t) = 4t + 5$ is linear in $t$ (so its mean over a symmetric window equals its midpoint value). Slide the window off-centre or pick a non-linear $a(t)$ and the average will no longer equal the instantaneous value at any obvious instant — that is the whole reason we take the limit.

- **Counter-example — constant velocity, zero instantaneous acceleration.** A delivery cart cruises at a steady $v = 0.40\ \text{m/s}$. The velocity curve is flat, so its slope is zero everywhere: $a(t) = dv/dt = 0$ at every instant. The cart is *moving* the whole time, but its instantaneous acceleration is identically zero — motion at non-zero $v$ does not by itself imply non-zero $a$.

## Resources

- **[Khan Academy — Physics channel](https://www.youtube.com/@khanacademy)** — search the channel for "instantaneous acceleration" for short calculus-based worked examples that mirror the differentiate-then-evaluate workflow on this page.
- **[The Organic Chemistry Tutor channel](https://www.youtube.com/@TheOrganicChemistryTutor)** — channel-search "instantaneous acceleration derivative" for additional worked problems where students differentiate a given $v(t)$ and evaluate at a chosen instant.
- **[Wikipedia — Acceleration (Instantaneous acceleration)](https://en.wikipedia.org/wiki/Acceleration#Instantaneous_acceleration)** — concise reference for the limit definition, the derivative form, and the tangent-line interpretation on the velocity-time curve.

## Practice

- A servo-driven cart moves so that its velocity is $v(t) = 3t^2 - 2t + 1$ m/s, with $t$ in seconds and the [[Positive Direction]] taken as the direction of increasing position. (a) Find the instantaneous acceleration $a(t)$ as a function of time. (b) Evaluate $a$ at $t = 0\ \text{s}$ and at $t = 2\ \text{s}$. (c) At what instant is the instantaneous acceleration zero, and what is the velocity at that instant? (d) Compute the [[Average Acceleration]] over the interval $[0, 2]\ \text{s}$ and compare it to the instantaneous values from (b).

> [!NOTE]- Answer
> **(a) Differentiate term by term.**
> $$a(t) = \frac{dv}{dt} = 6t - 2\ \text{m/s}^2$$
>
> **(b) Evaluate at the two instants.**
> $$a(0) = 6(0) - 2 = -2\ \text{m/s}^2$$
> $$a(2) = 6(2) - 2 = 10\ \text{m/s}^2$$
> At $t = 0$ the acceleration points in the $-x$ direction; at $t = 2\ \text{s}$ it points in $+x$. Whether the cart is speeding up or slowing down at each instant depends on the sign of $v$ at the same instant (see [[Acceleration]] notes on sign vs. deceleration).
>
> **(c) Where acceleration vanishes.**
> Set $a(t) = 0$:
> $$6t - 2 = 0 \implies t = \tfrac{1}{3}\ \text{s} \approx 0.333\ \text{s}$$
> The velocity at that instant is
> $$v(\tfrac{1}{3}) = 3(\tfrac{1}{9}) - 2(\tfrac{1}{3}) + 1 = \tfrac{1}{3} - \tfrac{2}{3} + 1 = \tfrac{2}{3}\ \text{m/s} \approx 0.667\ \text{m/s}$$
> The cart is still moving — only the *rate of change* of its velocity is momentarily zero. On the [[Velocity-Time Graph]] this is the instant where the tangent line is horizontal (the bottom of the parabola).
>
> **(d) Average acceleration over $[0, 2]\ \text{s}$.**
> Endpoint velocities:
> $$v(0) = 3(0) - 2(0) + 1 = 1\ \text{m/s}$$
> $$v(2) = 3(4) - 2(2) + 1 = 9\ \text{m/s}$$
> $$\bar a = \frac{v(2) - v(0)}{2 - 0} = \frac{9 - 1}{2} = 4\ \text{m/s}^2$$
> The average $4\ \text{m/s}^2$ lies between the two instantaneous values $-2\ \text{m/s}^2$ and $10\ \text{m/s}^2$ from (b), which is exactly what the mean value theorem promises: somewhere on $[0, 2]\ \text{s}$ the instantaneous acceleration equals the average. Here that happens at $t = 1\ \text{s}$, where $a(1) = 6 - 2 = 4\ \text{m/s}^2$. The average is a single number for the whole window; the instantaneous values describe the motion at each chosen point on the [[Acceleration-Time Graph]].
