---
tags: [dynamics, pre-release]
---
#dynamics #pre-release

## Definition
> [!definition]
> The **instantaneous velocity** of a particle is the limit of its [[Average Velocity]] as the [[Time Interval]] shrinks to zero — equivalently, the time derivative of [[Position]] evaluated at a single instant. In one dimension it is the signed scalar $v(t) = dx/dt$; in higher dimensions it is the vector $\mathbf{v}(t) = d\mathbf{r}/dt$. Geometrically it is the slope of the [[Position-Time Graph]] at that instant.

Notes:
- Instantaneous velocity is the "at this instant" version of [[Velocity]]. Where [[Average Velocity]] answers *how fast did the point move on average over a window*, instantaneous velocity answers *how fast is it moving right now*. The two converge as the window shrinks: $v(t) = \lim_{\Delta t \to 0} \bar v$.
- The geometric picture is the **tangent line** to the [[Position-Time Graph]] at the chosen instant. The slope of that tangent — rise over run — is $v(t)$. The average-velocity slope is a **secant** between two points on the curve; the instantaneous-velocity slope is the limit of that secant as the two points slide together.
- If position is given symbolically as $x(t)$, getting velocity is just differentiation — see [[Velocity from Position]]. Polynomials, sines, and exponentials all yield clean closed-form $v(t)$. For an arbitrary $t$ you then *evaluate* the derivative at that instant.
- Instantaneous velocity is a **point property**, not a window property. Saying "the instantaneous velocity at $t = 2\ \text{s}$ is 4 m/s" is meaningful; saying "the instantaneous velocity between $t = 2\ \text{s}$ and $t = 2.1\ \text{s}$" is not — that is an average.
- Plotting $v(t)$ against time gives the [[Velocity-Time Graph]], which is the derivative trace of the [[Position-Time Graph]]. Differentiating once more in time gives [[Acceleration]].
- Real sensors never report a true instantaneous velocity. An encoder, a tachometer, or a finite-difference velocity estimator always uses a finite $\Delta t$ — and that estimate is an [[Average Velocity]] over the sample window, not the mathematical $dx/dt$. Calling it "the instantaneous velocity" is a useful shorthand only when $\Delta t$ is small compared to the motion's time scale.
- Like [[Velocity]] itself, instantaneous velocity is **frame-dependent** and **signed**. Reversing the [[Positive Direction]] flips the sign of $v(t)$ at every instant.

## Equations

> [!equation] Instantaneous velocity as a limit
> $$v(t) = \lim_{\Delta t \to 0} \frac{\Delta x}{\Delta t} = \frac{dx}{dt}$$
>
> - $v(t)$ — instantaneous velocity at time $t$ (m/s)
> - $\Delta x$ — [[Displacement]] over the interval (m)
> - $\Delta t$ — [[Time Interval]] over which the average is taken (s)
> - The limit collapses the window to a point and turns the secant slope into the tangent slope on the [[Position-Time Graph]]

> [!equation] Vector form
> $$\mathbf{v}(t) = \frac{d\mathbf{r}}{dt}$$
>
> - $\mathbf{v}(t)$ — instantaneous velocity vector (m/s)
> - $\mathbf{r}(t)$ — [[Position Vector]] in a chosen [[Reference Frame]]
> - $|\mathbf{v}(t)|$ — the [[Speed]] at that instant; the direction of $\mathbf{v}$ is tangent to the path

## Examples and Non-Examples

- **Worked example — polynomial position trace.** A linear stage moves so that its position is $x(t) = 0.05 + 0.20\,t + 0.30\,t^2$ metres, with $t$ in seconds. Differentiating term by term — see [[Velocity from Position]] — gives the instantaneous velocity as a function of time:
$$v(t) = \frac{dx}{dt} = 0.20 + 0.60\,t\ \text{m/s}$$
At the instant $t = 2.0\ \text{s}$,
$$v(2.0) = 0.20 + 0.60 \cdot 2.0 = 1.40\ \text{m/s}$$
That single number is the slope of the [[Position-Time Graph]] at $t = 2.0\ \text{s}$, and a point on the [[Velocity-Time Graph]] at the same instant. The positive sign says the stage is moving in the [[Positive Direction]]; the fact that $v(t)$ keeps growing tells us [[Acceleration]] is positive (here, a constant $0.60\ \text{m/s}^2$).

- **Average vs. instantaneous over the same motion.** Using the same $x(t)$, the [[Average Velocity]] between $t_1 = 1.0\ \text{s}$ and $t_2 = 3.0\ \text{s}$ is
$$\bar v = \frac{x(3.0) - x(1.0)}{3.0 - 1.0} = \frac{(0.05 + 0.60 + 2.70) - (0.05 + 0.20 + 0.30)}{2.0} = \frac{3.35 - 0.55}{2.0} = 1.40\ \text{m/s}$$
This is also $1.40\ \text{m/s}$, but only by coincidence of the chosen window — for this motion the average over $[1, 3]$ happens to equal the instantaneous value at $t = 2.0\ \text{s}$ (the midpoint). Slide the window and the average changes; the instantaneous value at $t = 2.0\ \text{s}$ does not.

- **Tangent-line interpretation.** On the [[Position-Time Graph]] of the same motion, draw the tangent at $t = 2.0\ \text{s}$. Its slope is $1.40\ \text{m/s}$ — the instantaneous velocity. Draw a secant between $t = 1.0\ \text{s}$ and $t = 3.0\ \text{s}$ on the same curve; its slope is the average velocity above. As you bring the secant endpoints in toward $t = 2.0\ \text{s}$, the secant rotates and approaches the tangent. That rotation *is* the limit in the definition.

- **Counter-example — a finite-difference estimate is not the instantaneous velocity.** A controller reads encoder positions $x(2.000\ \text{s}) = 0.45000\ \text{m}$ and $x(2.001\ \text{s}) = 0.45140\ \text{m}$ and computes
$$\bar v = \frac{0.45140 - 0.45000}{0.001} = 1.40\ \text{m/s}$$
Students often call this "the instantaneous velocity at $t = 2\ \text{s}$." It isn't — it is an [[Average Velocity]] over the 1 ms window $[2.000, 2.001]$. It is a *good approximation* of $v(2.000)$ when $\Delta t$ is small enough that the velocity barely changes over the window, but it is never literally $dx/dt$ until the limit is taken.

- **Counter-example — constant speed, non-constant velocity.** A delivery robot circles a charging dock at a steady $0.5\ \text{m/s}$. At every instant the [[Speed]] $|\mathbf{v}(t)|$ is $0.5\ \text{m/s}$, but the instantaneous velocity vector $\mathbf{v}(t)$ is *different at every instant* because its direction changes. Constant speed with a non-constant instantaneous velocity vector is exactly what produces centripetal [[Acceleration]].

## Resources

- **[CPPMechEngTutorials channel](https://www.youtube.com/@CPPMechEngTutorials)** — engineering-mechanics videos on rectilinear motion; search for "velocity as derivative of position" for the calculus-based treatment of $v = dx/dt$.
- **[Michel van Biezen channel](https://www.youtube.com/@MichelvanBiezen)** — short physics-style worked examples; channel-search "instantaneous velocity" for derivative-evaluation problems on polynomial $x(t)$.
- **[Wikipedia — Velocity (Instantaneous velocity)](https://en.wikipedia.org/wiki/Velocity#Instantaneous_velocity)** — concise reference for the limit definition, the derivative form, and the tangent-line interpretation.

## Practice

- A robot end-effector slides along a linear track with position $x(t) = 0.10 + 0.50\,t - 0.20\,t^2 + 0.05\,t^3$ metres, where $t$ is in seconds and the [[Positive Direction]] is the direction of increasing $x$. (a) Find the instantaneous velocity $v(t)$ as a function of time. (b) Evaluate $v$ at $t = 1.0\ \text{s}$ and at $t = 3.0\ \text{s}$. (c) At what instant is the end-effector momentarily at rest? (d) Compute the [[Average Velocity]] over the interval $[1.0, 3.0]\ \text{s}$ and compare it to the instantaneous values from (b).

> [!NOTE]- Answer
> **(a) Differentiate term by term.**
> $$v(t) = \frac{dx}{dt} = 0.50 - 0.40\,t + 0.15\,t^2\ \text{m/s}$$
>
> **(b) Evaluate at the two instants.**
> $$v(1.0) = 0.50 - 0.40(1.0) + 0.15(1.0)^2 = 0.50 - 0.40 + 0.15 = 0.25\ \text{m/s}$$
> $$v(3.0) = 0.50 - 0.40(3.0) + 0.15(3.0)^2 = 0.50 - 1.20 + 1.35 = 0.65\ \text{m/s}$$
> Both are positive, so the end-effector is moving in the [[Positive Direction]] at each instant.
>
> **(c) Momentarily at rest.**
> Set $v(t) = 0$:
> $$0.15\,t^2 - 0.40\,t + 0.50 = 0$$
> The discriminant is $(-0.40)^2 - 4(0.15)(0.50) = 0.16 - 0.30 = -0.14 < 0$, so there are no real roots. The end-effector is **never** at rest on this track — $v(t) > 0$ for all $t$. (A negative or zero $v$ at some instant would have shown up as a real root.)
>
> **(d) Average velocity over $[1.0, 3.0]\ \text{s}$.**
> Endpoint positions:
> $$x(1.0) = 0.10 + 0.50 - 0.20 + 0.05 = 0.45\ \text{m}$$
> $$x(3.0) = 0.10 + 1.50 - 1.80 + 1.35 = 1.15\ \text{m}$$
> $$\bar v = \frac{x(3.0) - x(1.0)}{3.0 - 1.0} = \frac{1.15 - 0.45}{2.0} = 0.35\ \text{m/s}$$
> The average $0.35\ \text{m/s}$ lies between the two instantaneous values $0.25\ \text{m/s}$ and $0.65\ \text{m/s}$ from (b), which is exactly what the mean value theorem promises: somewhere on $[1.0, 3.0]\ \text{s}$ the instantaneous velocity equals the average. The average is a single number describing the whole window; the instantaneous values describe the motion at each chosen point on the [[Velocity-Time Graph]].
