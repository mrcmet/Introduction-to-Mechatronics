---
tags: [dynamics, pre-release]
---
#dynamics #pre-release

## Definition
> [!definition]
> A **final condition** is the value of a state variable — typically [[Position]] and [[Velocity]] — at the *end* of a [[Time Interval]]. We write it as $x_f = x(t_f)$ and $v_f = v(t_f)$. It is the counterpart to the [[Initial Condition]]: where an initial condition seeds an integration of the equations of motion, a final condition reports (or commands) the resulting state at $t = t_f$.

Notes:
- A final condition is the **end state of an integration problem**. Given an [[Initial Condition]] and the dynamics on $[t_i, t_f]$, the final condition is what you compute; given a desired final condition, the dynamics tell you what initial condition or input you need.
- In **motion planning**, the final condition is a *commanded* state — "move the gantry to $x_f = 0.350\ \text{m}$ and stop." In **simulation**, the final condition is a *computed* state — whatever the integrator produces at $t_f$. Same symbol, different role.
- Final conditions are what the [[Constant Acceleration Equations]] (SUVAT) are written to expose. Equations like $v_f = v_0 + a\,\Delta t$ and $x_f = x_0 + v_0\,\Delta t + \tfrac{1}{2}a\,\Delta t^2$ map the pair $(x_0, v_0)$ at $t_i$ to the pair $(x_f, v_f)$ at $t_f$.
- Common kinematic targets are special cases of a final condition. [[Stopping Distance]] is the final position with the side constraint $v_f = 0$; [[Stopping Time]] is the value of $\Delta t$ that drives $v_f$ to zero from a given $v_0$.
- A final condition is **not** an initial condition flipped around. The direction of integration matters: forward propagation goes from $(x_0, v_0)$ at $t_i$ to $(x_f, v_f)$ at $t_f$. You can run the math backwards algebraically, but the *meaning* of the two endpoints (cause vs. result, or command vs. start) is different.
- For a controller, the [[Final Condition]] of the current motion segment is usually the [[Initial Condition]] of the next one. A trajectory is a chain of these handoffs — design them so position and velocity match at each junction, or the actuator will see a step.

## Equations

> [!equation] Final position and velocity at $t = t_f$
> $$x_f = x(t = t_f), \qquad v_f = v(t = t_f)$$
>
> - $x_f$ — final position, the value of [[Position]] at the end of the interval (m)
> - $v_f$ — final velocity, the value of [[Velocity]] at the end of the interval (m/s)
> - $t_f$ — final instant on the chosen clock (s)

> [!equation] Final velocity under constant acceleration
> $$v_f = v_0 + a\,\Delta t$$
>
> - $v_0$ — initial velocity, an [[Initial Condition]] (m/s)
> - $a$ — constant acceleration on the interval (m/s²)
> - $\Delta t = t_f - t_i$ — [[Time Interval]] (s)

> [!equation] Final position under constant acceleration
> $$x_f = x_0 + v_0\,\Delta t + \tfrac{1}{2}\,a\,\Delta t^2$$
>
> - $x_0$ — initial position, an [[Initial Condition]] (m)
> - Other symbols as above

## Examples and Non-Examples

- **Worked example — predicting the final state from ICs and dynamics.** A linear slide starts a move with $x_0 = 0.020\ \text{m}$ and $v_0 = 0.10\ \text{m/s}$, accelerating at $a = 0.50\ \text{m/s}^2$ for $\Delta t = 0.40\ \text{s}$. The final conditions are
$$v_f = v_0 + a\,\Delta t = 0.10 + 0.50 \cdot 0.40 = 0.30\ \text{m/s}$$
$$x_f = x_0 + v_0\,\Delta t + \tfrac{1}{2} a\,\Delta t^2 = 0.020 + 0.10\cdot 0.40 + 0.5\cdot 0.50\cdot 0.40^2 = 0.100\ \text{m}$$
So at $t_f$ the slide is at 0.100 m moving at 0.30 m/s — the pair $(x_f, v_f)$ is the final condition.

- **Worked example — working backwards from a commanded final state.** A pick-and-place controller is told to reach $x_f = 0.350\ \text{m}$ with $v_f = 0$ (a clean stop on the target) starting from $x_0 = 0.050\ \text{m}$ and $v_0 = 0.40\ \text{m/s}$. With one constant deceleration phase, the SUVAT identity $v_f^2 = v_0^2 + 2a\,(x_f - x_0)$ gives
$$a = \frac{v_f^2 - v_0^2}{2(x_f - x_0)} = \frac{0 - 0.40^2}{2 \cdot 0.300} = -0.267\ \text{m/s}^2$$
and $\Delta t = (v_f - v_0)/a = ( -0.40)/(-0.267) \approx 1.50\ \text{s}$. The desired final condition is what *defines* the required acceleration and duration; the dynamics fit the command, not the other way around.

- **Trajectory handoff.** Segment 1 ends at $x_f^{(1)} = 0.220\ \text{m}$, $v_f^{(1)} = 0.15\ \text{m/s}$. Segment 2 begins at $x_0^{(2)} = 0.220\ \text{m}$, $v_0^{(2)} = 0.15\ \text{m/s}$. The final condition of one move becomes the initial condition of the next — match them, or the actuator command jumps.

- **Counter-example — a final condition is not an initial condition.** Swapping $(x_0, v_0)$ and $(x_f, v_f)$ in $v_f = v_0 + a\,\Delta t$ is not just a relabel. Integration runs forward in time: $(x_0, v_0)$ seeds the motion at $t_i$, and $(x_f, v_f)$ reports its outcome at $t_f$. You can algebraically solve for $v_0$ given $v_f$, but the *role* of the two endpoints — cause vs. result, or in mechatronics, start vs. commanded target — is different. Direction of integration matters.

- **Counter-example — a single number is not a final condition.** "The robot stops at $x = 0.5\ \text{m}$" is incomplete. A final condition is the full state at $t_f$: position *and* velocity (and any other state variable the model tracks). The stop in that sentence is implicit only because the reader assumes $v_f = 0$ — make the velocity component explicit when you write a final condition down.

## Resources

- **[Michel van Biezen channel](https://www.youtube.com/@MichelvanBiezen)** — short physics worked examples; nearly every kinematics problem there is structured as "given ICs, find final position/velocity at $t_f$."
- **[CPPMechEngTutorials channel](https://www.youtube.com/@CPPMechEngTutorials)** — engineering-dynamics rectilinear-motion problems where the final state is the unknown to solve for.
- **[Wikipedia — Equations of motion](https://en.wikipedia.org/wiki/Equations_of_motion)** — concise reference for the SUVAT relations that map $(x_0, v_0)$ at $t_i$ to $(x_f, v_f)$ at $t_f$.

## Practice

- A two-wheeled balancing robot is commanded to move forward from rest and reach a target docking position. Its initial condition is $x_0 = 0$, $v_0 = 0$ at $t_i = 0$. The controller applies a constant forward acceleration of $a = 0.80\ \text{m/s}^2$ for $\Delta t = 1.5\ \text{s}$, then a constant deceleration of $a = -0.80\ \text{m/s}^2$ until the robot stops. (a) What is the final condition $(x_f, v_f)$ at the end of the *acceleration* phase? (b) What is the final condition at the end of the *deceleration* phase (i.e., when the robot has come to rest)? (c) If the dock is at $x = 2.00\ \text{m}$, does the commanded final condition match the dock?

> [!NOTE]- Answer
> **(a) End of the acceleration phase.**
> Using the [[Constant Acceleration Equations]] with $v_0 = 0$, $a = 0.80\ \text{m/s}^2$, $\Delta t = 1.5\ \text{s}$:
> $$v_f^{(1)} = 0 + 0.80 \cdot 1.5 = 1.20\ \text{m/s}$$
> $$x_f^{(1)} = 0 + 0 + \tfrac{1}{2}\cdot 0.80 \cdot 1.5^2 = 0.90\ \text{m}$$
> So the final condition of segment 1 is $(x_f^{(1)}, v_f^{(1)}) = (0.90\ \text{m},\ 1.20\ \text{m/s})$.
>
> **(b) End of the deceleration phase.**
> Segment 2 takes the previous final condition as its initial condition: $x_0^{(2)} = 0.90\ \text{m}$, $v_0^{(2)} = 1.20\ \text{m/s}$, with $a = -0.80\ \text{m/s}^2$. The stop time satisfies $0 = v_0^{(2)} + a\,\Delta t^{(2)}$, giving
> $$\Delta t^{(2)} = -\frac{1.20}{-0.80} = 1.5\ \text{s}$$
> and the final position is
> $$x_f^{(2)} = 0.90 + 1.20 \cdot 1.5 + \tfrac{1}{2}\cdot (-0.80)\cdot 1.5^2 = 0.90 + 1.80 - 0.90 = 1.80\ \text{m}$$
> The final condition is $(x_f^{(2)}, v_f^{(2)}) = (1.80\ \text{m},\ 0)$. Note that this is also the [[Stopping Distance]] for segment 2 and the total $\Delta t^{(2)}$ is its [[Stopping Time]].
>
> **(c) Comparison with the dock.**
> The commanded final position is 1.80 m, but the dock is at 2.00 m — the robot stops 0.20 m short. The dynamics produced a valid final condition; it just doesn't match the *desired* one. To reach the dock with $v_f = 0$, the controller would need to lengthen the acceleration phase, reduce the deceleration magnitude, or add a constant-velocity coast in between. This is the everyday motion-planning loop: pick the inputs so the computed final condition equals the commanded final condition.
