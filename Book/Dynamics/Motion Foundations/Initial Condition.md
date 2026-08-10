---
tags: [dynamics, pre-release]
---
#dynamics #pre-release

## Definition
> [!definition]
> An **initial condition** is the value of a state variable — typically [[Position]] or [[Velocity]] — at the start of a [[Time Interval]], conventionally written with a subscript zero: $x_0 = x(t=0)$ and $v_0 = v(t=0)$. Initial conditions are the inputs that turn an [[Equation of Motion]] from a family of possible trajectories into one unique solution.

Notes:
- An initial condition is a **snapshot of state at $t = 0$**, not a property of the system. The same robot started from different $x_0$ or $v_0$ will trace out different trajectories even though the dynamics — masses, forces, gains — are identical.
- A second-order [[Equation of Motion]] needs two ICs per degree of freedom. For a single particle on a line that means $x_0$ and $v_0$; for a [[Position Vector]] in 3D it means $\mathbf{r}_0$ and $\mathbf{v}_0$, six numbers in total.
- The choice $t = 0$ is a **convention**, not a physical fact. Resetting the clock just relabels which instant carries the subscript zero — the underlying trajectory is unchanged, exactly as for a [[Time Interval]].
- Initial conditions are how an IC plugs into kinematics: in the constant-acceleration form $x(t) = x_0 + v_0 t + \tfrac12 a t^2$, the two ICs sit out front and the dynamics ($a$) sit inside the integral. Change the ICs and the whole trajectory shifts.
- **Mechatronics flavor.** When a controller boots, it needs an *estimate* of $x_0$ and $v_0$ to start integrating. Homing a linear stage against a hard-stop is the act of setting $x_0 = 0$; an IMU sitting still on the bench at startup is establishing $v_0 = 0$ for its dead-reckoning loop.
- Bad ICs corrupt the entire integrated solution. An encoder that powers up at the wrong reference, or an IMU started while in motion, gives a $v_0$ that biases every later velocity and position estimate — this is one of the most common sources of drift in dead reckoning.
- An IC is not the same as a [[Final Condition]]: $x_0$ is where the motion *starts*, the final condition is where it *ends*. Solvers run forward from ICs; backward problems (boundary-value problems) are a different category of question.

## Equations

> [!equation] Initial position and initial velocity
> $$x_0 = x(t = 0), \qquad v_0 = v(t = 0)$$
>
> - $x_0$ — initial position along the chosen axis (m)
> - $v_0$ — initial velocity along the chosen axis (m/s)
> - Together, the two ICs needed to uniquely solve Newton's second law on one axis

> [!equation] ICs in the SUVAT trajectory
> $$x(t) = x_0 + v_0\,t + \tfrac{1}{2} a\, t^2$$
>
> - $x_0$ — initial [[Position]] at $t = 0$ (m)
> - $v_0$ — initial [[Velocity]] at $t = 0$ (m/s)
> - $a$ — constant acceleration on this axis (m/s²)
> - The two ICs appear as the leading terms; the dynamics enter through $a$

## Examples and Non-Examples

- **Worked example — same dynamics, different ICs.** Two identical drop-test rigs release identical balls in the same gravitational field, so both obey $a = -g = -9.81\ \text{m/s}^2$ along the vertical axis. Rig A releases its ball from $x_0 = 2.00\ \text{m}$ with $v_0 = 0$. Rig B releases its ball from $x_0 = 2.00\ \text{m}$ with $v_0 = -3.00\ \text{m/s}$ (already moving downward when the timer starts). Plug both into the SUVAT trajectory:
$$x_A(t) = 2.00 + 0 \cdot t + \tfrac{1}{2}(-9.81)\,t^2$$
$$x_B(t) = 2.00 + (-3.00)\,t + \tfrac{1}{2}(-9.81)\,t^2$$
At $t = 0.40\ \text{s}$, ball A is at $x_A = 2.00 - 0.785 = 1.22\ \text{m}$ while ball B is at $x_B = 2.00 - 1.20 - 0.785 = 0.02\ \text{m}$. **Identical dynamics, different ICs, different trajectories** — that is the whole point of an initial condition.

- **Robot controller boot.** A two-wheeled balancer powers on while leaning at $\theta_0 = 0.03\ \text{rad}$ with $\dot\theta_0 = 0$. The control loop's state estimator needs both ICs to begin integrating the tilt dynamics; if it boots assuming $\theta_0 = 0$, every subsequent prediction inherits a 0.03 rad bias until a sensor correction beats it down.

- **Homing a linear stage.** A CNC gantry presses against a hard-stop and the firmware writes $x_0 \leftarrow 0$. This isn't an act of measurement — it's an act of *definition*. The homing routine is the moment the controller adopts its initial condition for [[Position]], and every motion command afterward is relative to that chosen origin.

- **Counter-example — a final condition is not an initial condition.** "The end-effector arrives at $x_f = 0.50\ \text{m}$ moving at $v_f = 0\ \text{m/s}$" describes a [[Final Condition]], not an initial one. Plugging $x_f$ in where $x_0$ belongs gives a trajectory that runs *forward* from the wrong starting point — usually a flipped or shifted curve. ICs are inputs to a forward integration; final conditions are outputs (or constraints in a different class of problem).

- **Counter-example — a parameter is not an initial condition.** The mass $m$, gravitational acceleration $g$, or spring stiffness $k$ are constants of the dynamics, not initial conditions. They sit inside the equation of motion regardless of when you start the clock. Only quantities that change in time — position and its derivatives — need an IC.

## Resources

- **[Steve Brunton channel](https://www.youtube.com/@Eigensteve)** — clear lectures on ODEs and state-space systems; search "initial conditions" or "state-space" for the integration-problem perspective.
- **[Michel van Biezen channel](https://www.youtube.com/@MichelvanBiezen)** — short physics-style problems that show $x_0$ and $v_0$ being substituted into the kinematic equations.
- **[Wikipedia — Initial condition](https://en.wikipedia.org/wiki/Initial_condition)** — concise reference for the role of ICs in ordinary differential equations.

## Practice

- A delivery drone is descending vertically when its altitude controller boots. At the boot instant ($t = 0$) the onboard barometer reports $x_0 = 12.0\ \text{m}$ above the launch pad and the IMU reports $v_0 = -1.5\ \text{m/s}$ (still moving downward). The controller commands a constant upward acceleration of $a = +2.0\ \text{m/s}^2$ for the next two seconds. (a) Write the SUVAT trajectory $x(t)$ for $0 \le t \le 2\ \text{s}$ using these ICs. (b) What is the drone's velocity at $t = 2\ \text{s}$? (c) What is its altitude at $t = 2\ \text{s}$? (d) If the IMU had been miscalibrated and reported $v_0 = 0$ instead, what altitude would the controller *predict* at $t = 2\ \text{s}$ — and by how much would it differ from the true altitude from (c)?

> [!NOTE]- Answer
> **(a) Trajectory with the correct ICs.**
> $$x(t) = x_0 + v_0\,t + \tfrac{1}{2} a\, t^2 = 12.0 + (-1.5)\,t + \tfrac{1}{2}(2.0)\,t^2$$
> $$x(t) = 12.0 - 1.5\,t + 1.0\,t^2 \quad\text{(metres, with $t$ in seconds)}$$
>
> **(b) Velocity at $t = 2\ \text{s}$.**
> $$v(2) = v_0 + a t = -1.5 + (2.0)(2) = +2.5\ \text{m/s}$$
> The drone has reversed direction and is now climbing.
>
> **(c) Altitude at $t = 2\ \text{s}$.**
> $$x(2) = 12.0 - 1.5(2) + 1.0(2)^2 = 12.0 - 3.0 + 4.0 = 13.0\ \text{m}$$
>
> **(d) Effect of a bad initial condition.**
> With the miscalibrated $v_0 = 0$, the controller's predicted trajectory is
> $$\tilde x(t) = 12.0 + 0\cdot t + 1.0\,t^2$$
> so $\tilde x(2) = 12.0 + 4.0 = 16.0\ \text{m}$. The predicted altitude differs from the true altitude by
> $$\tilde x(2) - x(2) = 16.0 - 13.0 = 3.0\ \text{m}$$
> A 1.5 m/s error in $v_0$ propagated into a 3 m altitude error over just two seconds — exactly the $v_0 \cdot t$ term that the bad IC zeroed out. This is the mechatronics reason ICs matter: bad inputs to an integrator become accumulating output errors.
