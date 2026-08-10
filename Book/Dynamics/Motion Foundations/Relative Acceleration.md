---
tags: [dynamics, pre-release]
---
#dynamics #pre-release

## Definition
> [!definition]
> The **relative acceleration** of point $A$ with respect to point $B$ is the [[Acceleration Vector]] of $A$ as measured from a frame attached to $B$. It is written $\mathbf{a}_{A/B}$ and read "acceleration of $A$ as seen from $B$." When both $\mathbf{a}_A$ and $\mathbf{a}_B$ are measured in a common [[Inertial Reference Frame]] and the frame attached to $B$ translates without rotating, it is simply their vector difference $\mathbf{a}_{A/B} = \mathbf{a}_A - \mathbf{a}_B$.

Notes:
- The **subscript convention matches [[Relative Velocity]] and [[Relative Position]]**: $\mathbf{a}_{A/B}$ is "$A$ relative to $B$." The point after the slash is the observer; the point before is what is being observed. Reversing the order flips every sign — $\mathbf{a}_{A/B} = -\mathbf{a}_{B/A}$.
- **Derivative chain.** Relative acceleration is the time derivative of [[Relative Velocity]] in the same way that [[Acceleration]] is the time derivative of [[Velocity]]: $\mathbf{a}_{A/B} = d\mathbf{v}_{A/B}/dt$. Differentiating $\mathbf{v}_{A/B} = \mathbf{v}_A - \mathbf{v}_B$ once more in time gives $\mathbf{a}_{A/B} = \mathbf{a}_A - \mathbf{a}_B$ directly.
- **The simple formula assumes a non-rotating observer frame.** If the frame attached to $B$ rotates relative to the inertial frame, extra terms appear — centripetal $\boldsymbol{\omega} \times (\boldsymbol{\omega} \times \mathbf{r}_{A/B})$, Coriolis $2\boldsymbol{\omega} \times \mathbf{v}_{A/B}$, and tangential $\dot{\boldsymbol{\omega}} \times \mathbf{r}_{A/B}$ — and $\mathbf{a}_{A/B} \neq \mathbf{a}_A - \mathbf{a}_B$. Those cases live on [[Moving Reference Frame]].
- **Frame matters.** As with [[Relative Velocity]], the same physical motion produces different numbers in different frames. Always state the observer frame before quoting a relative acceleration, just as you state the [[Reference Frame]] before quoting an [[Acceleration]].
- **Constrained mechanisms.** When $A$ and $B$ are points on the same rigid body, or are linked by a rolling-contact or sliding-pin constraint, $\mathbf{a}_{A/B}$ is not free — it is fixed by geometry. That constraint is exactly what an [[Acceleration Constraint Equation]] encodes, and it is the workhorse for analyzing linkages, gear trains, and rolling wheels.
- **Forces follow accelerations, not velocities.** [[Newton's Second Law]] ties net force to acceleration in an inertial frame. A non-inertial (e.g. accelerating) observer frame sees *fictitious* forces precisely because $\mathbf{a}_{A/B}$ is not the inertial-frame acceleration of $A$ — it is the acceleration of $A$ as the accelerating observer sees it.
- Relative acceleration is an [[Acceleration Vector]], not a scalar. Its **direction** carries as much information as its magnitude.

## Equations

> [!equation] Relative acceleration in a common inertial frame
> $$\mathbf{a}_{A/B} = \mathbf{a}_A - \mathbf{a}_B$$
>
> - $\mathbf{a}_{A/B}$ — acceleration of $A$ as seen from $B$ ($\text{m/s}^2$)
> - $\mathbf{a}_A,\ \mathbf{a}_B$ — accelerations of $A$ and $B$, both measured in a common [[Inertial Reference Frame]] ($\text{m/s}^2$)
> - Valid when the frame attached to $B$ translates without rotating relative to the inertial frame; see [[Moving Reference Frame]] for the rotating-frame correction

> [!equation] Time derivative of relative velocity
> $$\mathbf{a}_{A/B} = \frac{d\mathbf{v}_{A/B}}{dt}$$
>
> - Differentiating $\mathbf{v}_{A/B} = \mathbf{v}_A - \mathbf{v}_B$ in time recovers $\mathbf{a}_{A/B} = \mathbf{a}_A - \mathbf{a}_B$
> - Same derivative chain as $\mathbf{r}_{A/B} \to \mathbf{v}_{A/B} \to \mathbf{a}_{A/B}$

> [!equation] Antisymmetry of relative acceleration
> $$\mathbf{a}_{A/B} = -\mathbf{a}_{B/A}$$
>
> - Swapping observer and observed flips the sign of every component
> - Magnitudes are equal: $|\mathbf{a}_{A/B}| = |\mathbf{a}_{B/A}|$

For constrained pairs of points (rolling wheels, four-bar linkages, rack-and-pinion drives), the relative acceleration is not arbitrary — it is fixed by the geometry of the linkage. See [[Acceleration Constraint Equation]] for the systematic way to write those constraints down.

## Examples and Non-Examples

- **Worked example — part on an accelerating conveyor.** A conveyor belt is spinning up in the $+x$ direction of the workcell with $\mathbf{a}_{\text{belt}} = (0.80,\ 0)\ \text{m/s}^2$. A part sitting on the belt is slipping, so it accelerates more slowly in the workcell frame: $\mathbf{a}_{\text{part}} = (0.50,\ 0)\ \text{m/s}^2$. Its acceleration *relative to the belt* is
$$\mathbf{a}_{\text{part}/\text{belt}} = \mathbf{a}_{\text{part}} - \mathbf{a}_{\text{belt}} = (0.50 - 0.80,\ 0) = (-0.30,\ 0)\ \text{m/s}^2.$$
From the belt's point of view, the part is accelerating *backward* at $0.30\ \text{m/s}^2$ — exactly the slip an [[Acceleration Constraint Equation]] would have killed if the no-slip condition were enforced. By antisymmetry, $\mathbf{a}_{\text{belt}/\text{part}} = (+0.30,\ 0)\ \text{m/s}^2$.

- **Worked example — AGV decelerating toward a fixed obstacle.** An autonomous ground vehicle decelerates uniformly at $\mathbf{a}_{\text{AGV}} = (-1.5,\ 0)\ \text{m/s}^2$ in the workcell (ground) frame as it approaches a stationary pallet at $\mathbf{a}_{\text{pallet}} = (0,\ 0)\ \text{m/s}^2$. The AGV's acceleration relative to the pallet is
$$\mathbf{a}_{\text{AGV}/\text{pallet}} = (-1.5 - 0,\ 0) = (-1.5,\ 0)\ \text{m/s}^2,$$
the same as the ground-frame value — because anything stationary in the ground frame *is* the ground frame for the purpose of this subtraction. A bumper-mounted accelerometer on the pallet would read this directly.

- **Two AGVs maneuvering.** Two AGVs cross an aisle. In the workcell frame, $\mathbf{a}_A = (0.40,\ 0)\ \text{m/s}^2$ (still speeding up east) and $\mathbf{a}_B = (0,\ -0.60)\ \text{m/s}^2$ (braking from a northward run). The acceleration of $A$ as seen from $B$ is
$$\mathbf{a}_{A/B} = \mathbf{a}_A - \mathbf{a}_B = (0.40,\ 0.60)\ \text{m/s}^2.$$
An onboard predictor on $B$ uses both $\mathbf{v}_{A/B}$ and $\mathbf{a}_{A/B}$ to extrapolate where $A$ will be a fraction of a second from now.

- **Linkage example.** On a slider-crank, the slider's acceleration and the crank-pin's acceleration are not independent — the connecting rod ties them together. The pin-to-slider relative acceleration is exactly the quantity an [[Acceleration Constraint Equation]] solves for, and it is *not* free to take any value the analyst wants.

- **Counter-example — rotating observer frame.** A turntable spins at constant $\boldsymbol{\omega}$ about its centre, and a part sits at radius $r$ on the table. In the inertial (workcell) frame, the part has centripetal acceleration $\mathbf{a}_{\text{part}} = -\omega^2 r\,\hat{\mathbf{r}}$. In a frame *attached to the turntable*, the part is stationary — so its acceleration in that rotating frame is $\mathbf{0}$, not $\mathbf{a}_{\text{part}} - \mathbf{a}_{\text{centre}} = -\omega^2 r\,\hat{\mathbf{r}}$. The simple subtraction has failed because the observer frame is rotating. The missing pieces are the centripetal and Coriolis terms, which belong to [[Moving Reference Frame]] and are out of scope for this page.

- **Counter-example — relative acceleration is not a magnitude.** Writing "$a_{A/B} = 2\ \text{m/s}^2$" and stopping there throws away half the information. Like [[Acceleration]] itself, relative acceleration is an [[Acceleration Vector]] in a stated frame — a magnitude *and* a direction. Whether $A$ is closing on $B$, opening from $B$, or veering past $B$ depends on the direction of $\mathbf{a}_{A/B}$ relative to $\mathbf{v}_{A/B}$, not on the magnitude alone.

## Resources

- **[CPPMechEngTutorials channel](https://www.youtube.com/@CPPMechEngTutorials)** — engineering-mechanics treatment of relative motion; search the channel for "relative acceleration" and "relative motion of two particles" for worked examples in the same notation used here.
- **[Learn Engineering channel](https://www.youtube.com/@LearnEngineering)** — visual treatments of rotating frames, Coriolis, and centripetal acceleration; useful background before tackling [[Moving Reference Frame]].
- **[Wikipedia — Relative velocity](https://en.wikipedia.org/wiki/Relative_velocity)** — covers the (non-relativistic) frame transformation for both velocity and acceleration in a single article; the acceleration result is the direct time derivative of the velocity result quoted there.

## Practice

- A part slides on a conveyor belt. The belt accelerates in the $+x$ direction of the workcell at $\mathbf{a}_{\text{belt}} = (1.2,\ 0)\ \text{m/s}^2$. The part, due to friction limits, accelerates in the workcell frame at $\mathbf{a}_{\text{part}} = (0.90,\ 0)\ \text{m/s}^2$. At the same instant, the belt's velocity is $\mathbf{v}_{\text{belt}} = (0.40,\ 0)\ \text{m/s}$ and the part's velocity is $\mathbf{v}_{\text{part}} = (0.25,\ 0)\ \text{m/s}$. (a) Find the part's acceleration relative to the belt, $\mathbf{a}_{\text{part}/\text{belt}}$. (b) Find the part's velocity relative to the belt, $\mathbf{v}_{\text{part}/\text{belt}}$. (c) From the belt's perspective, is the part slipping faster backward or catching up? (d) If the friction model required no slip — $\mathbf{a}_{\text{part}/\text{belt}} = \mathbf{0}$ — what would the part's ground-frame acceleration have to be?

> [!NOTE]- Answer
> **(a) Part relative to belt — acceleration.**
> $$\mathbf{a}_{\text{part}/\text{belt}} = \mathbf{a}_{\text{part}} - \mathbf{a}_{\text{belt}} = (0.90 - 1.2,\ 0) = (-0.30,\ 0)\ \text{m/s}^2.$$
> Negative $x$-component: in the belt's (translating, non-rotating) frame, the part is accelerating backward at $0.30\ \text{m/s}^2$.
>
> **(b) Part relative to belt — velocity.**
> $$\mathbf{v}_{\text{part}/\text{belt}} = \mathbf{v}_{\text{part}} - \mathbf{v}_{\text{belt}} = (0.25 - 0.40,\ 0) = (-0.15,\ 0)\ \text{m/s}.$$
> The part is already sliding backward across the belt at $0.15\ \text{m/s}$ — see [[Relative Velocity]].
>
> **(c) Slipping faster, or catching up?**
> $\mathbf{v}_{\text{part}/\text{belt}}$ and $\mathbf{a}_{\text{part}/\text{belt}}$ both point in $-x$ — same sign. From the rule on [[Negative Acceleration]], same-sign velocity and acceleration means *speeding up* in that direction. The part is slipping backward across the belt *faster* with time — the friction model isn't keeping up with the belt's spin-up.
>
> **(d) No-slip requirement.**
> No slip means $\mathbf{a}_{\text{part}/\text{belt}} = \mathbf{0}$, i.e. $\mathbf{a}_{\text{part}} = \mathbf{a}_{\text{belt}} = (1.2,\ 0)\ \text{m/s}^2$. This is the kind of geometric tie an [[Acceleration Constraint Equation]] enforces in a rolling-contact or linkage analysis: the relative acceleration between the contacting points is not free — it is pinned by the constraint.
