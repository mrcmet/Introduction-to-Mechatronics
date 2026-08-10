---
tags: [dynamics, pre-release]
---
#dynamics #pre-release

## Definition
> [!definition]
> The **distance traveled** by a particle over a time interval is the total length of the path it sweeps out, measured as a non-negative scalar. It is the integral of [[Speed]] over time, $d = \int |v|\,dt$, or equivalently the sum of the lengths of every segment of the path. Unlike [[Displacement]], distance traveled depends on the *path*, not just the start and end [[Position]].

Notes:
- Distance traveled is a **scalar** and is **always $\geq 0$**. There is no "negative distance" — direction of motion is discarded when speed is taken as $|v|$.
- It is the integral of **speed**, not [[Velocity]]: $d = \int |v(t)|\,dt$. Integrating $v(t)$ instead gives [[Displacement]] and can produce cancellation when motion reverses.
- **Path-dependent.** Two trips with the same start and end [[Position]] can have very different distances traveled if the paths differ — a straight line vs. a detour, or a round trip back to the start.
- Distance traveled equals the magnitude of [[Displacement]] **only when** motion is in a single direction along a straight line. Any reversal makes distance strictly greater than $|\Delta x|$.
- For piecewise motion, distance traveled adds: if the path is a sequence of straight segments of lengths $\ell_1, \ell_2, \ldots, \ell_n$, then $d = \ell_1 + \ell_2 + \cdots + \ell_n$. Each $\ell_i$ is itself positive regardless of the [[Positive Direction]].
- This is the quantity an odometer measures. A car odometer counts up whether you drive forward or in reverse — it accumulates path length, not signed position.

## Equations

> [!equation] Distance traveled as a time integral
> $$d = \int_{t_i}^{t_f} |v(t)|\,dt$$
>
> - $d$ — distance traveled over the interval (m)
> - $|v(t)|$ — instantaneous [[Speed]] (m/s)
> - $t_i, t_f$ — start and end times (s)

> [!equation] Distance traveled as a sum of path segments
> $$d = \sum_{i=1}^{n} \ell_i, \qquad \ell_i \geq 0$$
>
> - $\ell_i$ — length of the $i$-th segment of the path (m)
> - $n$ — number of segments
> - Each $\ell_i$ is a positive length, independent of the chosen [[Positive Direction]]

## Examples and Non-Examples

- **Gantry traverse.** An XY gantry head is commanded to move from $\mathbf{r}_i = [0, 0]^T\ \text{m}$ to $\mathbf{r}_f = [0.30, 0.40]^T\ \text{m}$. The controller moves the X axis first (0.30 m), then the Y axis (0.40 m). The distance traveled is
$$d = 0.30 + 0.40 = 0.70\ \text{m}$$
The [[Displacement]] magnitude, by contrast, is $|\Delta\mathbf{r}| = \sqrt{0.30^2 + 0.40^2} = 0.50\ \text{m}$. The path-following move covers more ground than the straight-line shift.

- **Pick-and-place cycle.** A robot picks a part at $x = 0.10\ \text{m}$, carries it to $x = 0.60\ \text{m}$ to place it, then returns to a home position at $x = 0$ to wait. The distance traveled over the full cycle is
$$d = |0.60 - 0.10| + |0.0 - 0.60| = 0.50 + 0.60 = 1.10\ \text{m}$$
This is the number an energy-budget calculation cares about, because every meter of travel costs motor work — even the meters that undo previous motion.

- **Variable speed via integration.** A linear stage has speed $|v(t)| = 0.20 + 0.10\,t\ \text{m/s}$ for $t \in [0, 2]\ \text{s}$. Then
$$d = \int_0^2 (0.20 + 0.10\,t)\,dt = \left[0.20\,t + 0.05\,t^2\right]_0^2 = 0.40 + 0.20 = 0.60\ \text{m}$$

- **Counter-example — round trip.** A two-wheeled balancer rolls 2 m forward, then 2 m back to where it started. Its [[Displacement]] is $\Delta x = 0$, but its distance traveled is
$$d = 2 + 2 = 4\ \text{m}$$
Zero displacement, nonzero distance — this is the canonical case that separates the two ideas.

- **Counter-example — integrating velocity.** For the round trip above, $\int v\,dt = +2 + (-2) = 0$. That integral is [[Displacement]], not distance. To get distance you must integrate $|v|$, which gives $2 + 2 = 4\ \text{m}$. Forgetting the absolute value is the most common mistake on this topic.

## Resources

- **[CPPMechEngTutorials — Vector Dynamics playlist](https://www.youtube.com/playlist?list=PLZOZfX_TaWAEzhyvNT1e9jbmTt4Eqo8C0)** — engineering-mechanics treatment of rectilinear motion that contrasts path length with displacement.
- **[Michel van Biezen — channel](https://www.youtube.com/@MichelvanBiezen)** — short physics-style worked examples on distance vs. displacement and integrating speed over time.
- **[Wikipedia — Distance](https://en.wikipedia.org/wiki/Distance)** — concise reference on path length as a non-negative scalar and its contrast with displacement.

## Practice

- A SCARA arm performs the following motion along a single linear rail with [[Positive Direction]] to the right. Starting at $x = 0$: it moves to $x = 0.40\ \text{m}$, then to $x = 0.10\ \text{m}$, then to $x = 0.50\ \text{m}$. (a) What is the [[Displacement]] from start to end? (b) What is the total distance traveled along the path? (c) Why are the two answers different?

> [!NOTE]- Answer
> **(a) Displacement.**
> $$\Delta x = x_f - x_i = 0.50 - 0 = +0.50\ \text{m}$$
>
> **(b) Distance traveled.** Sum the lengths of the three segments:
> $$d = |0.40 - 0| + |0.10 - 0.40| + |0.50 - 0.10| = 0.40 + 0.30 + 0.40 = 1.10\ \text{m}$$
>
> **(c) Why they differ.**
> The arm reverses direction between the second and third moves. [[Displacement]] only compares the endpoints and ignores the reversal, while distance traveled accumulates every segment as a positive length. Whenever motion reverses, $d > |\Delta x|$ — and the gap between them is exactly the "wasted" travel that an energy or cycle-time budget has to account for.
