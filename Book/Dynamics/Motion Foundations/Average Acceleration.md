---
tags: [dynamics, pre-release]
---
#dynamics #pre-release

## Definition
> [!definition]
> **Average acceleration** is the change in [[Velocity]] of a point divided by the [[Time Interval]] over which that change occurred. In one dimension it is the signed scalar $\bar a = \Delta v / \Delta t$, and in two or three dimensions it is the vector $\bar{\mathbf{a}} = \Delta\mathbf{v}/\Delta t$. It is the interval-averaged version of [[Acceleration]] — distinct from [[Instantaneous Acceleration]], which is the limit of this ratio as $\Delta t \to 0$.

Notes:
- Average acceleration is a **vector quantity** (or a signed scalar in 1D). It carries direction, anchored to the chosen [[Positive Direction]], because the numerator $\Delta\mathbf{v}$ is itself a vector difference of two [[Velocity]] vectors.
- It depends on **only the endpoint velocities**. Any peaks, dips, or wiggles between $t_i$ and $t_f$ are invisible to $\bar{\mathbf{a}}$. Two motion profiles with the same starting and ending velocities over the same interval have the same average acceleration, even if one took a smooth ramp and the other slammed in and out of saturation.
- **Average tells you displacement; peak tells you force.** Average acceleration governs the net change in velocity (and, by integration, the change in position) over an interval. But [[Newton's Second Law]] applies at every instant — so the *peak* acceleration over the interval, not the average, sets the maximum force and torque the drivetrain has to deliver. When you size a motor, bearing, or coupling, peak matters.
- It is **not the same as [[Instantaneous Acceleration]]**. The instantaneous version is the derivative $d\mathbf{v}/dt$ at one instant. Average acceleration is a ratio over an interval; the two coincide only in the limit $\Delta t \to 0$ or when the acceleration is exactly constant over the interval — see [[Constant Acceleration]].
- The sign of $\bar a$ alone does not tell you "speeding up" or "slowing down." Compare it with the sign of velocity over the same interval — see [[Acceleration]] and [[Negative Acceleration]] for the general rule. A negative $\bar a$ on a body moving in the [[Positive Direction]] is deceleration; the same negative $\bar a$ on a body moving in $-x$ is speeding up in reverse.
- In a digital control loop, **every "acceleration" the firmware computes is really an average acceleration** over one or more sample periods: $\bar a \approx (v_{k+1} - v_k)/T_s$. As with [[Average Velocity]], we treat it as instantaneous when $T_s$ is short compared with the system's dynamics.
- Average acceleration shows up naturally in the impulse–momentum form of [[Newton's Second Law]]: $\bar{\mathbf{F}}\,\Delta t = m\,\Delta\mathbf{v}$, so $\bar{\mathbf{F}} = m\bar{\mathbf{a}}$. This is the right tool for short events — collisions, impacts, brake pulses — where you only know endpoint velocities and the interval.

## Equations

> [!equation] Average acceleration in 1D
> $$\bar a = \frac{\Delta v}{\Delta t} = \frac{v_f - v_i}{t_f - t_i}$$
>
> - $\bar a$ — average acceleration along the chosen axis ($\text{m/s}^2$)
> - $\Delta v$ — change in [[Velocity]] (m/s); sign set by the chosen [[Positive Direction]]
> - $\Delta t$ — [[Time Interval]] (s); always positive when measured forward in time

> [!equation] Average acceleration as a vector
> $$\bar{\mathbf{a}} = \frac{\Delta \mathbf{v}}{\Delta t} = \frac{\mathbf{v}_f - \mathbf{v}_i}{t_f - t_i}$$
>
> - $\bar{\mathbf{a}}$ — average acceleration vector ($\text{m/s}^2$)
> - $\Delta \mathbf{v}$ — change in velocity vector between the two instants (m/s)
> - Direction of $\bar{\mathbf{a}}$ matches the direction of $\Delta\mathbf{v}$, not the direction of motion

## Examples and Non-Examples

- **Worked example — motor spin-up from encoder data.** A brushed DC motor drives a cart, and the controller estimates wheel velocity from the encoder once per tick. At $t_i = 0.020\ \text{s}$ the velocity estimate is $v_i = 0.40\ \text{m/s}$; at $t_f = 0.080\ \text{s}$ it is $v_f = 1.30\ \text{m/s}$. The [[Time Interval]] is $\Delta t = 0.060\ \text{s}$, and the change in [[Velocity]] is $\Delta v = 0.90\ \text{m/s}$, so
$$\bar a = \frac{\Delta v}{\Delta t} = \frac{1.30 - 0.40}{0.060} = 15\ \text{m/s}^2$$
The positive sign says the average acceleration over that 60 ms window points in the [[Positive Direction]] — the cart is speeding up. If the cart's mass is $m = 0.50\ \text{kg}$, [[Newton's Second Law]] in interval form gives an *average* net force of $\bar F = m\bar a = 0.50 \times 15 = 7.5\ \text{N}$ over that window.

- **Worked example — brake pulse.** An AGV moving at $v_i = 2.0\ \text{m/s}$ in $+x$ engages a brake and is measured at $v_f = 0.4\ \text{m/s}$ exactly $\Delta t = 0.20\ \text{s}$ later. The average acceleration is
$$\bar a = \frac{0.4 - 2.0}{0.20} = -8.0\ \text{m/s}^2$$
The negative sign says $\bar{\mathbf{a}}$ points opposite to the motion; because $\bar a$ and $v$ have opposite signs over the interval, the vehicle is decelerating. This is an [[Average Acceleration]], not the actual brake-clamp acceleration at any one instant — the real waveform likely spiked harder than 8 m/s² when the friction pads first bit.

- **2D heading change.** A mobile robot is moving at $\mathbf{v}_i = [1.0, 0]^T\ \text{m/s}$ and 0.50 s later is moving at $\mathbf{v}_f = [0.8, 0.6]^T\ \text{m/s}$ — same speed, different direction. The average acceleration vector is
$$\bar{\mathbf{a}} = \frac{1}{0.50}\begin{bmatrix}0.8 - 1.0\\0.6 - 0\end{bmatrix} = \begin{bmatrix}-0.4\\1.2\end{bmatrix}\ \text{m/s}^2$$
The robot's *speed* didn't change, but its [[Velocity]] vector did — and average acceleration is nonzero whenever the velocity vector changes, including pure direction changes.

- **Counter-example — average hides the peak.** Compare two spin-up profiles that both take a stage from rest to $v_f = 1.0\ \text{m/s}$ in $\Delta t = 0.10\ \text{s}$. Profile A applies a smooth ramp with peak acceleration $\hat a = 10\ \text{m/s}^2$. Profile B slams to full torque, saturates briefly at $\hat a = 40\ \text{m/s}^2$, then coasts. Both have the same average acceleration,
$$\bar a = \frac{1.0 - 0}{0.10} = 10\ \text{m/s}^2$$
so they produce the same displacement and the same final velocity. But profile B's *instantaneous* peak force on the drivetrain is four times larger — see [[Instantaneous Acceleration]]. Average for kinematics; peak for sizing actuators, couplings, and gearboxes.

- **Counter-example — same speed, nonzero average acceleration.** A wheel rim point on a robot driving at constant 1.0 m/s through a tight turn has unchanging *speed* but a velocity vector that rotates with the chassis. Over any nonzero interval $\Delta\mathbf{v} \neq \mathbf{0}$, so $\bar{\mathbf{a}} \neq \mathbf{0}$. Constant speed is not the same as zero acceleration — only constant *velocity* is.

## Resources

- **[CPPMechEngTutorials channel](https://www.youtube.com/@CPPMechEngTutorials)** — engineering-dynamics worked examples on rectilinear motion; search within the channel for "average acceleration" for matched problems.
- **[Michel van Biezen channel](https://www.youtube.com/@MichelvanBiezen)** — short physics-style problems on average vs. instantaneous acceleration; useful for the derivative-chain framing.
- **[Wikipedia — Acceleration (Average acceleration)](https://en.wikipedia.org/wiki/Acceleration#Average_acceleration)** — concise reference for the formal definition and the contrast with instantaneous acceleration.

## Practice

- A two-wheeled balancing robot's inner velocity loop runs at 500 Hz. Across one tick the velocity estimate goes from $v_i = 0.32\ \text{m/s}$ to $v_f = 0.35\ \text{m/s}$, with [[Positive Direction]] taken as forward. (a) What is the average acceleration over that tick? (b) Twenty ticks later, the velocity has reached $v = 0.80\ \text{m/s}$. What is the average acceleration over the full 20-tick window from the first reading? (c) The robot has mass $m = 1.8\ \text{kg}$. What is the average net horizontal force on it over that 20-tick window? (d) Looking at the per-tick numbers in (a) and the broader average in (b), why might a motor-sizing calculation based on (b) alone leave you under-spec'd?

> [!NOTE]- Answer
> **(a) Single-tick average acceleration.**
> A 500 Hz loop has $\Delta t = 1/500 = 0.002\ \text{s}$. Then
> $$\bar a = \frac{0.35 - 0.32}{0.002} = \frac{0.03}{0.002} = 15\ \text{m/s}^2$$
> Positive — average acceleration points in the [[Positive Direction]] over that tick.
>
> **(b) 20-tick average acceleration.**
> Twenty ticks at 2 ms each is $\Delta t = 20 \cdot 0.002 = 0.040\ \text{s}$. The velocity changed from $v_i = 0.32\ \text{m/s}$ to $v_f = 0.80\ \text{m/s}$:
> $$\bar a_{0\to 20} = \frac{0.80 - 0.32}{0.040} = \frac{0.48}{0.040} = 12\ \text{m/s}^2$$
> Slightly lower than the per-tick value in (a), which already hints that the per-tick acceleration is not constant over the window.
>
> **(c) Average net force.**
> By [[Newton's Second Law]] in interval form, $\bar F = m\bar a$:
> $$\bar F = 1.8 \times 12 = 21.6\ \text{N}$$
> directed forward.
>
> **(d) Why average can mislead motor sizing.**
> The 20-tick average smears the first-tick value of 15 m/s² (and possibly higher peaks in between) into a single 12 m/s². If the per-tick acceleration spiked to, say, 20 m/s² during the most aggressive part of the spin-up, the *instantaneous* force on the drivetrain at that moment would be $1.8 \times 20 = 36\ \text{N}$ — well above the 21.6 N suggested by the average. Sizing the motor, gearbox, and coupling off the average force would leave them under-spec'd for the worst instant in the trajectory. For displacement and final velocity, use [[Average Acceleration]]; for force and torque limits, use the peak [[Instantaneous Acceleration]].
