---
tags: [dynamics, pre-release]
---
#dynamics #pre-release

## Definition
> [!definition]
> A **time interval** is the elapsed time between two instants, written $\Delta t = t_f - t_i$. It is a scalar quantity, always positive when measured forward in time, and it is the denominator that turns a [[Displacement]] into an [[Average Velocity]] and a change in [[Velocity]] into an [[Average Acceleration]].

Notes:
- A time interval is a **scalar**, not a vector — it has no direction. The two endpoints $t_i$ and $t_f$ are themselves instants on a chosen clock, but only their *difference* enters kinematic equations.
- $\Delta t$ is **positive when measured forward in time**. If you ever compute a negative $\Delta t$, you have swapped initial and final — fix the labels rather than carry a negative time.
- The choice of $t_i = 0$ is a convention, not a physical fact. Shifting the clock's zero changes $t_i$ and $t_f$ by the same amount, so $\Delta t$ is unchanged. This is why time intervals — not absolute times — appear in the [[Constant Acceleration Equations]].
- A time interval is the bridge from a **change** to a **rate**: [[Average Velocity]] is $\Delta\mathbf{r}/\Delta t$ and [[Average Acceleration]] is $\Delta\mathbf{v}/\Delta t$. Shrinking $\Delta t$ toward zero is what defines the instantaneous versions of both.
- In a digital control loop, the **sample period** $T_s$ *is* a time interval. A 1 kHz loop has $\Delta t = T_s = 1\ \text{ms}$ between encoder reads, and that number sets how finely you can resolve velocity from finite differences.
- For collisions and impacts the interval can be very short — milliseconds or less. That short $\Delta t$ becomes the [[Impact Duration]] in the impulse–momentum form of Newton's second law.
- Watch units. SI uses seconds; controller and microcontroller code often use milliseconds or microseconds. Mixing them silently is one of the most common bugs in motion code.

## Equations

> [!equation] Time interval between two instants
> $$\Delta t = t_f - t_i$$
>
> - $\Delta t$ — elapsed time (s)
> - $t_i$ — initial instant on the chosen clock (s)
> - $t_f$ — final instant on the same clock (s)
> - Always $\Delta t > 0$ when $t_f$ is later than $t_i$

## Examples and Non-Examples

- **Encoder sample interval.** A motor controller reads its quadrature encoder on a 1 kHz timer. Between two consecutive reads,
$$\Delta t = t_f - t_i = 1\ \text{ms} = 0.001\ \text{s}$$
That sample interval is what the firmware divides by to estimate [[Velocity]] from the change in encoder counts: $\bar v \approx \Delta x / \Delta t$.

- **Worked example — average velocity over a sample interval.** A linear stage's encoder reports position $x_i = 0.12450\ \text{m}$ at the start of a 2 ms control tick and $x_f = 0.12498\ \text{m}$ at the end. The time interval is
$$\Delta t = 2\ \text{ms} = 0.002\ \text{s}$$
and the displacement over that tick is $\Delta x = 0.12498 - 0.12450 = 0.00048\ \text{m}$. The [[Average Velocity]] computed by the loop is
$$\bar v = \frac{\Delta x}{\Delta t} = \frac{0.00048\ \text{m}}{0.002\ \text{s}} = 0.24\ \text{m/s}$$
The controller uses this $\bar v$ as its best estimate of the *instantaneous* velocity at the middle of the tick — accurate only because $\Delta t$ is small.

- **Impact interval.** A robot end-effector strikes a workpiece and rebounds; high-speed video shows contact lasts from $t_i = 0.04217\ \text{s}$ to $t_f = 0.04428\ \text{s}$. The [[Impact Duration]] is
$$\Delta t = 0.04428 - 0.04217 = 0.00211\ \text{s} \approx 2.1\ \text{ms}$$
This very short $\Delta t$ is what makes the contact force so large: a finite change in momentum divided by a tiny interval is a huge [[Average Acceleration]].

- **Counter-example — an instant is not an interval.** "The robot arrived at $t = 3.5\ \text{s}$" reports a single instant, not a time interval. You cannot divide a displacement by a single instant; you need *two* instants to form a $\Delta t$.

- **Counter-example — negative $\Delta t$.** Writing $\Delta t = t_i - t_f$ flips the sign and is the wrong convention. If your code or worksheet produces a negative time interval, you have the labels swapped, not a physically meaningful "backwards in time" — relabel and continue.

## Resources

- **[Michel van Biezen channel](https://www.youtube.com/@MichelvanBiezen)** — short physics-style examples of average velocity and acceleration; the $\Delta t$ in the denominator is exactly this page's quantity.
- **[CPPMechEngTutorials channel](https://www.youtube.com/@CPPMechEngTutorials)** — engineering-dynamics worked examples; useful for seeing $\Delta t$ used in rectilinear-motion problems.
- **[Wikipedia — Time](https://en.wikipedia.org/wiki/Time_in_physics)** — concise reference for time as a physical quantity and its role in kinematics.

## Practice

- A two-wheeled balancing robot runs its inner velocity loop at 500 Hz. Between two consecutive ticks the left wheel's encoder count changes by $\Delta n = 12$ counts. The encoder has 4096 counts per revolution and the wheel radius is $r = 0.035\ \text{m}$. (a) What is the time interval $\Delta t$ between ticks? (b) What is the displacement of the wheel's contact point over that interval? (c) What is the [[Average Velocity]] of the contact point during that tick?

> [!NOTE]- Answer
> **(a) Time interval.**
> A 500 Hz loop has a sample period equal to one over the rate:
> $$\Delta t = \frac{1}{500\ \text{Hz}} = 0.002\ \text{s} = 2\ \text{ms}$$
>
> **(b) Contact-point displacement.**
> Each count corresponds to an angular displacement of $2\pi / 4096$ rad. For 12 counts,
> $$\Delta\theta = 12 \cdot \frac{2\pi}{4096} \approx 0.01841\ \text{rad}$$
> The arc length at the contact point is
> $$\Delta x = r\,\Delta\theta = 0.035 \cdot 0.01841 \approx 6.44 \times 10^{-4}\ \text{m} \approx 0.64\ \text{mm}$$
>
> **(c) Average velocity.**
> $$\bar v = \frac{\Delta x}{\Delta t} = \frac{6.44 \times 10^{-4}\ \text{m}}{0.002\ \text{s}} \approx 0.322\ \text{m/s}$$
> The controller treats this as the wheel's instantaneous speed at the middle of the tick. The estimate is only as good as $\Delta t$ is small — halving the loop period would let it track faster speed changes but would also halve the count resolution per tick.
