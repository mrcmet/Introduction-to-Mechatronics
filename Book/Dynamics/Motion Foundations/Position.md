---
tags: [dynamics, pre-release]
---
#dynamics #pre-release

## Definition
> [!definition]
> The **position** of a particle is its location along a chosen axis, measured as a signed scalar relative to an origin fixed in a [[Reference Frame]]. We typically write it as $x(t)$, where the sign carries direction along the [[Positive Direction]] of that axis and the magnitude is the distance from the origin. For motion in a plane or in space, position generalizes to a [[Position Vector]] $\mathbf{r}(t)$.

Notes:
- Position is **frame-dependent**. The same physical point has different numerical values of $x$ depending on where you place the origin and which way the axis points — choosing a sensible [[Reference Frame]] first is half the work.
- Position is a **signed** quantity. A reading of $x = -0.12\ \text{m}$ means the particle is 0.12 m on the negative side of the origin. Mixing this up with distance is the most common pitfall on this page.
- **Position vs. displacement.** Position $x$ locates a point relative to the origin; [[Displacement]] $\Delta x = x_2 - x_1$ measures the change between two instants. Shift the origin and every position changes, but displacement stays the same.
- **Position vs. distance traveled.** A robot that moves forward 1 m then back 1 m returns to $x = 0$, but its [[Distance Traveled]] is 2 m. Distance is a path integral; position is a snapshot.
- The value of $x$ at $t = 0$ is the [[Initial Condition]] $x_0$. Every kinematic equation that propagates motion in time needs $x_0$ plus a velocity history to give a unique answer.
- [[Velocity]] is the time derivative of position, $v = dx/dt$. If you know $x(t)$ as a function, every other kinematic quantity on this axis follows from differentiation.
- For motion that isn't confined to a single axis, switch to the vector form. See [[Position Vector]] for the 2D and 3D treatment and [[Coordinate Frames]] for choosing the right basis.

## Equations

> [!equation] Scalar position relative to an origin
> $$x(t) = x_0 + \int_0^t v(\tau)\,d\tau$$
>
> - $x(t)$ — position at time $t$ (m)
> - $x_0$ — initial position at $t = 0$, an [[Initial Condition]] (m)
> - $v(\tau)$ — velocity along the chosen axis (m/s)

> [!equation] Displacement between two instants
> $$\Delta x = x_2 - x_1$$
>
> - $x_1, x_2$ — positions at times $t_1$ and $t_2$ (m)
> - $\Delta x$ — signed [[Displacement]] (m); independent of origin

## Examples and Non-Examples

- **Linear gantry axis.** A CNC gantry rides on a rail with a home switch at one end. We set the origin at the home switch and define the [[Positive Direction]] as "toward the far end of the rail." The encoder reports a head position of $x = 0.842\ \text{m}$. That single signed number, combined with the frame definition, fully locates the cutting head on its axis.

- **Robot joint as a 1D position.** A prismatic joint on a SCARA arm extends along its own axis. With the retracted hard-stop as origin, a commanded position of $x = 0.15\ \text{m}$ means the joint is 15 cm out from the stop. Differentiating the encoder trace $x(t)$ in software gives the joint [[Velocity]] used in the control loop.

- **Sign convention matters.** A two-wheeled robot on a track has its origin set at the charging dock and positive $x$ pointing forward. A position $x = -0.30\ \text{m}$ means the robot is 30 cm *behind* the dock — not 30 cm of error magnitude. Reversing the sign convention flips the meaning of every controller term downstream.

- **Counter-example — distance traveled is not position.** A drill slide moves out 50 mm, then back 50 mm, returning to its starting point. Its [[Distance Traveled]] is 100 mm, but its position is $x = 0$ — the same as before the move. Position is the current location; distance traveled is an accumulator over the path.

- **Counter-example — a magnitude alone is not a position.** "The end-effector is 0.4 m from the base" describes a sphere of possible locations, not a unique point. Position requires both a frame and a signed coordinate (or, in higher dimensions, the full [[Position Vector]]).

## Resources

- ![](https://www.youtube.com/watch?v=Eq-aOO_Lqr0)
- **[CPPMechEngTutorials channel](https://www.youtube.com/@CPPMechEngTutorials)** — engineering-style dynamics videos; search for "rectilinear motion" for position-along-an-axis examples.
- **[Michel van Biezen channel](https://www.youtube.com/@MichelvanBiezen)** — short physics-style worked examples for position and motion along a line.
- **[Wikipedia — Position (geometry)](https://en.wikipedia.org/wiki/Position_(geometry))** — concise reference for the formal definition and notation.

## Practice

- A linear actuator on a pick-and-place machine is homed at the left hard-stop, which we take as $x_0 = 0$. Positive $x$ points to the right. The actuator moves to $x_1 = 0.220\ \text{m}$ to pick a part, then to $x_2 = 0.080\ \text{m}$ to place it. (a) What is the displacement from pick to place? (b) What is the total distance traveled from home to pick to place? (c) If we re-zero the encoder at the pick location (so the new $x_0 = 0$ corresponds to the old $x = 0.220$), what is the place position in the new frame?

> [!NOTE]- Answer
> **(a) Displacement from pick to place.**
> $$\Delta x = x_2 - x_1 = 0.080 - 0.220 = -0.140\ \text{m}$$
> Negative because the place point is to the left of the pick point.
>
> **(b) Distance traveled.**
> Home to pick: $|0.220 - 0| = 0.220\ \text{m}$. Pick to place: $|0.080 - 0.220| = 0.140\ \text{m}$. Total $= 0.360\ \text{m}$.
>
> **(c) Place position in the new frame.**
> Shifting the origin to the old pick location subtracts 0.220 m from every position: $x_{\text{place}}^{\text{new}} = 0.080 - 0.220 = -0.140\ \text{m}$. The place point is 0.140 m to the *left* of the new origin. The displacement from (a) is unchanged by the reframing — that is the point of [[Displacement]] being origin-independent.
