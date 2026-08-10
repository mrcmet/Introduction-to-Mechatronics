---
tags: [dynamics, pre-release]
---
#dynamics #pre-release

## Definition
> [!definition]
> **Average velocity** is the [[Displacement]] of a point divided by the [[Time Interval]] over which that displacement occurred. In one dimension it is the signed scalar $\bar v = \Delta x / \Delta t$, and in two or three dimensions it is the vector $\bar{\mathbf{v}} = \Delta\mathbf{r}/\Delta t$. It is the interval-averaged version of [[Velocity]] — distinct from [[Instantaneous Velocity]], which is the limit of this ratio as $\Delta t \to 0$.

Notes:
- Average velocity is a **vector quantity** (or a signed scalar in 1D). It carries direction, anchored to the chosen [[Positive Direction]]. The magnitude-only counterpart, computed from path length rather than displacement, is the **average speed** — see [[Speed]] and [[Distance Traveled]].
- It depends on **only the endpoints**. Because [[Displacement]] depends only on $\mathbf{r}_i$ and $\mathbf{r}_f$, every wiggle of the path between them is invisible to $\bar{\mathbf{v}}$. Two robots that take very different routes between the same two waypoints in the same $\Delta t$ have the same average velocity.
- Average velocity is **not the same as average speed**. Average velocity uses [[Displacement]]; average speed uses [[Distance Traveled]]. They agree only when motion is in a single direction along a straight line.
- It is **not the same as [[Instantaneous Velocity]]**. The instantaneous version is the derivative $d\mathbf{r}/dt$ at one instant. Average velocity is a ratio over an interval; the two coincide only in the limit $\Delta t \to 0$ (or when the velocity is exactly constant over the interval).
- In a discrete control loop, **every "velocity" the firmware computes is really an average velocity** over one sample period: $\bar v \approx (x_{k+1} - x_k)/T_s$. We *use* it as if it were instantaneous, which is fine when $T_s$ is small compared with the system's dynamics.
- Average velocity does **not** equal $(\mathbf{v}_i + \mathbf{v}_f)/2$ in general. That mean-of-endpoints formula only works under [[Constant Acceleration]]; with varying acceleration you must use the displacement-over-time definition.

## Equations

> [!equation] Average velocity in 1D
> $$\bar v = \frac{\Delta x}{\Delta t} = \frac{x_f - x_i}{t_f - t_i}$$
>
> - $\bar v$ — average velocity along the chosen axis (m/s)
> - $\Delta x$ — [[Displacement]] (m); sign set by the chosen [[Positive Direction]]
> - $\Delta t$ — [[Time Interval]] (s); always positive when measured forward in time

> [!equation] Average velocity as a vector
> $$\bar{\mathbf{v}} = \frac{\Delta \mathbf{r}}{\Delta t} = \frac{\mathbf{r}_f - \mathbf{r}_i}{t_f - t_i}$$
>
> - $\bar{\mathbf{v}}$ — average velocity vector (m/s)
> - $\Delta \mathbf{r}$ — displacement vector between the two instants (m)
> - $|\bar{\mathbf{v}}|$ — magnitude is *not* the average speed in general; see Notes above

## Examples and Non-Examples

- **Worked example — finite difference from encoder data.** A linear stage's encoder is sampled at 1 kHz. Two successive readings are $x_i = 0.20410\ \text{m}$ at $t_i = 0.000\ \text{s}$ and $x_f = 0.20446\ \text{m}$ at $t_f = 0.001\ \text{s}$. The [[Time Interval]] is $\Delta t = 0.001\ \text{s}$ and the [[Displacement]] is $\Delta x = 0.00036\ \text{m}$, so
$$\bar v = \frac{\Delta x}{\Delta t} = \frac{0.00036\ \text{m}}{0.001\ \text{s}} = 0.36\ \text{m/s}$$
The positive sign says the stage moved in the [[Positive Direction]] over that tick. The control loop treats this $\bar v$ as the [[Instantaneous Velocity]] near the middle of the sample window — accurate because $\Delta t$ is small compared with how fast the stage is actually accelerating.

- **Worked example — sampled trajectory over several ticks.** Suppose the same encoder reports four positions at $\Delta t = 10\ \text{ms}$ intervals: $x_0 = 0.000$, $x_1 = 0.004$, $x_2 = 0.011$, $x_3 = 0.021\ \text{m}$. The **overall** average velocity from $t_0$ to $t_3$ is
$$\bar v_{0\to 3} = \frac{x_3 - x_0}{3 \cdot \Delta t} = \frac{0.021 - 0.000}{0.030} = 0.70\ \text{m/s}$$
The per-tick averages are different (0.40, 0.70, 1.00 m/s) — they are climbing because the stage is accelerating. The overall $\bar v_{0\to 3}$ is *not* the simple mean of the three per-tick values in general; it is the total [[Displacement]] divided by the total [[Time Interval]].

- **2D mobile robot.** A mobile robot moves from $\mathbf{r}_i = [1.0, 2.0]^T\ \text{m}$ at $t_i = 0$ to $\mathbf{r}_f = [4.0, 6.0]^T\ \text{m}$ at $t_f = 5\ \text{s}$. Its average velocity vector is
$$\bar{\mathbf{v}} = \frac{1}{5}\begin{bmatrix}4.0 - 1.0\\6.0 - 2.0\end{bmatrix} = \begin{bmatrix}0.6\\0.8\end{bmatrix}\ \text{m/s}$$
with magnitude $|\bar{\mathbf{v}}| = \sqrt{0.6^2 + 0.8^2} = 1.0\ \text{m/s}$. That 1.0 m/s is the magnitude of the **average velocity**, not the average speed — the robot's actual path may be much longer than the straight line between the two waypoints.

- **Counter-example — round trip has zero average velocity.** A delivery robot drives 8 m down a corridor in 10 s and then drives 8 m back to its start in another 10 s. Total elapsed time $\Delta t = 20\ \text{s}$, but the [[Displacement]] is $\Delta x = 0$, so
$$\bar v = \frac{0}{20\ \text{s}} = 0\ \text{m/s}$$
Average velocity is zero even though the robot was moving the entire time. Its **average speed**, computed from [[Distance Traveled]] $= 16\ \text{m}$ over $20\ \text{s}$, is $0.8\ \text{m/s}$ — nonzero, as expected. This is the cleanest demonstration that average velocity and average speed are not the same quantity.

- **Counter-example — average velocity is not the mean of endpoint velocities.** A motor ramps from rest with non-constant torque, finishing at $v_f = 2\ \text{m/s}$ after 1 s, having covered $\Delta x = 0.8\ \text{m}$. The true average velocity is $\bar v = 0.8 / 1 = 0.80\ \text{m/s}$, **not** $(0 + 2)/2 = 1.0\ \text{m/s}$. The mean-of-endpoints shortcut is only valid under [[Constant Acceleration]].

## Resources

- **[CPPMechEngTutorials — Engineering Dynamics playlist](https://www.youtube.com/playlist?list=PLqesm9GxhGVQgR41eEgnwEzKFGHiYrTmX)** — engineering-mechanics treatment of rectilinear motion; the average-versus-instantaneous distinction appears throughout.
- **[Michel van Biezen channel](https://www.youtube.com/@MichelvanBiezen)** — short physics-style worked examples; search within the channel for "average velocity" for many matched problems.
- **[Wikipedia — Velocity (Average velocity)](https://en.wikipedia.org/wiki/Velocity#Average_velocity)** — concise reference for the formal definition and the contrast with average speed.

## Practice

- A two-wheeled balancing robot starts at $x_i = 0$ and drives forward to $x = 2.5\ \text{m}$ in 5 s, pauses for 2 s, then reverses and ends at $x_f = 1.0\ \text{m}$ at $t_f = 10\ \text{s}$. The [[Positive Direction]] is forward. (a) What is the robot's average velocity over the full 10 s trip? (b) What is its average velocity during just the reverse leg (from $t = 7\ \text{s}$ to $t_f = 10\ \text{s}$)? (c) What is the robot's **average speed** over the full trip, and why does it differ from (a)?

> [!NOTE]- Answer
> **(a) Overall average velocity.**
> $$\bar v = \frac{\Delta x}{\Delta t} = \frac{1.0 - 0.0}{10 - 0} = +0.10\ \text{m/s}$$
> Positive because the net [[Displacement]] is forward, even though the robot reversed for part of the trip.
>
> **(b) Reverse-leg average velocity.**
> Over the reverse leg the robot goes from $x = 2.5\ \text{m}$ at $t = 7\ \text{s}$ to $x = 1.0\ \text{m}$ at $t = 10\ \text{s}$:
> $$\bar v_{\text{rev}} = \frac{1.0 - 2.5}{10 - 7} = \frac{-1.5}{3} = -0.50\ \text{m/s}$$
> The negative sign tells the controller the robot is moving in the negative direction at 0.5 m/s during that leg.
>
> **(c) Average speed.**
> The [[Distance Traveled]] over the whole trip is $2.5 + 0 + 1.5 = 4.0\ \text{m}$ (forward leg + pause + reverse leg, using path lengths). The average speed is
> $$\bar s = \frac{\text{distance traveled}}{\Delta t} = \frac{4.0}{10} = 0.40\ \text{m/s}$$
> This is four times the magnitude of the answer to (a). Average velocity uses [[Displacement]] (endpoints only); average speed uses path length. They agree only when motion is in a single direction along a straight line — and this trip wasn't.
