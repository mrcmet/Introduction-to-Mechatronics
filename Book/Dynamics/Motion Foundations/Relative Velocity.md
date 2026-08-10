---
tags: [dynamics, pre-release]
---
#dynamics #pre-release

## Definition
> [!definition]
> The **relative velocity** of point $A$ with respect to point $B$ is the [[Velocity Vector]] of $A$ as measured from a frame attached to $B$. It is written $\mathbf{v}_{A/B}$ and read "velocity of $A$ as seen from $B$." When both $\mathbf{v}_A$ and $\mathbf{v}_B$ are measured in a common [[Inertial Reference Frame]], it is simply their vector difference $\mathbf{v}_{A/B} = \mathbf{v}_A - \mathbf{v}_B$.

Notes:
- The **subscript notation is "numerator over denominator"**: $\mathbf{v}_{A/B}$ is "$A$ relative to $B$." The point after the slash is the observer; the point before is the thing being observed. Mixing the order is the most common error on this page.
- **Antisymmetry.** Reversing the roles flips the sign: $\mathbf{v}_{A/B} = -\mathbf{v}_{B/A}$. If a part moves forward at $0.5\ \text{m/s}$ relative to a belt, the belt moves backward at $0.5\ \text{m/s}$ relative to the part.
- The world or "**ground frame**" is just a convenient choice of [[Reference Frame]] — usually one fixed to the lab or workcell floor. Quantities like $\mathbf{v}_A$ without a subscript almost always mean "$\mathbf{v}_A$ in the ground frame," shorthand for $\mathbf{v}_{A/\text{ground}}$.
- Relative velocity is the velocity-level companion of [[Relative Position]]: differentiating $\mathbf{r}_{A/B} = \mathbf{r}_A - \mathbf{r}_B$ in time gives exactly $\mathbf{v}_{A/B} = \mathbf{v}_A - \mathbf{v}_B$. Differentiating once more gives [[Relative Acceleration]].
- The simple subtraction $\mathbf{v}_A - \mathbf{v}_B$ assumes the observer frame on $B$ is **translating only** — not rotating — relative to a common inertial frame. When the observer frame rotates, a $\boldsymbol{\omega} \times \mathbf{r}_{A/B}$ term appears; that case lives on [[Moving Reference Frame]].
- **Frame matters, and the answer changes with it.** The same physical motion produces different numbers in different frames. Always state the observer frame before quoting a relative velocity, just as you state the [[Reference Frame]] before quoting a [[Velocity]].
- Relative velocity is a [[Velocity Vector]], not a scalar. Its **direction** carries as much information as its magnitude — see the counter-example below.

## Equations

> [!equation] Relative velocity in a common inertial frame
> $$\mathbf{v}_{A/B} = \mathbf{v}_A - \mathbf{v}_B$$
>
> - $\mathbf{v}_{A/B}$ — velocity of $A$ as seen from $B$ (m/s)
> - $\mathbf{v}_A,\ \mathbf{v}_B$ — velocities of $A$ and $B$, both measured in a common [[Inertial Reference Frame]] (m/s)
> - Valid when the frame attached to $B$ translates without rotating relative to the inertial frame; see [[Moving Reference Frame]] otherwise

> [!equation] Antisymmetry of relative velocity
> $$\mathbf{v}_{A/B} = -\mathbf{v}_{B/A}$$
>
> - Swapping the observer and the observed flips the sign of every component
> - Magnitudes are equal: $|\mathbf{v}_{A/B}| = |\mathbf{v}_{B/A}|$

## Examples and Non-Examples

- **Worked example — part on a conveyor.** A conveyor belt runs in the $+x$ direction of the workcell at $\mathbf{v}_{\text{belt}} = (0.40,\ 0)\ \text{m/s}$. A robot places a part on the belt and, an instant later, the part moves in the workcell frame at $\mathbf{v}_{\text{part}} = (0.30,\ 0)\ \text{m/s}$ — the part hasn't yet matched belt speed. Its velocity *relative to the belt* is
$$\mathbf{v}_{\text{part}/\text{belt}} = \mathbf{v}_{\text{part}} - \mathbf{v}_{\text{belt}} = (0.30 - 0.40,\ 0) = (-0.10,\ 0)\ \text{m/s}.$$
From the belt's point of view, the part is sliding *backward* at $0.10\ \text{m/s}$ — exactly the slip a friction model needs. By antisymmetry, $\mathbf{v}_{\text{belt}/\text{part}} = (+0.10,\ 0)\ \text{m/s}$.

- **Two AGVs in a workcell.** Two autonomous ground vehicles cross an aisle. In the workcell (ground) frame, $\mathbf{v}_A = (1.0,\ 0)\ \text{m/s}$ moving east and $\mathbf{v}_B = (0,\ 0.6)\ \text{m/s}$ moving north. The velocity of $A$ as seen from $B$ is
$$\mathbf{v}_{A/B} = \mathbf{v}_A - \mathbf{v}_B = (1.0,\ -0.6)\ \text{m/s},$$
with magnitude $\sqrt{1.0^2 + 0.6^2} \approx 1.17\ \text{m/s}$ and direction $\arctan(-0.6/1.0) \approx -31^\circ$ from east. An onboard collision-avoidance system on $B$ uses exactly this vector to decide whether $A$ is closing or opening.

- **Encoder on the wheel vs. encoder on the ground.** A wheeled robot rolls forward at $1.2\ \text{m/s}$ in the ground frame. A floor-mounted optical encoder reads the robot's velocity directly: $\mathbf{v}_{\text{robot}/\text{ground}} = 1.2\ \text{m/s}$ forward. A wheel-mounted encoder, by contrast, measures the wheel's rotation relative to the robot chassis — its reading describes $\mathbf{v}_{\text{wheel surface}/\text{chassis}}$, *not* the robot's ground velocity. Confusing the two frames is a classic odometry bug: the numbers only agree under the no-slip assumption.

- **Counter-example — relative velocity is not a magnitude.** A student writes "$v_{A/B} = 0.5\ \text{m/s}$" and stops there. That number alone is a [[Speed]] — it cannot tell you whether $A$ is approaching $B$, receding from $B$, or moving sideways past $B$. Relative velocity is a [[Velocity Vector]]: a magnitude *and* a direction in a stated frame. The collision-avoidance decision in the AGV example above flips entirely on the sign of the $x$-component.

## Resources

- **[CPPMechEngTutorials channel](https://www.youtube.com/@CPPMechEngTutorials)** — engineering-mechanics treatment of relative motion; search the channel for "relative velocity" and "relative motion of two particles" for worked examples in the same notation used here.
- **[Michel van Biezen channel](https://www.youtube.com/@MichelvanBiezen)** — short physics-style worked examples on relative velocity in one and two dimensions; useful for building subscript-notation fluency before tackling the [[Moving Reference Frame]] case.
- **[Wikipedia — Relative velocity](https://en.wikipedia.org/wiki/Relative_velocity)** — concise reference for the formal definition, notation, and the (non-relativistic) frame transformation.

## Practice

- A part rides on a conveyor that moves in the $+x$ direction of the workcell at $\mathbf{v}_{\text{belt}} = (0.50,\ 0)\ \text{m/s}$. A robot end-effector grabs the part and accelerates it so that, at the moment of pickup, the end-effector moves in the workcell frame at $\mathbf{v}_{\text{ee}} = (0.50,\ 0.20)\ \text{m/s}$ — matching belt speed in $x$ but also rising in $y$. (a) What is the end-effector's velocity relative to the belt, $\mathbf{v}_{\text{ee}/\text{belt}}$? (b) What is the belt's velocity relative to the end-effector? (c) If a second part on the belt moves with the belt (no slip), what is the velocity of the end-effector relative to that part?

> [!NOTE]- Answer
> **(a) End-effector relative to belt.**
> $$\mathbf{v}_{\text{ee}/\text{belt}} = \mathbf{v}_{\text{ee}} - \mathbf{v}_{\text{belt}} = (0.50 - 0.50,\ 0.20 - 0) = (0,\ 0.20)\ \text{m/s}.$$
> From the belt's point of view, the end-effector is rising straight up at $0.20\ \text{m/s}$ — no horizontal slip. That is exactly the condition a pick-on-the-fly trajectory is designed to satisfy.
>
> **(b) Belt relative to end-effector.**
> By antisymmetry,
> $$\mathbf{v}_{\text{belt}/\text{ee}} = -\mathbf{v}_{\text{ee}/\text{belt}} = (0,\ -0.20)\ \text{m/s}.$$
> From the end-effector's frame, the belt is moving straight *down* at $0.20\ \text{m/s}$. The magnitudes match; the direction reverses.
>
> **(c) End-effector relative to a part moving with the belt.**
> A no-slip part has $\mathbf{v}_{\text{part}} = \mathbf{v}_{\text{belt}} = (0.50,\ 0)\ \text{m/s}$, so
> $$\mathbf{v}_{\text{ee}/\text{part}} = \mathbf{v}_{\text{ee}} - \mathbf{v}_{\text{part}} = (0,\ 0.20)\ \text{m/s},$$
> the same as (a). Any two points that share a velocity in the ground frame also share the same observer frame for the purpose of this subtraction.
